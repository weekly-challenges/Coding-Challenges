Lilah has a string,`s` , of lowercase English letters that she repeated infinitely many times.

Given an integer,`n` , find and print the number of letter a's in the first  letters of Lilah's infinite string.

For example, if the string `s=abcac` and n=10, the substring we consider is `abcacabcac`, the first  characters of her infinite string. There are `4` occurrences of a in the substring.


Solution #1 (Java)

```java
// Complete the repeatedString function below.
    static long repeatedString(String s, long n) {
        if(s.length() == n){
            return find(s, n);
        } else {
            //Find 'a' for the S length only
            long res = find(s, s.length());
            //Find how many times is the string to be repeated
            long x1 = n / s.length();
            // multiply the single occurance to the repeated set
            long x2 = res * x1;
            // find the difference in case n is not a mutiple of s.length()
            long sub = n - (s.length()*x1);
            // calculate again for the difference
            long resagain = find(s, sub);
            // sum the initial calculation with the differece.
            return x2+resagain;
        }
    }
```

Sample Test Data
```
s = aba
n = 10

output = 7
```


```
s = a
n = 1000000000000

output = 1000000000000
```
