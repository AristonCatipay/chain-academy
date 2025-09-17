```ts
class Vehicle {
    protected speed: number;

    constructor(speed: number){
        this.speed = speed;
    }

    public getSpeed(): number{
        return this.speed;
    }
}

class Car extends Vehicle {
    private make: string;
    private model: string;

    constructor(speed: number, make: string, model: string){
        super(speed)
        this.make = make;
        this.model = model;
    }

    public drive(): string {
        return `The ${this.make} ${this.model} is traveling at ${this.speed} mph.`
    }
}

const car = new Car(60, "Ford", "Mustang")
console.log(car.drive())
console.log(car.getSpeed())
```
```ts
class Animal {
    public makeSound(): void{
        console.log("The animal makes a sound.")
    }
}

class Dog extends Animal {
    public makeSound(): void {
        console.log("The dog barks.")
    }
}

const genericAnimal = new Animal()
const booster = new Dog()

genericAnimal.makeSound()
booster.makeSound()
```
```ts
class MathUtil {
    public static PI = 3.14159;

    public static calculateCircumference(radius: number): number{
        return 2 * this.PI * radius
    }
}

console.log(MathUtil.PI)
console.log(MathUtil.calculateCircumference(5))
```
```ts
abstract class Shape {
    public abstract getArea(): number;

    public toString(): string{
        return `This is a shape.`
    }
}

class Circle extends Shape{
    constructor(private radius: number){
        super()
    }

    public getArea(): number {
        return Math.PI * this.radius * this.radius
    }
}

const circle = new Circle(10)
console.log(circle.getArea())
```