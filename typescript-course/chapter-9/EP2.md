```ts
function logLength<T>(argument: T){
    console.log(argument.length)
}

logLength("Hello Generics")
logLength(30)
```
```ts
interface HasLength {
    length: number
}

function logLength<T extends HasLength>(argument: T){
    console.log(argument.length)
}

logLength("Hello Generics")
logLength([1, 2, 3])
// logLength(30)
```

```ts
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K]{
    return obj[key]
}

const exampleObject = { name: "John", age: 30}

const value1 = getProperty(exampleObject, "name")
console.log(value1)

const value2 = getProperty(exampleObject, "address")
```