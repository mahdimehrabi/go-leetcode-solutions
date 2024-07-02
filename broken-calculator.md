# Leetcode 991. Broken Calculator 

The solution works by reversing the operations, starting from the `target` and working backwards to the `startValue`. Here's a step-by-step explanation:

1. **Base Case**: If `startValue` is greater than or equal to `target`, return the difference `startValue - target` because the only operation needed is decrementing `startValue` until it equals `target`.
2. **Recursive Case**:
   - If `target` is even, halve it (`target / 2`) and recursively solve for the new target.
   - If `target` is odd, increment it (`target + 1`) to make it even, and then recursively solve for the new target.

This approach ensures minimal operations by efficiently reducing the problem size at each step.

### Code
```go
func brokenCalc(startValue int, target int) int {
    if startValue >= target {
        return startValue - target
    }
    if target % 2 == 0 {
        return brokenCalc(startValue, target / 2) + 1
    }
    return brokenCalc(startValue, target + 1) + 1
}
```

