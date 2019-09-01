```
Challenge: 2

Given an even number ( greater than 2 ), return two prime numbers whose sum will be equal to given number.

NOTE A solution will always exist. read Goldbach’s conjecture

Example: Input : 4 Output: 2 + 2 = 4

If there are more than one solutions possible, return the lexicographically smaller solution.

If [a, b] is one solution with a <= b, and [c,d] is another solution with c <= d, then

[a, b] < [c, d]

If a < c OR a==c AND b < d.

#coding #challange #easy
```

Solution Attempt: #2(In Java)

```java
import java.math.BigInteger;

public class ProblemTwo {

	public static void main(String[] args) {
		int n = 17;

		BigInteger left = new BigInteger((n / 2) + "");
		BigInteger right = new BigInteger((n % 2) + "").add(left);

		while (!left.isProbablePrime(1) || !right.isProbablePrime(1)) {
			System.out.println(left);
			System.out.println(right);
			if (left.compareTo(right) > 0) {
				left = left.subtract(BigInteger.ONE);
				right = right.add(BigInteger.ONE);
			} else {
				left = left.add(BigInteger.ONE);
				right = right.subtract(BigInteger.ONE);
			}

		}

		System.out.println(left);
		System.out.println(right);
	}
}
```
