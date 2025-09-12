```ts
interface User {
  name: string;
  address? : {
    street: string;
    city: string;
  }
}

const user: User = {
  name: "Alex"
}

// console.log(user.address.city)

let city;
if (user.address){
  city = user.address.city
}
console.log(city)
```
```ts
interface User {
  name: string;
  address? : {
    street: string;
    city: string;
  }
}

const user: User = {
  name: "Alex"
}

const anotherUser: User = {
  name: "Charlie",
  address: {
    street: "123 Main St",
    city: "Example City"
  }
}

// console.log(user.address.city)

// let city;
// if (user.address){
//   city = user.address.city
// }
// console.log(city)

const city = user.address?.city
console.log(city)

const anotherUserCity = anotherUser.address?.city
console.log(anotherUserCity)
```
```ts
function getScore(score: number | null | undefined): number{
  const finalScore = score ?? 10
  return finalScore
}

console.log(getScore(0))
console.log(getScore(null))
console.log(getScore(25))
```
```ts
function getScore(score: number | null | undefined): number{
  const finalScore = score || 10
  return finalScore
}

console.log(getScore(0))
console.log(getScore(null))
console.log(getScore(25))
```
```ts
interface User {
  name: string;
  address? : {
    city: string;
  }
}

function getUserCity(user: User): string{
  return user.address?.city ?? "City not provided"
}

const user1: User = {
  name: "Alice",
  address: {
    city: "Example City"
  }
}

const user2: User = {
  name: "Alex"
}

console.log(getUserCity(user1))
console.log(getUserCity(user2))
```