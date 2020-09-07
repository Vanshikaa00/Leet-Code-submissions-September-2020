# :japanese_goblin: Question-Image Overlap

> Two images A and B are given, represented as binary, square matrices of the same size.  (A binary matrix has only 0s and 1s as values.)  
> We translate one image however we choose (sliding it left, right, up, or down any number of units), and place it on top of the other image.   
> After, the overlap of this translation is the number of positions that have a 1 in both images.  
> (Note also that a translation does not include any kind of rotation.)  
> What is the largest possible overlap?  
>      
> Example 1:  
> Input: A = [[1,1,0],  
>             [0,1,0],  
>             [0,1,0]]  
>        B = [[0,0,0],  
>             [0,1,1],  
>             [0,0,1]]  
> Output: 3  
> Explanation: We slide A to right by 1 unit and down by 1 unit.  
> Notes:   
> 1 <= A.length = A[0].length = B.length = B[0].length <= 30  
> 0 <= A[i][j], B[i][j] <= 1  

# :bento: Solution
```
class Solution {
    private int overlappedOnes(int[][] A,int[][] B,int ro,int co){
        int r,c,count=0;
        for(r=0;r<A.length;r++){
            for(c=0;c<A[0].length;c++){
                if((r+ro<0 || r+ro>=A.length)||(c+co<0 || c+co>=A[0].length))
                    continue;
                if(A[r][c]+B[r+ro][c+co]==2)
                    count++;
            }
        }
        return count;
    }
    public int largestOverlap(int[][] A, int[][] B) {
        int r,c,largestOnes=0;
        for(r=-A.length+1;r<A.length;r++){
            for(c=-A[0].length+1;c<A.length;c++){
                largestOnes=Math.max(largestOnes,overlappedOnes(A,B,r,c));
            }
        }
        return largestOnes;
    }
}

```
