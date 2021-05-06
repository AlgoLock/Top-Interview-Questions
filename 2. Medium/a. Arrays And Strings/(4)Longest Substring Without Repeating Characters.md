**Problem 4 in Top Interview Questions (medium): Arrays and Strings**

 Leetcode Problem 3: Longest Substring Without Repeating Characters

Problem Link: https://leetcode.com/problems/longest-substring-without-repeating-characters/

Explanation: https://www.youtube.com/watch?v=ijIANdVFRR8&t=21s&ab_channel=CodeBrosIO




 Java Solution: 
    n = number of characters in string
    
Time and Space Complexity
    => Space: O(n)
    => Time: O(n)
    

```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
        
        HashMap<Character, Integer> seen = new HashMap<>();
        int sow = 0, eow = 0, maxlen =0;
        
        char [] carr = s.toCharArray();
        int len = carr.length;
        
        while(eow < len){
            //duplicate case
            if(seen.containsKey(carr[eow]) && seen.get(carr[eow]) >= sow){
                sow = seen.get(carr[eow])+1;
            }else{
                //unique character
                maxlen = Math.max(maxlen, eow-sow+1);
            }
            seen.put(carr[eow], eow);
             eow++;  
        }
        return maxlen;
    }
}
```
