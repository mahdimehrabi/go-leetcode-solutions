# LeetCode 167: Two Sum II - Input Array Is Sorted

## Solution 1

To solve this problem, we can implement a two-pointer algorithm. Since the numbers are already sorted, we can set the first pointer to the first element of the array (the smallest number) and the second pointer to the last element of the array (the largest number). We then iterate through the array, checking the sum of the elements at the two pointers:

- If the sum of `nums[i] + nums[j]` is less than the target, we increase `i` (move the first pointer to the right) to get a larger sum.
- If the sum is greater than the target, we decrease `j` (move the second pointer to the left) to get a smaller sum.
- If `i` becomes equal to or greater than `j`, the iteration stops, indicating that no two numbers in the array add up to the target.

If we find that `nums[i] + nums[j] == target`, we return the 1-based indices of these two numbers.

```go
func twoSum(nums []int, target int) []int {
    i := 0
    j := len(nums) - 1
    
    for i != j {
        s := nums[i] + nums[j]
        
        if s > target {
            j--
        } else if s < target {
            i++
        } else {
            return []int{i + 1, j + 1}
        }
    }
    
    return []int{}
}
```


## Solution 2 

To solve this problem, we use a hashmap. We iterate through the numbers, and for each number, we calculate the difference between the target and the current number. We then check if this difference exists in the hashmap. If it does, we return the indices of the two numbers, incremented by 1 as required by the problem. If the difference does not exist in the hashmap, we add the current number and its index to the map.func twoSum(nums []int, target int) []int {
    i:=0
    j:=len(nums)-1
    for i!=j{
        s:=nums[i]+nums[j]
        if s>target{
            j--
        }else if s<target{
            i++
        }else{
            return []int{i+1,j+1}
        }
    }
    return []int{}
}



```go
func twoSum(numbers []int, target int) []int {
    mp:=make(map[int]int,0)

    for i:=0;i<len(numbers);i++{
        s:=target-numbers[i]
        if n,exist:=mp[s];exist{
            return []int{n+1,i+1}
        }

        mp[numbers[i]]=i
    }

    return []int{}
}
```
