Challenge: 174

Longest Consecutive Run of 1s in Binary.

Given a non-negative integer `n`, return the length of the longest consecutive run of `1`s in its binary representation.

Contrainsts: `0 ≤ n < 2 ^ 31`

Example:
Input: 156
Output: 3
Explanation: 10011100

#coding #challenge #easy #udemy

Udemy: https://nlbsg.udemy.com/course/competitive-programming-algorithms-coding-minutes/learn/quiz/5323488


Solution Attempt #1: (In Java):

```java
    public static int longest_consecutive_run_1s(int n){
      int max = 0;
      int current_count = 0;

      while(n>0){
        int last_bit = n&1;
        if(last_bit == 1){
            current_count++;
        } else {
          if(max < current_count){
            max = current_count;
          }
          current_count = 0;
        }
        n = n >> 1;
      }
      return max;
   }
```
