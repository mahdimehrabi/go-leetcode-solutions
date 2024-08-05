# Leetcode 167: Two Sum II - Input Array Is Sorted

To solve this problem, we use a hashmap. We iterate through the numbers, and for each number, we calculate the difference between the target and the current number. We then check if this difference exists in the hashmap. If it does, we return the indices of the two numbers, incremented by 1 as required by the problem. If the difference does not exist in the hashmap, we add the current number and its index to the map.


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
