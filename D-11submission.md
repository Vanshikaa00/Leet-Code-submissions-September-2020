# :japanese_goblin: Question-Product of Longest Subarray

> Given an integer array nums, find the contiguous subarray within an array (containing at least one number) which has the largest product.  
> Example 1:  
> Input: [2,3,-2,4]  
> Output: 6  
> Explanation: [2,3] has the largest product 6.  
> Example 2:  
>  Input: [-2,0,-1]  
>  Output: 0  
> Explanation: The result cannot be 2, because [-2,-1] is not a subarray.  


# :bento: Solution

```
class Solution {
    public int maxProduct(int[] nums) {
        if(nums.length==0)
            return 0;
        int prod,max=nums[0],l=nums.length,i,j;
        for(i=0;i<l;i++){
            prod=nums[i];
            for(j=i+1;j<l;j++){
                max=Math.max(prod,max);
                prod*=nums[j];
                if(prod==0)
                    break;
            }
            max=Math.max(max,prod);
        }
        return max;
    }
}
```