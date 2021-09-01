## 75. Sort Colors || Sort an array of 0s, 1s and 2s
## https://practice.geeksforgeeks.org/problems/sort-an-array-of-0s-1s-and-2s4231/1#
## https://leetcode.com/problems/sort-colors/

### Approach 1: Sort the Array, TC: O(N logN)

### Approach 2: Counting Sort, TC: O(N)
> Count the number of 0’s, 1’s and 2’s. After Counting, put all 0’s first, then 1’s and lastly 2’s in the array. We traverse the array two times.
```java
class Solution
{
    public static void sort012(int a[], int n)
    {
        int c0 = 0, c1 = 0, c2 = 0;
        for(int ele: a)
        {
            if(ele == 0)
                c0++;
            else if(ele == 1)
                c1++;
            else
                c2++;
        }
        int index = 0;
        for(; index < c0; index++)
            a[index] = 0;
        for(; index < c0+c1; index++)
            a[index] = 1;
        for(; index < c0+c1+c2; index++)
            a[index] = 2;
    }
}
```