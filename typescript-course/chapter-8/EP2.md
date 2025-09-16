```ts
class BankAccount {
    public accountNumber: string;
    public balance: number;

    constructor(accountNumber: string, initialBalance: number){
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    public deposit(amount: number): void{
        this.balance += amount;
        console.log(`Deposited ${amount}. New balance is ${this.balance}.`)
    }
}

const myAccount = new BankAccount("123456", 100)

console.log("Balance:", myAccount.balance)
myAccount.deposit(100)
console.log("Balance:", myAccount.balance)
myAccount.balance = 100000
console.log("Balance:", myAccount.balance)
```
```ts
class BankAccount {
    private _accountNumber: string;
    private _balance: number;

    constructor(accountNumber: string, initialBalance: number){
        this._accountNumber = accountNumber;
        this._balance = initialBalance;
    }

    public deposit(amount: number): void{
        this._balance += amount;
        console.log(`Deposited ${amount}. New balance is ${this._balance}.`)
    }

    public getBalance(): number{
        return this._balance;
    }
}

const myAccount = new BankAccount("123456", 100)

// console.log(myAccount._balance)
// myAccount._balance = 100000

myAccount.deposit(100)
console.log(myAccount.getBalance())
```
```ts
class Parent {
    protected familyName: string;

    constructor(familyName: string){
        this.familyName = familyName;
    }
}

class Child extends Parent {
    public getFamilyName(): string{
        return `The family name is ${this.familyName}`
    }
}

const child = new Child("Smith")
// console.log(child.familyName)
console.log(child.getFamilyName())

```
```ts
class Product {
    public readonly id: string;
    public name: string;

    constructor(id: string, name: string){
        this.id = id;
        this.name = name;
    }
}

const laptop = new Product("LAP-001", "Laptop")

console.log(laptop.id)
laptop.id = "LAP-002" // Error
```
```ts

```
```ts

```