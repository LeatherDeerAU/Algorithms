# Linked-list

+ [reverse-linked-list](#reverse-linked-list)
+ [middle-of-the-linked-list](#middle-of-the-linked-list)
+ [palindrome-linked-list](#palindrome-linked-list)
+ [merge-two-sorted-lists](#merge-two-sorted-lists)


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

##palindrome-linked-list

https://leetcode.com/problems/palindrome-linked-list/

```python
def isPalindrome(self, head: ListNode) -> bool:
    numList = []

    while head is not None:
        numList.append(head.val)
        head = head.next

    numList2 = numList[::-1]

    if numList2 == numList:
        return True
    else:
        return False

```

##merge-two-sorted-lists

https://leetcode.com/problems/merge-two-sorted-lists/

```python
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    if l1 is None:
        return l2
    if l2 is None:
        return l1

    ans = ListNode(0)
    newList = ans
    while l1 != None and l2 != None:
        if l1.val <= l2.val:
            newList.next = l1
            l1 = l1.next
        else:
            newList.next = l2
            l2 = l2.next

        newList = newList.next

    if l1 == None:
        newList.next = l2
    elif l2 == None:
        newList.next = l1

    return ans.next

```