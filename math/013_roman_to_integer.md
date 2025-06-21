## LeetCode Problem 13: Roman to Integer

**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/roman-to-integer/](https://leetcode.com/problems/roman-to-integer/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public int romanToInt(String s) {

        int num = 0;

        for(int i = 0 ; i < s.length() ; i++){
            
            if(i != (s.length() - 1) && s.charAt(i) == 'C' && s.charAt(i+1) == 'D'){
                num = num + 400;
                i++;
            }
            else if(i != (s.length() - 1) && s.charAt(i) == 'C' && s.charAt(i+1) == 'M' ){
                num = num + 900;
                i++;
            }
            else if(i != (s.length() - 1) && s.charAt(i) == 'X' && s.charAt(i+1) == 'L'){
                num = num + 40;
                i++;
            }
            else if(i != (s.length() - 1) && s.charAt(i) == 'X' && s.charAt(i+1) == 'C' ){
                num = num + 90;
                i++;
            }
            else if( i != (s.length() - 1) && s.charAt(i) == 'I' && s.charAt(i+1) == 'V' ){
                num = num + 4;
                i++;
            }
            else if(i != (s.length() - 1) && s.charAt(i) == 'I' && s.charAt(i+1) == 'X'){
                num = num + 9;
                i++;
            }else{
                if(s.charAt(i) == 'I'){
                    num = num + 1;
                }
                if(s.charAt(i) == 'V'){
                    num = num + 5;
                }
                if(s.charAt(i) == 'X'){
                    num = num + 10;
                }
                if(s.charAt(i) == 'L'){
                    num = num + 50;
                }
                if(s.charAt(i) == 'C'){
                    num = num + 100;
                }
                if(s.charAt(i) == 'D'){
                    num = num + 500;
                }
                if(s.charAt(i) == 'M'){
                    num = num + 1000;
                }
            }
        }
        return num;
    }
}

