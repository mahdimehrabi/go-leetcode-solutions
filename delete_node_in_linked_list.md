# Leetcode 237. Delete Node in a Linked List
in order to solve this problem we just need to copy the next element of our linked list to current one and delete next one. 




```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func deleteNode(node *ListNode) {
    node.Val=node.Next.Val
    node.Next=node.Next.Next
}
```
