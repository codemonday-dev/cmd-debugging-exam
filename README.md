# Debugging skill exam

## Exercise 1: Infinite Loop (3 Minutes)

**Description:** The following pseudo code is intended to print numbers from 1 to 10, but it runs indefinitely. Identify and fix the issue.

```js
function printNumbers() {
  let i = 1
  let j = 0

  while (i <= 10) {
    console.log(i)
    j++
  }
}
```

**Challenge:** Fix the loop so it terminates correctly.

---

## Exercise 2: Understanding Function Composition, Loop Logic, and Conditional Execution (5 Minutes)

**Description:**
Find the final value of `ans` by tracing the code step-by-step,

```js
f = (x) => 2*x
g = (y) => 3*y+1

ans = 0
result = 0
n=2
for(i=1; i<5; i++) {
    result = ans * 2 || 2
}
while(n>0) {
    ans = g(ans)
    n = n - 2
}
if(f(2) < g(0)){
    ans = g(0) + result
}
```

## Exercise 3: Class (3 Minutes)
Consider the file `ab.js`
```js
export class A { 
  constructor() { this.x = 0 }
  increment() { return ++this.x }
}

const newA = new A()
export const a = newA
export const b = new A()
export function makeA() {
  return new A()
}
```
then file `ex.js`
```js
import { a, b, A, makeA } from "./ab.js"

export function execute() {
  const c = makeA()
  console.log((new A()).increment())
  console.log(a.increment())
  console.log(b.increment())
  console.log(c.increment())
}
```
then `main.js` 
```js
import { execute } from "./ex.js"
execute()
execute() // answer the result
```
what is output result of second `execute()`

## Exercise 4: Scaling our service (3 Minutes)
We are trying to scale this Express service
```js
queue.consume(msg => {
  process(msg)
})

cron(* 12 * * *) {
  sendEmail()
}

app.get('/service', async (req, res) => {
   return ...
})
```
Are there any problem if we install load balancer and scale this service from 1 to 4 instances

## Exercise 5: Error Handling and Synchronous (3 Minutes)
```js
const f = () => { throw new Error("X") }
const g = () => {
  Promise.resolve()
    .then(() => { 
       console.log("E")
       throw new Error("F")
    })  
    .catch((err) => {
       throw err 
       console.log("G")
     })  
    .catch((err) => {
       console.log("H")
       throw new Error("I")
       throw new Error("J")
    })  
    .finally(() => {
      throw new Error("K")
    })  
}

console.log("A")
try {
  f() 
  console.log("B")
} catch {
  console.log("C")
}
console.log("D")
try {
  g() 
  throw new Error("L")
} catch {
  console.log("M")
  throw new Error("N")
}
console.log("O")
```
What is the output printed to console

## Exercise 6:
let's assume that we have some dummy bank account service
```js
let balance = 100

function deposit(x) {
  return new Promise(r =>
    setTimeout(() => { balance += x; r(balance) }, Math.random() * 10)
  )
}

function withdraw(x) {
  return new Promise(r => {
    if (balance >= x)
      setTimeout(() => { balance -= x; r(true) }, Math.random() * 10)
    else
      r(false)
  })
}

const result = await Promise.all([
  deposit(50),
  withdraw(120),
  deposit(30),
])

console.log("result:", result)
console.log("balance:", balance)
```
what is the outcome out the program
