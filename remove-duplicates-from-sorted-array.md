# remove duplicates from sorted array
This solution removes duplicates from a sorted slice of integers and returns the count of unique elements. We use a pointer k to track the position of the next unique element. Starting from the second element, we iterate through the slice and check if the current element is different from the last unique element. If it is, we move it to the position indicated by k and increment k. Finally, k represents the number of unique elements in the slice.

### Full code
``` go
func removeDuplicates(nums []int) int {
    k := 1
    for i := 1; i < len(nums); i++ {
        if nums[k-1] != nums[i] {
            nums[k] = nums[i]
            k++
        }
    }
    return k
}


```
