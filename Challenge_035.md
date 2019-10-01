```
Challenge: 35

Given an array of integers, return a new array where each element in the new array is the number of smaller elements to the right of that element in the original input array.

For example, given the array [3, 4, 9, 6, 1], return [1, 1, 2, 1, 0], since:

There is 1 smaller element to the right of 3
There is 1 smaller element to the right of 4
There are 2 smaller elements to the right of 9
There is 1 smaller element to the right of 6
There are no smaller elements to the right of 1

#coding #challenge #easy
```

Solution Attempt: #1
```java
import java.util.Arrays;

public class Solution {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int[] arr = {3, 4, 9, 6, 1};
		
		int[] returnArr = new int[arr.length];
		
		for(int i=0; i<arr.length; i++) {
			int currEl = arr[i];
			int count = 0;
			for(int j=i+1; j<arr.length; j++) {
				if(arr[j] < currEl) {
					count++;
				}
			}
			returnArr[i] = count;
		}
		
		System.out.println(Arrays.toString(returnArr));
	}

}

```
