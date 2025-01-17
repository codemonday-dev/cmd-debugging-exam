# Debugging skill exam

## Exercise 1: Infinite Loop

**Description:** The following pseudo code is intended to print numbers from 1 to 10, but it runs indefinitely. Identify and fix the issue.

```
function printNumbers():
    i = 1
    while i <= 10:
        print(i)
```

**Challenge:** Fix the loop so it terminates correctly.

---

## Exercise 2: Incorrect Output

**Description:** The function is supposed to return the sum of all even numbers in a given list, but it returns an incorrect result.

```
function sumEvenNumbers(numbers):
    sum = 0
    for number in numbers:
        if number % 2 == 1:
            sum += number
    return sum
```
**Challenge:** Identify and fix the logic error.

---

## Exercise 3: Array Manipulation and Aggregation

**Description:**
The function processes an array of objects representing sales transactions. Each transaction contains an id, product, quantity, and price. The goal is to calculate the total revenue for each product, but the implementation contains several bugs and inefficiencies.

```
function calculateRevenue(transactions):
    productRevenue = []
    
    for transaction in transactions:
        if transaction.quantity > 0 or transaction.price > 0:  // Ignore invalid transactions
            revenue = transaction.quantity * transaction.price
            product = transaction.product
            
            // Check if product exists in productRevenue
            for entry in productRevenue:
                if entry.product == product:
                    entry.revenue += revenue
                else:
                    productRevenue.append({ product: product, revenue: revenue })
    
    // Sort products by revenue in descending order
    sortedRevenue = productRevenue.sort((a, b) => a.revenue - b.revenue)
    
    return sortedRevenue
```

**Challenge:**

 - Fix all logical errors.
 - Optimize the function to avoid duplicate entries in productRevenue.
 - Ensure proper error handling for edge cases.
