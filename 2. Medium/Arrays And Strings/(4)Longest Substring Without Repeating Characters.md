

Problem 4 in Top Interview Questions (medium)

 Leetcode Problem 3: Longest Substring Without Repeating Characters
     
 Java Solution: 
    n = number of characters in string
    
Time and Space Complexity
    => Space: O(n)
    => Time: O(n)
    
```java
class Solution {
    public int lengthOfLongestSubstring(String s) {

        HashSet<Character> seen = new HashSet<Character>();
        int sow =0, eow =0, maxlen = 0;
        char [] carr = s.toCharArray();
        int len = carr.length;
        
        while(eow < len){
            while(seen.contains(carr[eow])){
                //dupicate seen at carr[eow]
                seen.remove(carr[sow]);
                sow++;
            }
            while(eow < len && !seen.contains(carr[eow])){
                //unique value seen at carr[eow]
                seen.add(carr[eow]);
                eow++;
                maxlen = Math.max(maxlen, seen.size());
            }
        }
        return maxlen;
    }
}
```
