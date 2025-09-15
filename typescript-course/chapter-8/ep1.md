```ts
class Person {
    name: string;

    constructor(name: string){
        this.name = name;
    }

    sayHello(): void{
        console.log(`Hello, my name is ${this.name}.`)
    }
}

const person1 = new Person("John")

console.log(person1.name)

person1.sayHello()
```
```ts
class Person {
    constructor(public name: string){}

    sayHello(): void{
        console.log(`Hello, my name is ${this.name}.`)
    }
}

const person1 = new Person("John")

console.log(person1.name)

person1.sayHello()
```
```ts
class Car {
    constructor(
        public make: string,
        public model: string,
        public year: number,
        public color: string
    ){}

    start(): string{
        return `${this.make} ${this.model} started.`
    }

    stop(): string{
        return `${this.make} ${this.model} stopped.`
    }
}

const car1 = new Car("Ford", "Mustang", 1964, "Red")
const car2 = new Car("Dodge", "Charger", 1966, "Silver")

console.log(car1.start())
console.log(car2.start())
console.log(car1.stop())
console.log(car2.stop())
console.log("Car 1 Release Date:", car1.year)
console.log("Car 2 Release Date:", car2.year)
console.log("Car 1 Color:", car1.color)
console.log("Car 2 Color:", car2.color)
```