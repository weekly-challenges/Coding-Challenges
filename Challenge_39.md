```
Challenge: 39

Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand. Find the minimum element in O(log N) time. You may assume the array does not contain duplicates.

For example, given [5, 7, 10, 3, 4], return 3.

#coding #challenge #hard
```

Java Sol:

```java
public class RotateDelta {
	public static void main(String[] args) {
		int[] input  = new int[] {5, 7, 10, 3, 4};
		int soFarMin = input[0];
		int index = 0;
		for(int i=1; i<input.length; i++) {
			if(input[i] < soFarMin) {
				soFarMin = input[i];
				index = i;
			}
		}
		System.out.println(index);
	}
}
//The above can be enchaced with binary search algorithm
```
