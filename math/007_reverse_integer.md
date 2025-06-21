## LeetCode Problem 7: Reverse Integer

**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/reverse-integer/](https://leetcode.com/problems/reverse-integer/)

---

### ✅ My Solution (Java)
```java
class Solution {
    public int reverse(int x) {

        int result = 0;
        int basamak = 0;
        boolean negatif = false;
        String s  = Integer.toString(x);

        if(x<0){
            s = s.substring(1);
        }

        ArrayList<Integer> list = new ArrayList<>();

        for(int i = 0; i<s.length(); i++){
            list.add(s.charAt(i) - '0');
        }
        
        for(int i = 0 ; i<list.size() ; i++){
            if(list.get(i) != 0){
                basamak = (int)(Math.pow(10,i)) * list.get(i);
                if(basamak / (int)(Math.pow(10,i)) != list.get(i)) return 0;
                if(result > (Integer.MAX_VALUE) - basamak) return 0;
                result += basamak;
            }
        }
       
       if(x<0){
        negatif = true;
       }
       return negatif ? -result : result;
    }
}

