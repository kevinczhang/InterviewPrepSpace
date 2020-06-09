# Largest Number

Given a list of non negative integers, arrange them such that they form the largest number.

#### Example

Given \[1, 20, 23, 4, 8\], the largest formed number is 8423201.

```java
public class Solution {
    /**
     *@param num: A list of non negative integers
     *@return: A string
     */
    public String largestNumber(int[] num) {
        String[] numStrings = new String[num.length];
        for (int i = 0; i < num.length; i++){
            numStrings[i] = String.valueOf(num[i]); 
            Arrays.sort(numStrings, NumberComparator);
        
            StringBuilder res = new StringBuilder();
            for(String n : numStrings) res.append(n);
            return res.charAt(0) == '0' ? "0" : res.toString();
        }
    
        Comparator<String> NumberComparator = new Comparator<String>(){
            public int compare(String num1, String num2){
                int cur = 0;
                while(cur < num1.length() && cur < num2.length()){
                    if(num1.charAt(cur) == num2.charAt(cur))
                        cur++;
                    else
                        return num2.charAt(cur) - num1.charAt(cur);
                }
                if(cur < num1.length()) return compare(num1.substring(cur), num2);
                if(cur < num2.length()) return compare(num1, num2.substring(cur));
                return 0;
           }
        };
    }
}

```



