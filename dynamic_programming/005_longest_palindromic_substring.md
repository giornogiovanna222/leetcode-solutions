## LeetCode Problem 5: Longest Palindromic Substring

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/longest-palindromic-substring/](https://leetcode.com/problems/longest-palindromic-substring/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public String longestPalindrome(String s) {

        String longestpal = s.substring(0,1);
        String candidate;

        if(s.length() <= 1){
            return s;
        }

        // tek poli xayax gibi
        for(int i = 0; i<s.length();i++){
            for(int j = 0;(i-j)>=0 && (i+j)<s.length();j++){
                if(s.charAt(i-j) != s.charAt(i+j)) break;
                    candidate = s.substring(i - j, i + j + 1);
                    if(candidate.length() > longestpal.length()){
                            longestpal = candidate;
                        }
                }
            }

        // çift poli abba gibi abbt gibi "bb" gelir.
        for(int i = 0; i <s.length() - 1; i++ ){
            if(s.charAt(i) == s.charAt(i+1)){
                for(int j = 0; (i-j) >= 0 && (i+j+1) < s.length()  ; j++){
                    if(s.charAt(i-j) != s.charAt(i+j+1)) break;
                        candidate = s.substring(i-j, i+j+2);
                        if(candidate.length() > longestpal.length()){
                            longestpal = candidate;
                        }
                    }
                } 
        }  
        return longestpal;
    }
}

