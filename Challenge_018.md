```
Challenge: 18

Write an algorithm that will print all the factors of given input N.

For example:
Input: 48
Output: 1, 2, 3, 4, 6, 8, 12, 16, 24, 48

#coding #challenge #easy
```

Solution Attempt: 
```java
import java.util.Scanner;

public class PrimeFactors {
   public static void main(String args[]){
      int number;
      Scanner sc = new Scanner(System.in);
      System.out.println("Enter a number ::");
      number = sc.nextInt();
      
      for(int i = 2; i< number; i++) {
         while(number%i == 0) {
            System.out.println(i+" ");
            number = number/i;
         }
      }
      if(number >2) {
         System.out.println(number);
      }
   }
}
```
