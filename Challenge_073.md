```
Challenge: 73

Given the head of a singly linked list, reverse it in-place.

1 -> 2 -> 3

3 -> 2 -> 1

#coding #challenge #easy
```


Proposed Solution #1

```java

    public static void reverse(){
        LinkedList<Integer> linkedList = new LinkedList<>();

        linkedList.add(1);
        linkedList.add(2);
        linkedList.add(3);

        Stack<Integer> stack = new Stack<>();

        for(Integer i: linkedList){
            stack.push(i);
        }

        LinkedList<Integer> reverseLinkedList = new LinkedList<>();

        while(!stack.empty()){
            reverseLinkedList.add(stack.pop());
        }
    }

```

Proposed Solution #2 (Without using any extra storage hence Time O(n) and Space O(1))

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
    public ListNode reverseList(ListNode head) {
        // Pick 2 then change pointer of 2 i.e 3 to 1
        // and then take the 3 to current pick
        if(head == null || head.next == null){
            return head;
        }
        ListNode first = head;//1
        ListNode second = first.next;//2
        while(second != null){
            ListNode tmp = second.next; //3
            second.next = first; //2 is point to 1 now
            first = second; //shifting pointer to right
            second = tmp; //shifting pointer to right
        }
        head.next = null;
        head = first;   
        return head;
    }
}
```
