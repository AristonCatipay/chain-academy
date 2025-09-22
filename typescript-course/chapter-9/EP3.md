```ts
interface User {
    id: number;
    name: string;
    email: string;
    isActive: boolean;
}

let myUser: User = {
    id: 1,
    name: "Alice",
    email: "alice@example.com",
    isActive: true
}

console.log("Original User:", myUser)

function updateUserProfile(user: User, updates: Partial<User>): User{
    return Object.assign(user, updates)
    // { id: 1, name: 'Alice', email: "new.alice@example.com", isActive: true }
}

let updatedUser = updateUserProfile(myUser, { email: "new.alice@example.com" })
console.log("Updated User:", updatedUser)
```
```ts
interface Product {
    id: number;
    name: string;
    price: number;
    description: string;
    inStock: boolean;
}

type ProductPreview = Pick<Product, "name" | "price">

const shirtPreview: ProductPreview = {
    name: "T-Shirt",
    price: 25.00
}

const bagPreview: ProductPreview = {
    name: "Bag",
    price: 50.00,
    // description: "A cool bag",
}
```
```ts
interface User {
    id: number;
    name: string;
    email: string;
    createdAt: Date;
}

type UserCreation = Omit<User, "id" | "createdAt">

const newUser: UserCreation = {
    name: "Charlie",
    email: "charlie@example.com"
}

console.log("New User:", newUser)

const invalidUser: UserCreation = {
    // id: 1,
    name: "Dave",
    email: "dave@example.com"
}
```