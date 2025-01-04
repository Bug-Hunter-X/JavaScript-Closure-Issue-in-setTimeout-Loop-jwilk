# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue that arises when using `setTimeout` within a loop.  The code intends to log numbers 0 through 9 with a one-second delay between each log. However, due to how closures work in JavaScript, the code will instead log the number 10 ten times.

## Problem

The issue stems from the fact that the `setTimeout` callback function doesn't create a new closure for each iteration of the loop.  Instead, it references the variable `i` in the outer scope, which only gets updated after the loop completes. Therefore when the `setTimeout` functions finally execute, 'i' is already 10.

## Solution

The solution involves using an immediately invoked function expression (IIFE) or `let` to create a new scope for each iteration, thus preserving the correct value of `i` for each callback.