## LeetCode Problem 11: Container With Most Water

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/container-with-most-water/](https://leetcode.com/problems/container-with-most-water/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public int maxArea(int[] height) {

        int L = height.length;
        int maxarea = 0;
        int candidate;
        int i = 0;
        int j = L-1;

        while(i<j){
            candidate = (j-i) * (height[j] <= height[i] ? height[j] : height[i]);
            if(candidate > maxarea){
                maxarea = candidate;
            }
            if(height[i] < height[j]){
                i++;
            }
            else{
                j--;
            }
        }
        return maxarea;  
    }
}

