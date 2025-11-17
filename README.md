# Debugging skill exam

## Exercise 1: Infinite Loop (3 Minutes)

**Description:** The following pseudo code is intended to print numbers from 1 to 10, but it runs indefinitely. Identify and fix the issue.

```
function printNumbers():
    i = 1
    j = 0
    while i <= 10:
        print(i)
        j++
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
```
class A
	constructor() : this.x = 0
	increment() : this.x += 1
a = new A()

export a
```
and
```
class B
	constructor() { this.x = 0 }
	increment() { this.x += 1 }

export new B()
```
then file x
```
import A
import B
function execute()
	print A.increment()
	print B.increment()
```
then main
```
import execute from X
execute()
execute()
```
what is result to the console
