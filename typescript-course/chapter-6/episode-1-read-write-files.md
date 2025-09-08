```ts
import { readFile, writeFile } from "fs/promises";
import * as path from "path"

async function readFileContent(){
    const filePath = path.join(__dirname, "..", "src", "sample.txt")

    try {
        const content = await readFile(filePath, { encoding: "utf-8"})
        console.log("File content:", content)
    } catch (error) {
        console.error("Error reading file:", error)
    }
}

async function writeToFile(){
    const filePath = path.join(__dirname, "..", "src", "output.txt")

    const data = "This is a new data written to a file using TypeScript and async/await."

    try {
        await writeFile(filePath, data, { encoding: "utf-8"})
        console.log("Successfully wrote to output.txt.")
    } catch (error) {
        console.error("Error writing file:", error)
    }
}

interface Data {
    name: string;
    version: string;
    active: boolean;
}

async function readAndModifyJson(){
    const filePath = path.join(__dirname, "..", "src", "data.json")

    try {
        const content = await readFile(filePath, { encoding: "utf-8"})

        const data: Data = JSON.parse(content)

        console.log("Original JSON data:", data)

        data.version = "2.0.0"
        data.active = false

        const updatedContent = JSON.stringify(data, null, 2)

        await writeFile(filePath, updatedContent, { encoding: "utf-8"})
        console.log("Successfully updated data.json.")
    } catch (error) {
        console.error("Error handling JSON file:", error)
    }
}

async function main(){
    await readFileContent()
    await writeToFile()
    await readAndModifyJson()
}

main()
```