```
Challenge: 33

Given an array arr, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Example:
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]

#coding #challenge #easy
```

Solution Attempt: #1(In Java)
```java
import java.util.Arrays;

public class ProblemThreeThree {

	public static void main(String[] args) {
		int[] arr = {0,1,0,3,12};
		int[] newarr = new int[arr.length];
		
		int count = 0;
		for(int i=0; i<arr.length; i++) {
			if(arr[i] != 0) {
				newarr[count] = arr[i];
				count++;
			}
		}
		
		System.out.println(Arrays.toString(newarr));
	}
}
```
