## LeetCode Problem 12: Integer to Roman

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/integer-to-roman/](https://leetcode.com/problems/integer-to-roman/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public String intToRoman(int num) {

        StringBuilder S = new StringBuilder();

        while( num >= 1000){
            S.append("M");
            num = num - 1000;
        }
        if(num > 899 && num <1000){
            S.append("CM");
            num = num - 900;
        }
        if(num > 399 && num < 500){
            S.append("CD");
            num = num - 400;
        }
        if ( num >= 500 ){
            S.append("D");
            num = num - 500;
        }
        while( num >= 100 && num < 400){
            S.append("C");
            num = num - 100;
        }
        if(num > 39 && num < 50){
            S.append("XL");
            num = num - 40;
        }
        if(num > 89 && num < 100){
            S.append("XC");
            num = num - 90;
        } 
        while(num >= 50){
            S.append("L");
            num = num - 50;
        }
        while(num >= 10){
            S.append("X");
            num = num - 10;
        }
        if( num == 4){
            S.append("IV");
            num = num - 4;
        }
        if(num == 9){
            S.append("IX");
            num = num - 9;
        }
        if ( num >= 5){
            S.append("V");
            num = num - 5;
        }
        while( num >= 1){
            S.append("I");
            num = num - 1;
        }

        String sb = S.toString();

        return sb;  
    }
}

