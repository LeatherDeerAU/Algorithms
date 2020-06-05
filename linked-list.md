# Linked-list

+ [Reverse linked list](#reverse-linked-list)
+ [Middle of the linked list](#middle-of-the-linked-list)
+ [Palindrome linked list](#palindrome-linked-list)
+ [Merge two sorted lists](#merge-two-sorted-lists)
+ [Remove nth node from end of list](#remove-nth-node-from-end-of-list)
+ [Linked list cycle ii](#linked-list-cycle-ii)
+ [Linked list cycle](#linked-list-cycle)
+ [Reorder list](#reorder-list)


##Reverse linked list

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

##Middle of the linked list

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

##Palindrome linked list

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

##Merge two sorted lists

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

##Remove nth node from end of list

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
    current = head
    count = 0
    while current:
        current = current.next
        count += 1
    i = 0
    current = head
    while i < count - n - 1:
        current = current.next
        i += 1
    if n == count:
        head = current.next
    else:
        current.next = current.next.next
    return head
```

##Linked list cycle ii

https://leetcode.com/problems/linked-list-cycle-ii/

```python
class Solution:
    def detectCycle(self, head: ListNode) -> ListNode:
        nodes = set()
        while head:
            if head not in nodes:
                nodes.add(head)
            else:
                return head
            head = head.next
        return None
```

##Linked list cycle

https://leetcode.com/problems/linked-list-cycle/

```python
    def hasCycle(self, head: ListNode) -> bool:
        nodes = set()
        while head:
            if head not in nodes:
                nodes.add(head)
            else:
                return head
            head = head.next
        return None
```

##Reorder list

https://leetcode.com/problems/reorder-list/

```python
    def reorderList(self, head: ListNode) -> None:
        """
        Do not return anything, modify head in-place instead.
        """
        if not head:
            return head
        def getList(head):
            ls = []
            while head:
                ls.append(head)
                head = head.next
            return ls
    
        ls = getList(head)
        for i in range(1,len(ls)//2+1):
            ls[i-1].next = ls[len(ls)-i]
            ls[len(ls)-i].next = ls[i]
            ls[len(ls)//2].next = None
```
