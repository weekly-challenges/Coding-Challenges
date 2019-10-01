```
Challenge: 34

Given a 32-bit integer, return the number with its bits reversed.

For example, 
given the binary number 1111 0000 1111 0000 1111 0000 1111 0000, 

return 0000 1111 0000 1111 0000 1111 0000 1111.

#coding #challenge #easy
```

```java
public class Solution {

	public static void main(String[] args) {
		String input = "1111 0000 1111 0000 1111 0000 1111 0000";
		
		String result = "";
		
		for(int i=0; i<input.length(); i++) {
			if(input.charAt(i)=='1') {
				result += "0";
			}
			else if(input.charAt(i)=='0') {
				result += "1";
			}
			else {
				result += input.charAt(i);
			}
		}
		
		System.out.println(result);

	}
}
```
