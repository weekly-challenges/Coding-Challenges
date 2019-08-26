```
Challenge: 1

Given a list of numbers and a number k, return whether any two numbers from the list add up to k. For example, given [10, 15, 3, 7] and k of 17, return true since 10 + 7 is 17. Can you do this in one pass?

#coding #challange #easy
```

Solution Attempt #1: (In Java)

```java
import java.util.HashMap;

public class ProblemOne {

	public static void main(String[] args) {
		int[] arr = {10, 15, 3, 7};
		int k = 10;
		
		HashMap<Integer, String> map = new HashMap<Integer, String>();
		
		for(int i=0; i<arr.length; i++) {
			if(map.get(arr[i]) != null) {
				System.out.println("Pair Found:"+map.get(arr[i]));
			}
			map.put(k-arr[i],""+arr[i]+" + "+(k-arr[i]));
		}

	}

}
```
