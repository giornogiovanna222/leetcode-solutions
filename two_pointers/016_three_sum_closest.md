## LeetCode Problem 16: 3Sum Closest

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/3sum-closest/](https://leetcode.com/problems/3sum-closest/)

---

### ✅ My Solution (Java)

```java
class Solution {
    public int threeSumClosest(int[] nums, int target) {

        Arrays.sort(nums);

        int left, right;
        int closestsum = 0;
        int mindistance = Integer.MAX_VALUE;

        for (int i = 0; i < nums.length - 2; i++) {
            left = i + 1;
            right = nums.length - 1;

            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];
                int distance = Math.abs(sum - target);

                if (distance < mindistance) {
                    mindistance = distance;
                    closestsum = sum;
                    if (distance == 0) return closestsum;
                }
                if (sum < target) {
                    left++;
                } else {
                    right--;
                }
            }
        }
        return closestsum;
    }
}
