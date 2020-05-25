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
