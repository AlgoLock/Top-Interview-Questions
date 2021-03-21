**Problem 1 in Top Interview Questions (medium): Arrays and Strings**

Leetcode Problem 15: 3Sum

Problem Link:  https://leetcode.com/problems/3sum/

Explanation: https://www.youtube.com/watch?v=Gj0BJ7OEYPY&t=7s&ab_channel=CodeBrosIO



 Java Solution: Left Right Pointer Method: 
     n = # elements in array
     Space: O(1)
     Time: O(n^2):

```java
 class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        
        Arrays.sort(nums);
        List<List<Integer>> outputArr = new ArrayList();
        int len = nums.length;
        
        int left,right,sum;
        
        for(int curr = 0; curr < len-2; curr++){
            
            if(curr == 0 || nums[curr-1] != nums[curr]){
                
                left = curr+1;
                right = len-1;
                
                while(left < right){
                    sum = nums[curr] + nums[left]+ nums[right];
                    if(sum == 0){
                        List<Integer> triplet = Arrays.asList(nums[curr], nums[left], nums[right]);
                        outputArr.add(triplet);
                        while(left < right && nums[left+1] == nums[left]){ left++; }
                        while(left < right && nums[right-1] == nums[right]){ right--; }
                        left++;
                        right--;
                    }else if (sum < 0){
                        left++;
                    }else if (sum > 0){
                        right--;
                    }
                    
                }
            }
        }
        return outputArr;
    }
}
```
