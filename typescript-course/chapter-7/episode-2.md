```ts
interface Vehicle {
  name: string;
  id: number | string;
}

function processVehicle(vehicle: Vehicle){
  if (typeof vehicle.id === "string"){
    console.log(`Processing vehicle with string ID: ${vehicle.id.toUpperCase()}`)
  } else {
    console.log(`Processing vehicle with string ID: ${vehicle.id.toFixed(2)}`)
  }
}

const car: Vehicle = {
  name: "Sedan",
  id: "abc-123"
}

const bike: Vehicle = {
  name: "Mountain Bike",
  id: 1001
}

processVehicle(car)
processVehicle(bike)
```
```ts
interface Cat {
  name: string;
  purr: () => void;
}

interface Dog {
  name: string;
  bark: () => void;
}

type Pet = Cat | Dog

function playSound(pet: Pet){
  if ("purr" in pet){
    pet.purr()
  } else {
    pet.bark()
  }
}

const whiskers: Pet = {
  name: "Whiskers",
  purr: () => console.log("Meow... purrrrrr.")
}

const booster: Pet = {
  name: "Booster",
  bark: () => console.log("Woof! Woof!")
}

playSound(whiskers)
playSound(booster)
```
```ts
interface Cat {
  name: string;
  purr: () => void;
}

interface Dog {
  name: string;
  bark: () => void;
}

type Pet = Cat | Dog

function playSound(pet: Pet){
  if ("purr" in pet){
    pet.purr()
  } else {
    pet.bark()
  }
}

const whiskers: Pet = {
  name: "Whiskers",
  purr: () => console.log("Meow... purrrrrr.")
}

const booster: Pet = {
  name: "Booster",
  bark: () => console.log("Woof! Woof!")
}

// playSound(whiskers)
// playSound(booster)

function isCat(pet: Pet): pet is Cat{
  return (pet as Cat).purr !== undefined
}

function playSoundWithCustomGaurd(pet: Pet){
  if (isCat(pet)){
    pet.purr()
  } else {
    pet.bark()
  }
}

playSoundWithCustomGaurd(whiskers)
playSoundWithCustomGaurd(booster)
```