# Leetcode 1: twoSum 

To solve this problem, we use a hashmap and iterate through the array of numbers. In each iteration, we add the current number and its index to the hashmap. We then check if the complement of the current number (i.e., target - current number) already exists in the hashmap. If it does, we return the indices of the current number and its complement.


# Golang codes
```go
func twoSum(nums []int, target int) []int {
    mp:=make(map[int]int,0)

    for i:=0;i<len(nums);i++{
        s:=target-nums[i]
        if n,exist:=mp[s];exist{
            return []int{i,n}
        }
        mp[nums[i]]=i
    }

    return []int{}
}
```
