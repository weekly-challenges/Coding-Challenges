```
Challenge: 173

Given two strings s and t, return true if they are equal when both are typed into empty text editors. '#' means a backspace character.

Note that after backspacing an empty text, the text will continue empty.

#coding #challenge #easy #leetcode

LeetCode: https://leetcode.com/problems/backspace-string-compare/ 
```

Solution Attempt #1: (In Java) Using Stack:

```java
    String s = "ab#c";
    String t = "ad#c";

    Stack<Character> stack = new Stack<>();

    for (char c : s.toCharArray()) {
      if (c == '#') {
        if (!stack.isEmpty()) {
          stack.pop();
        }

      } else {
        stack.push(c);
      }
    }

    Stack<Character> stackForT = new Stack<>();

    for (char c : t.toCharArray()) {
      if (c == '#') {
        if (!stackForT.isEmpty()) {
          stackForT.pop();
        }
      } else {
        stackForT.push(c);
      }
    }

    StringBuilder sBuilder = new StringBuilder();
    while (!stack.empty()) {
      sBuilder.append(stack.pop());
    }

    StringBuilder tBuilder = new StringBuilder();
    while (!stackForT.empty()) {
      tBuilder.append(stackForT.pop());
    }

    if (sBuilder.toString().equals(tBuilder.toString())) {
      System.out.println("They are equal!");
    } else {
      System.out.println("They are NOT equal!");
    }
```

Solution Attempt #2: (In Java) Using Pointer:

