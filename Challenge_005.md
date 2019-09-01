```
Challenge: 5

Given a list of integers and a number K, return which contiguous elements of the list sum to K.

For example, if the list is [1, 2, 3, 4, 5] and K is 9, then it should return [2, 3, 4].

#coding  #challenge #easy
```

Solution Attempt: #1
```java
public class ProblemFive {

	public static void main(String[] args) {
		int arr[] = { 1, 2, 3, 4, 5 };
		int k = 9;

		int since = 0;
		List<Integer> sinceThen = new ArrayList<Integer>();

		first:
		for (int i = 0; i < arr.length; i++) {
			since = arr[i];
			sinceThen = new ArrayList<Integer>();
			sinceThen.add(arr[i]);
			for (int j = i + 1; j < arr.length - 1; j++) {
				if ((since + arr[j]) == k) {
					since += arr[j];
					sinceThen.add(arr[j]);
					break first;
				} else if ((since + arr[j]) > k) {
					since = 0;
					sinceThen = new ArrayList<Integer>();
				} else if ((since + arr[j]) < k) {
					since += arr[j];
					sinceThen.add(arr[j]);
				}
			}
		}
		if(since == k)
			System.out.println(Arrays.toString(sinceThen.toArray()));
		else 
			System.out.println("No solution found");
	}
}
```
