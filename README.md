# JavaScript Closure Problem with setTimeout

This repository demonstrates a common issue in JavaScript related to closures and the `setTimeout` function.  The problem arises when using `setTimeout` within a loop, leading to unexpected behavior due to how closures capture variables.

## The Bug

The `bug.js` file contains a function `myFunction` that iterates ten times and uses `setTimeout` to log the value of `i` after a one-second delay.  Intuitively, one would expect the output to be the numbers 0 through 9, each printed after a one-second interval. However, due to the closure's late capture of the variable `i`, the actual output is 10 printed ten times.

## The Solution

The `bugSolution.js` file demonstrates how to resolve this by creating a new scope for each iteration of the loop using an immediately invoked function expression (IIFE). This ensures each `setTimeout` callback has its own copy of the `i` value at the time the callback was created, resulting in the expected output. 

## How to Run

1. Clone this repository.
2. Navigate to the directory in your terminal.
3. Run the buggy code using: `node bug.js`
4. Run the solution code using: `node bugSolution.js`

Observe the difference in the output to understand the problem and its solution.