**Problem 1 in Top Interview Questions (medium): Linked Lists**

Leetcode Problem 2: Add Two Numbers

Problem Link:  https://leetcode.com/problems/add-two-numbers/

Explanation:



 Java Solution: 
     n = # elements in l1         m = # elements in l2

​     Space: O(n+m)
​     Time: O(max(n,m)):

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
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummyhead = new ListNode();
        ListNode sumhead = dummyhead;
        
        int sum = 0, carry=0;
        
        while(l1 != null || l2 != null){
            sum = 0;
            if(l1!=null){sum+= l1.val; l1 = l1.next; }
            if(l2!=null){ sum+= l2.val; l2 = l2.next; }
            sum += carry;
            carry = sum / 10;
            sum = sum %10;
            sumhead.next = new ListNode(sum);
            sumhead= sumhead.next;
        }
        if(carry!= 0){
            sumhead.next = new ListNode(carry);
        }
        return dummyhead.next;
    }
}
```
