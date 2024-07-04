# Leetcode 3191: Minimum Operations to Make Binary Array Elements Equal to One I

The solution involves iterating over each element in the array except the last two. If the current element is `0`, we flip it and its next two elements. At the end, we check if either of the last two elements is `0`. If so, it means it is not possible to make all elements in the array equal to `1`, so we return `-1`.

### Code
```go
func minOperations(nums []int) int {
	times := 0
	n := len(nums)
	for i := 0; i <= n-3; i++ {
		if nums[i] == 0 {
			nums[i] ^= 1
			nums[i+1] ^= 1
			nums[i+2] ^= 1
			times++
		}
	}

	if nums[n-1] == 0 || nums[n-2] == 0 {
		return -1
	}

	return times
}
```

