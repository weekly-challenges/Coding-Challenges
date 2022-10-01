```
Challenge: 38

Given an integer, find the next permutation of it in absolute order. 

For example, given 48975, the next permutation would be 49578.

#coding #challenge #easy
```


Java Solution

```java
public void reverse(int nums[] , int start , int last)
    {
        while(start<last)
        {
            int temp = nums[start];
            nums[start] = nums[last];
            nums[last] = temp;
            start++;
            last--;
        }
    }
    
    public void nextPermutation(int[] nums) {
        
        int index = -1;
        for(int i=nums.length-1; i>=1; i--)
        {
            if(nums[i-1]<nums[i])
            {
                index = i-1;
                break;
            } 
        }
        
        if(index != -1)
        {
            for(int i=nums.length-1; i>=0; i--)
            {
                if(nums[index]<nums[i])
                {
                    int temp = nums[index];
                    nums[index] = nums[i];
                    nums[i] = temp;
                    break;
                } 
            }
        }
        
        
        reverse(nums,index+1,nums.length-1);
        
    }
```

Reference Links: https://leetcode.com/problems/next-permutation/discuss/2619160/Simple-Java-Solution
