```
Challenge: 10

Design an algorithm and write code to remove the duplicate characters in a string.

Follow Up:  Can you write the algorithm without using any additional buffer NOTE: One or two additional variables are fine, an extra copy of the array is not.

Follow Up: What are the ways would you test the above-written algorithm.

#coding #challenge #easy
```

Solution Attempt: #1 (In Java)
```java
public class ProblemTen {

	public static void main(String[] args) {
		String s = "OKOKOK";
		
		String updatedS = "";
		
		for(int i=0; i<s.length(); i++) {
			if(updatedS.indexOf(s.charAt(i)) == -1) {
				updatedS += s.charAt(i);
			}
		}
		
		System.out.println(updatedS);
	}
}
```
