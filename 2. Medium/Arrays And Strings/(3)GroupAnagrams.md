**Problem 3 in Top Interview Questions (medium)**

Leetcode Problem 49: Group Anagrams

Problem Link: https://leetcode.com/problems/group-anagrams/

Explanation: https://www.youtube.com/watch?v=TJm2sAyogbg&t=16s&ab_channel=CodeBrosIO




 Java Solution: 
    n = number of strings
    k = length of longest string 
    
Time and Space Complexity
    => Space: O(n)
    => Time: O(n*klogk)
    

```java
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        
        List<List<String>> GAreturnlist = new ArrayList<>();
        HashMap<String, List<String>> strmap = new HashMap<>();
        
        
        char [] tempchar;
        String sortedstr;
        for(int i =0; i<strs.length; i++){
            tempchar = strs[i].toCharArray();
            Arrays.sort(tempchar);
            sortedstr = new String(tempchar);
            
            if(strmap.containsKey(sortedstr)){
                // map has key sortedstr
                strmap.get(sortedstr).add(strs[i]);
            }else{
              // map doesnt has key sortedstr
              List<String> temp = new ArrayList<>();
              temp.add(strs[i]);
              strmap.put(sortedstr, temp);
            }
        }
        for(String key: strmap.keySet()){
            GAreturnlist.add(strmap.get(key));
        }
        return GAreturnlist;
    }
}
```
