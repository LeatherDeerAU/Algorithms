# Linked-list

+ [reverse-linked-list](#reverse-linked-list)
+ [middle-of-the-linked-list](#middle-of-the-linked-list)


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

##middle-of-the-linked-list

https://leetcode.com/problems/middle-of-the-linked-list/#

```python
def middleNode(self, head: ListNode) -> ListNode:
    count = 1
    cur = head
    while cur.next != None:
        cur = cur.next
        count += 1

    count = count // 2 + 1

    for i in range(count - 1):
        head = head.next
    return head

```
