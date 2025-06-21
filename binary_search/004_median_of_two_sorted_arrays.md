## LeetCode Problem 4: Median of Two Sorted Arrays

**Difficulty:** Hard  
**Link:** [https://leetcode.com/problems/median-of-two-sorted-arrays/](https://leetcode.com/problems/median-of-two-sorted-arrays/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {

        int[] nums3 = new int[nums1.length + nums2.length];

        double m = 0;
        int z = nums1.length;
        int zz = nums2.length;

        if(z == 1 && zz == 0){
            return nums1[0];
        }
        if(z == 0){
            for(int i = 0; i<nums2.length;i++){
            nums3[i] = nums2[i];
            }

            if(z == 0 && zz == 1){
                return nums2[0];
            }

            if(nums3.length % 2 == 1){
                 m = nums3[zz/2];
            }
            else{
                 m = (nums3[zz/2] + nums3[(zz/2) - 1]) / 2.0;
            }
        }
        else{
            if(nums1.length > 0){
            for(int i = 0; i<nums1.length;i++){
            nums3[i] = nums1[i];
            }
        }
        if(nums2.length > 0){
            for(int i = 0; i<nums2.length;i++){
            nums3[z+i] = nums2[i];
            }
        }
        }

        int zt = nums1.length + nums2.length;

        int temp;

        for(int i = 0; i< zt - 1; i++){
            for(int j = 0; j< zt - i - 1; j++){
               if(nums3[j] > nums3[j+1]){
                temp = nums3[j];
                nums3[j] = nums3[j+1];
                nums3[j+1] = temp; 
               }
            }
        }

        double max = 0;
        
        if(zt>1){
            double a = (nums3[zt/2]);
            double b = (nums3[zt/2] + nums3[(zt/2)-1]) / 2.0;

        if(z == 0){
            max = m;
        }
        else if(zt == 1){
            max = nums3[0];
        }
        else{
            if(zt%2 == 1){
            max = a;
        }
            if(zt%2 == 0){
            max = b;
        }
        }
        }
    return max;   
    }
}

