## LeetCode Problem 8: String to Integer (atoi)

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/string-to-integer-atoi/](https://leetcode.com/problems/string-to-integer-atoi/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public int myAtoi(String s) {

        int i = 0; int sign = 1;
        int n = s.length();
        int result = 0;
        int digit = 0;

        while(i < n && s.charAt(i) == ' ' ) i++;
        if(i < n && (s.charAt(i) == '-' || s.charAt(i) == '+')){
            sign = s.charAt(i) == '-' ? -1 : 1;
            i++;
        }
        while(i < n && Character.isDigit(s.charAt(i) )){
            digit = s.charAt(i) - '0';

            if(result > (Integer.MAX_VALUE - digit) / 10){
                return sign == 1 ? Integer.MAX_VALUE : Integer.MIN_VALUE;
            }
            
            result = result * 10 + digit;
            i++;
        }
        return result * sign;
    }
}

