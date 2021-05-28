```
Challenge: 91

Given two rectangles on a 2D graph, return the area of their intersection. If the rectangles don't intersect, return 0.

For example, given the following rectangles:
{
    "top_left": (1, 4),
    "dimensions": (3, 3) # width, height
}
and
{
    "top_left": (0, 5),
    "dimensions": (4, 3) # width, height
}
return 6.

#coding #challenge #easy
```

Solution Attempt #1: (In Java)

```java
// Java program to find total area of two  
// overlapping Rectangles 
class GFG 
{ 
  
static class Point 
{ 
    int x, y; 
  
    public Point(int x, int y)  
    { 
        this.x = x; 
        this.y = y; 
    } 
}; 
  
// Returns Total Area of two overlap  
// rectangles 
static int overlappingArea(Point l1, Point r1, 
                           Point l2, Point r2) 
{ 
    // Area of 1st Rectangle 
    int area1 = Math.abs(l1.x - r1.x) * 
                Math.abs(l1.y - r1.y); 
  
    // Area of 2nd Rectangle 
    int area2 = Math.abs(l2.x - r2.x) * 
                Math.abs(l2.y - r2.y); 
  
    // Length of intersecting part i.e  
    // start from max(l1.x, l2.x) of  
    // x-coordinate and end at min(r1.x, 
    // r2.x) x-coordinate by subtracting  
    // start from end we get required  
    // lengths 
    int areaI = (Math.min(r1.x, r2.x) -  
                 Math.max(l1.x, l2.x)) *  
                (Math.min(r1.y, r2.y) - 
                 Math.max(l1.y, l2.y)); 
  
    return (area1 + area2 - areaI); 
} 
  
// Driver Code 
public static void main(String[] args)  
{ 
    Point l1 = new Point( 2, 2 ),  
          r1 = new Point( 5, 7 ); 
    Point l2 = new Point( 3, 4 ),  
          r2 = new Point( 6, 9 ); 
    System.out.println(overlappingArea(l1, r1, l2, r2)); 
} 
} 
```
