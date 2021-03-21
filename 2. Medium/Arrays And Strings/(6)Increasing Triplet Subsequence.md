**Problem 6 in Top Interview Questions (medium)**

 Leetcode Problem 334: Increasing Triplet Subsequence

Problem Link:  https://leetcode.com/problems/increasing-triplet-subsequence/

Explanation: https://www.youtube.com/watch?v=rHeA_insRro&list=PLvRP22vSRCvIQfawmmsBvcrR9d90YfSJi&index=6&ab_channel=CodeBrosIO



 Java Solution: 
    n = number of integers in array
    
Time and Space Complexity
    => Space: O(1)
    => Time: O(n)

```java
 class Solution {
    public boolean increasingTriplet(int[] nums) {
        
        int min=-1, mid=-1;
        
        for(int curr = 0; curr < nums.length; curr++){   
            if(min == -1 || nums[curr] < nums[min]){
                min = curr;
            }
            else if(nums[curr] > nums[min] && (mid == -1 ||  nums[curr] < nums[mid])){
                mid = curr;
            }else if(mid != -1 && nums[curr] > nums[mid]){
                return true;
            }
        }
        return false;
    }
}

```
