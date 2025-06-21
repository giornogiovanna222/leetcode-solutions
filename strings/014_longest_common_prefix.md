## LeetCode Problem 14: Longest Common Prefix

**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/longest-common-prefix/](https://leetcode.com/problems/longest-common-prefix/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public String longestCommonPrefix(String[] strs) {

        if(strs.length <= 1){
            String kek = strs[0];
            return kek;
        }

        String s1 = strs[0];
        String temp;
        int count = 200;
        int mincount = 0;
        int len1 = s1.length();

        for(int i = 1 ; i < strs.length; i++){

            temp = strs[i];

            int len2 = temp.length();

            int len3 = len1 > len2 ? len2 : len1;

            for(int j = 0; j< len3; j++){
                
            if(temp.charAt(j) != s1.charAt(j)) break;
            
            mincount++;

            } 
            count = Math.min(count,mincount);
            mincount = 0;    
        }
        StringBuilder sd = new StringBuilder();
        for(int i = 0 ; i < count;i++){
            sd.append(s1.charAt(i));
        }
        String sdd = sd.toString();
        return sdd;
    }
}

