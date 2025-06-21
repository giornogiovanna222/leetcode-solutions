## LeetCode Problem 9: Palindrome Number

**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/palindrome-number/](https://leetcode.com/problems/palindrome-number/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public boolean isPalindrome(int x) {

        String s = Integer.toString(x);
        boolean ispal = true;

        for(int i = 0; i < s.length()/2 ; i++){
            if(s.charAt(i) != s.charAt(s.length() - 1 - i)){
                ispal = false;
                break;
            }     
        }
        return ispal; 
    }
}

