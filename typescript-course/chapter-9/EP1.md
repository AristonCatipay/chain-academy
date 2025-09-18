```ts
function identityAny(argument: any): any{
  return argument;
}

const output = identityAny("Hello World!")
console.log("Output:", output)
console.log("Length:", output.length)
```
```ts
// <T>
function identity<T>(argument: T): T{
  return argument;
}

const output = identity<string>("Hello World!")
console.log("Output:", output)
console.log("Length:", output.length)
console.log("Uppercase:", output.toUpperCase())

const outputNumber = identity<number>(30)
console.log("Output:", outputNumber)
console.log("To Fixed:", outputNumber.toFixed(2))
```
```ts
// <T>
function identity<T>(argument: T): T{
  return argument;
}

const output = identity<string>("Hello World!")
console.log("Output:", output)
console.log("Length:", output.length)
console.log("Uppercase:", output.toUpperCase())

const outputNumber = identity<number>(30)
console.log("Output:", outputNumber)
console.log("To Fixed:", outputNumber.toFixed(2))

const inferredString = identity("Hello Generics")
console.log("Output", inferredString)
console.log("Length", inferredString.length)
console.log("Lowercase", inferredString.toLowerCase())

const inferredNumber = identity(300)
console.log("Output:", inferredNumber)
console.log("To Fixed:", inferredNumber.toFixed(4))
```
```ts
function firstElement<T>(array: T[]): T | undefined{
  if (array.length > 0){
    return array[0]
  }
  return undefined
}

const numbers = [1, 2, 3]
const strings = ["apple", "banana", "cherry"]
const booleans = [true, false]


const firstNumber = firstElement(numbers)
const firstString = firstElement(strings)
const firstBoolean = firstElement(booleans)

console.log("First Number:", firstNumber)
console.log("First String:", firstString)
console.log("First Boolean:", firstBoolean)
```