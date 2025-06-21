## LeetCode Problem 1: Two Sum

**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/two-sum/](https://leetcode.com/problems/two-sum/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        int [] nums2 = new int[2];

        for(int i=0; i<(nums.length)-1; i++){
            for(int j = i+1; j< (nums.length);j++){

                if((nums[i] + nums[j]) == target){
                    nums2[0] = i;
                    nums2[1] = j;
                } 
            }
        }
    return nums2;
    }
}

