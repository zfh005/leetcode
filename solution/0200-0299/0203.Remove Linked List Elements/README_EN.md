# [203. Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements)

[中文文档](/solution/0200-0299/0203.Remove%20Linked%20List%20Elements/README.md)

## Description

<p>Given the <code>head</code> of a linked list and an integer <code>val</code>, remove all the nodes of the linked list that has <code>Node.val == val</code>, and return <em>the new head</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://cdn.jsdelivr.net/gh/doocs/leetcode@main/solution/0200-0299/0203.Remove%20Linked%20List%20Elements/images/removelinked-list.jpg" style="width: 500px; height: 142px;" />
<pre>
<strong>Input:</strong> head = [1,2,6,3,4,5,6], val = 6
<strong>Output:</strong> [1,2,3,4,5]
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> head = [], val = 1
<strong>Output:</strong> []
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> head = [7,7,7,7], val = 7
<strong>Output:</strong> []
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the list is in the range <code>[0, 10<sup>4</sup>]</code>.</li>
	<li><code>1 &lt;= Node.val &lt;= 50</code></li>
	<li><code>0 &lt;= k &lt;= 50</code></li>
</ul>


## Solutions

<!-- tabs:start -->

### **Python3**

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeElements(self, head: ListNode, val: int) -> ListNode:
        dummy = ListNode(-1, head)
        pre = dummy
        while pre and pre.next:
            if pre.next.val != val:
                pre = pre.next
            else:
                pre.next = pre.next.next
        return dummy.next
```

### **Java**

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        ListNode dummy = new ListNode(-1, head);
        ListNode pre = dummy;
        while (pre != null && pre.next != null) {
            if (pre.next.val != val) pre = pre.next;
            else pre.next = pre.next.next;
        }
        return dummy.next;
    }
}
```

### **C++**

```cpp
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
        ListNode* dummy = new ListNode();
        dummy->next = head;
        ListNode* p = dummy;
        while (p->next) {
            if (p->next->val == val) {
                p->next = p->next->next;
            } else {
                p = p->next;
            }
        }
        return dummy->next;
    }
};
```

### **Go**

```go
func removeElements(head *ListNode, val int) *ListNode {
	dummy := new(ListNode)
	dummy.Next = head
	p := dummy
	for p.Next != nil {
		if p.Next.Val == val {
			p.Next = p.Next.Next
		} else {
			p = p.Next
		}
	}
	return dummy.Next
}
```

### **...**

```

```

<!-- tabs:end -->
