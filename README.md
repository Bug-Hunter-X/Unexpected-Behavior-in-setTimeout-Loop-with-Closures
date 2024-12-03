# Unexpected Behavior in setTimeout Loop with Closures

This repository demonstrates a common JavaScript closure issue encountered when using `setTimeout` within a loop.  The expected behavior is to print the values 0 through 9 after a one-second delay for each iteration. However, the code unexpectedly prints the value 10 ten times. This occurs because the closure created by the `setTimeout` callback refers to the variable `i`, and by the time the `setTimeout` functions execute, the loop has already completed, resulting in `i` having its final value of 10.

## Solution

The solution involves using an immediately invoked function expression (IIFE) or `let` to create a new scope for each iteration, ensuring each closure captures a unique value of `i`.