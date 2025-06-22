## LeetCode Problem 15: 3Sum

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/3sum/](https://leetcode.com/problems/3sum/)

---

### ✅ My Solution (Java)

```java
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {

        List<List<Integer>> result = new ArrayList<>();

        Arrays.sort(nums);
        int left, right;
        int length = nums.length;

        for (int i = 0; i < length - 2; i++) {
            if (nums[i] > 0) break;
            if (i > 0 && nums[i - 1] == nums[i]) continue;

            left = i + 1;
            right = length - 1;

            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];
                if (sum == 0) {
                    List<Integer> triple = new ArrayList<>();
                    triple.add(nums[i]);
                    triple.add(nums[left]);
                    triple.add(nums[right]);
                    result.add(triple);

                    while (left < right && nums[left] == nums[left + 1]) left++;
                    while (left < right && nums[right] == nums[right - 1]) right--;

                    left++;
                    right--;
                } else if (sum > 0) {
                    right--;
                } else {
                    left++;
                }
            }
        }
        return result;
    }
}
