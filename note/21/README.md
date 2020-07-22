# [Merge Two Sorted Lists](https://leetcode-cn.com/problems/merge-two-sorted-lists/)

## Description

Merge two sorted linked lists and return it as a new sorted list. The new list should be made by splicing together the nodes of the first two lists.

### Example:

````
Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4
````

## 思路

利用递归，每次选小的节点。

## 代码
```` Go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func mergeTwoLists(l1 *ListNode, l2 *ListNode) *ListNode {
    if l1 == nil {
        return l2
    }
    if l2 == nil {
        return l1
    }
    if l1.Val <= l2.Val {
        l1.Next = mergeTwoLists(l1.Next,l2)
        return l1
    } else {
        l2.Next = mergeTwoLists(l1,l2.Next)
        return l2
    }
}
````

