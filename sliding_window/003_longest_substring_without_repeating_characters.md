## LeetCode Problem 3: Longest Substring Without Repeating Characters

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/longest-substring-without-repeating-characters/](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

---

### ✅ My Solution (Java)
```java
import java.util.ArrayList;

class Solution {
    public int lengthOfLongestSubstring(String s) {
        ArrayList<Character> list = new ArrayList<>();
        int count = 0; 
        int maxCount = 0;

        for(int i = 0; i< s.length(); i++){
            char currentChar = s.charAt(i);

        if(list.contains(currentChar)){
            while(list.contains(currentChar)){
                list.remove(0);
                count--;
            }
        }
        list.add(currentChar);
        count++;
        maxCount = Math.max(maxCount, count);
        }

       return maxCount;
    }
}

