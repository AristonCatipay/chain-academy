```ts
// src/math.ts
export const PI: number = 3.14159

export function add(a: number, b: number): number{
    return a + b
}

export function subtract(a: number, b: number): number{
    return a - b
}
```
```ts
// src/greeting.ts
const generateGreeting = (name: string): string => {
    return `Hello, ${name}! Welcome to the tutorial.`
}

export default generateGreeting
```
```ts
// src/index.ts
import { PI, add } from "./math.js";
import { subtract as difference } from "./math.js";
import generateGreeting from "./greeting.js"

const x = 10
const y = 5

console.log(`The sum of ${x} and ${y} is:`, add(x, y))
console.log(`The difference of ${x} and ${y} is:`, difference(x, y))
console.log(`The PI is approximately:`, PI)
console.log(generateGreeting('Alice'))
```