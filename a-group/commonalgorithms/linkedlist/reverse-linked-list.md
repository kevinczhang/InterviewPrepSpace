# Reverse Linked List

Example

For linked list 1-&gt;2-&gt;3, the reversed linked list is 3-&gt;2-&gt;1

```java
/**
 * Definition for ListNode.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int val) {
 *         this.val = val;
 *         this.next = null;
 *     }
 * }
 ***/ 
public class Solution {
    /**
     * @param head: The head of linked list.
     * @return: The new head of reversed linked list.
     */
    public ListNode reverse(ListNode head) {
        if(head == null || head.next == null) return head;
        
        ListNode fakeHead = new ListNode(-1);
        fakeHead.next = head;
        while(head.next != null){
            ListNode oldHead = fakeHead.next;
            ListNode newHead = head.next;
            fakeHead.next = newHead;
            head.next = newHead.next;
            newHead.next = oldHead;
        }
        return fakeHead.next;
    }
}

```

