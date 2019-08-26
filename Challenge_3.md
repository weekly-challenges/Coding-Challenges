```
Challenge: 3

Given an array of integers, return a new array such that each element at index i of the new array is the product of all the numbers in the original array except the one at i.

For example, if our input was [1, 2, 3, 4, 5], the expected output would be [120, 60, 40, 30, 24]. If our input was [3, 2, 1], the expected output would be [2, 3, 6].

Follow-up: what if you can’t use division?

#coding #challange #easy
```

Solution Attempt #1: (In Java)

```java
public class ProblemThree {

	public static void main(String[] args) {
		int arr[] = {1,2,3,4,5};
		int product = 1;
		for(int i=0; i<arr.length; i++) {
			product *= arr[i];
		}
		
		int revArr[] = new int[arr.length];
		for(int i=0; i<arr.length; i++) {
			//With Followup
			revArr[i] = withoutDivision(product,arr[i]);
			
			//Without Followup
			//revArr[i] = product/arr[i];
		}
		System.out.println(Arrays.toString(revArr));
	}
	
	//a/b
	public static int withoutDivision(int a, int b) {
		int count = 0;
		while(a > 0) {
			a = a - b;
			count++;
		}
		return count;
	}

}
```
