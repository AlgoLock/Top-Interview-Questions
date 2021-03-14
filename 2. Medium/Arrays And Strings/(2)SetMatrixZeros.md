**Problem 2 in Top Interview Questions (medium)**

 Leetcode Problem 73: Set Matrix Zeros

Problem Link: https://leetcode.com/problems/set-matrix-zeroes/

Explanation: https://www.youtube.com/watch?v=rZ6IhefcrTo&t=20s&ab_channel=CodeBrosIO



 Java Solution: In Place
   n = # rows in matrix
   m = # columns in matrix
   Space: O(1)
   Time: O(nxm)

```java
class Solution {
    public void setZeroes(int[][] matrix) {
        
        boolean firstRowHasZero = false;
        boolean firstColHasZero = false;
        
        if(matrix.length == 0){ return; }
        
        for(int r = 0; r < matrix.length; r++){
          for(int c = 0; c < matrix[0].length; c++){
             if(r == 0 && matrix[r][c] == 0){
                 firstRowHasZero = true;
             } 
             if(c == 0 && matrix[r][c] == 0){
                 firstColHasZero = true;
             } 
             if(r!= 0 && c!=0 && matrix[r][c] == 0){
                 matrix[0][c] = 0;
                 matrix[r][0] = 0;
             }
        }      
        }
        
        for(int r = 1; r < matrix.length; r++){
            if(matrix[r][0] == 0){
                for(int c = 0; c < matrix[r].length; c++){ matrix[r][c] = 0;}
            }
        }
        for(int c = 1; c < matrix[0].length; c++){
            if(matrix[0][c] == 0){
                for(int r = 0; r < matrix.length; r++){ matrix[r][c] = 0;}
            }
        }
        
        if(firstRowHasZero){
            for(int c = 0; c < matrix[0].length; c++){ matrix[0][c] = 0;}
        }
        
        if(firstColHasZero){
            for(int r = 0; r < matrix.length; r++){ matrix[r][0] = 0;}
        } 
    }
}
```
