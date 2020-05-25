```
Challenge: 74

Given a real number n, find the square root of n. For example, given n = 9, return 3. 

You may not use in-built square root function provided by programming language library.

#coding #challenge #medium
```


Proposed Solution #1

```java
    public static int sqrt(int number){
        int current = 1;
        int count = 0;
        int sum = 1;
        while(sum <= number){
            current++;

            if(current % 2 != 0){
                sum += current;
                count++;
            }
        }
        return count;
    }
```
