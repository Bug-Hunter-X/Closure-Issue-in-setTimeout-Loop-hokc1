# Closure Issue in setTimeout Loop

This repository demonstrates a common issue in JavaScript related to closures and the `setTimeout` function. The problem arises when using a loop variable inside a `setTimeout` callback.

## Bug Description
The code in `bug.js` uses a `for` loop to schedule multiple `setTimeout` calls.  Each callback is intended to print the current value of `i`. However, due to the way closures work in JavaScript, all callbacks end up referencing the final value of `i` (which is 10) instead of their respective values at the time of scheduling.

## Solution
The `bugSolution.js` file provides a solution using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, capturing the correct value of `i` within each callback.