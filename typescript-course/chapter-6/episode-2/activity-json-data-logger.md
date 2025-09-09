```ts
import { readFile, writeFile } from "fs/promises";
import * as path from "path"

type BPReading = {
  date: string;
  systolic: number;
  diastolic: number;
  note?: string;
}

const filePath = path.join(__dirname, "..", "src", "bpData.json")

async function saveReading(reading: BPReading){
  let data: BPReading[] = []

  try {
    const file = await readFile(filePath, "utf-8")
    data = JSON.parse(file)
  } catch (error) {
    console.log("No existing file, creating a new one...")
  }

  data.push(reading)

  await writeFile(filePath, JSON.stringify(data, null, 2), "utf-8")

  console.log("Reading saved!")
}

async function loadReadings(): Promise<BPReading[]>{
  try {
    const file = await readFile(filePath, "utf-8")
    const data: BPReading[] = JSON.parse(file)
    return data
  } catch (error) {
    console.log("No readings found yet.")
    return []
  }
}

async function showHighReadings(){
  const data = await loadReadings()
  const high = data.filter((reading) => reading.systolic > 130)
  console.log("High BP Readings:", high)
}

async function main(){
  const newReading: BPReading = {
    date: new Date().toISOString(),
    systolic: 143,
    diastolic: 92,
    note: "After breakfast."
  }

  await saveReading(newReading)

  const all = await loadReadings()

  console.log("All readings:", all)

  await showHighReadings()
}

main()
```