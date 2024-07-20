# Leetcode 995. Minimum Number of K Consecutive Bit Flips

In this solution, we implement a greedy algorithm using a queue to efficiently track and simulate the flip operations. Here's a step-by-step explanation:

1. **Iterate Through Items**: We use a linear loop to traverse the array, processing each bit one by one.
2. **Manage the Flip Window**: We maintain a queue to keep track of the flip operations. If the current index surpasses the effective range of the first flip operation in the queue, we remove it from the queue.
    ```go
    if len(q) > 0 && i > q[0]+k-1 {
        q = q[1:]
    }
    ```
3. **Check If Flip is Needed**: For each bit, we check if it needs to be flipped by considering the cumulative effect of all flips stored in the queue. This is done by evaluating if the sum of the bit and the queue length is even.
    ```go
    if (nums[i]+len(q))%2 == 0 {
    ```
4. **Validate Flip Range**: Before performing a flip, we ensure that the operation is within bounds. If not, we return `-1` as it's impossible to achieve the desired outcome.
    ```go
    if i+k > n {
        return -1
    }
    ```
5. **Perform Flip and Update Queue**: If a flip is needed and valid, we increment the flip count and add the current index to the queue to mark the start of a new flip range.
    ```go
    times++
    q = append(q, i)
    ```

### Full Code

```go
func minKBitFlips(nums []int, k int) int {
    times := 0
    n := len(nums)
    q := make([]int, 0)

    for i := 0; i < n; i++ {
        // Remove the first flip if it's out of the current window
        if len(q) > 0 && i > q[0]+k-1 {
            q = q[1:]
        }
        // Check if the current bit needs to be flipped
        if (nums[i]+len(q))%2 == 0 {
            // Check if a flip is possible within bounds
            if i+k > n {
                return -1
            }
            // Perform the flip and record its start
            times++
            q = append(q, i)
        }
    }

    return times
}
```
