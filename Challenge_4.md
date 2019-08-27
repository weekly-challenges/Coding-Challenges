```
Challenge: 4

Integer to Roman

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

Write a program that accepts an integer and converts it into a roman characters.

Input: 3
Output: "III"

Input: 4
Output: "IV"

Input: 9
Output: "IX"

Input: 58
Output: "LVIII"
Explanation: L = 50, V = 5, III = 3.

Input: 1994
Output: "MCMXCIV"
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.

#coding  #challenge #easy
```

Solution Attempt #1: (In Java)
```java
public class ProblemFour {

	public static void main(String[] args) {
		char roman[] = { 'I', 'V', 'X', 'L', 'C', 'D', 'M' };
		int romanInt[] = { 1, 5, 10, 50, 100, 500, 1000 };
		HashMap<Integer, Character> hm = new HashMap<Integer, Character>();
		hm.put(1, 'I');
		hm.put(5, 'V');
		hm.put(10, 'X');
		hm.put(50, 'L');
		hm.put(100, 'C');
		hm.put(500, 'D');
		hm.put(1000, 'M');
		
		int num = 1994;
		List<Integer> romanInts = new ArrayList<Integer>();
		List<Integer> romanIntDivs = new ArrayList<Integer>();
		while (num > 0) {
			for (int i = romanInt.length - 1; i >= 0; i--) {
				int div = num / romanInt[i];
				if (div > 0) {
					romanInts.add(romanInt[i]);
					romanIntDivs.add(div);
					num = num % romanInt[i];
				}
			}
		}
		System.out.println(Arrays.toString(romanInts.toArray()));
		System.out.println(Arrays.toString(romanIntDivs.toArray()));
		String letters = "";
		for (int i = 0; i < romanInts.size(); i++) {
			if (romanIntDivs.get(i) == 4) {
				int index = getIndexOf(romanInt,romanInts.get(i));
				letters += hm.get(romanInts.get(i)).toString();
				letters += hm.get(romanInt[index+1]).toString();
			} else {
				for (int j = 0; j < romanIntDivs.get(i); j++) {
					letters += hm.get(romanInts.get(i)).toString();
				}
			}
		}
		System.out.println(letters);

	}
	
	static int getIndexOf(int[] arr, int n) {
		for(int i=0; i<arr.length; i++) {
			if(arr[i] == n) {
				return i;
			}
		}
		return -1;
	}
}
```
