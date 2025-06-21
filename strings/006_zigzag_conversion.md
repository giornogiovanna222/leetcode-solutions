## LeetCode Problem 6: Zigzag Conversion

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/zigzag-conversion/](https://leetcode.com/problems/zigzag-conversion/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public String convert(String s, int numRows) {

        char [][] matris = new char[numRows][s.length()];

        if(numRows == 1 || s.length() <= 1){
            return s;
        }
        int row = 0;
        int column = 0;
        String mode = "down";
        int zigzagcounter = 0;
        String result = "";

        for(int k = 0; k< s.length() ; k++){

            matris[row][column] = s.charAt(k);

                if(mode.equals("down")){
                    row++;  
                if((row == numRows -1 )){
                    mode = "zigzag";
                    zigzagcounter = numRows-1;   
                }
                }
                else if(mode.equals("zigzag")){
                    row--;
                    column++;
                    zigzagcounter--;
                    if(zigzagcounter == 0){
                        mode = "down";
                    }
                }
        }
        for(int i = 0;i<numRows;i++){
            for(int j = 0; j < s.length(); j++){
                if(matris[i][j] != 0){
                result += matris[i][j];
                }
            }
        }
        return result;
    }
}

