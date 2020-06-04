# Linked-list

+ [reverse-linked-list](#reverse-linked-list)


##reverse-linked-list

https://leetcode.com/problems/reverse-linked-list/

```python
def reverseList(self, head: ListNode) -> ListNode:
    curr = head
    top = None
    newNode = None

    while curr is not None:
        newNode = ListNode(curr.val)
        newNode.next = top
        top = newNode
        curr = curr.next

    return newNode

```