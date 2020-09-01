# :japanese_goblin: Question-Largest Time for Given Digits

> Given an array of 4 digits, return the largest 24 hour time that can be made.  
> The smallest 24 hour time is 00:00, and the largest is 23:59.  Starting from 00:00, a time is larger if more time has elapsed since midnight.  
> Return the answer as a string of length 5.  If no valid time can be made, return an empty string.  
> Example 1:  
> nput: [1,2,3,4]  
> Output: "23:41"  
> Example 2:  
> Input: [5,5,5,5]  
> Output: ""  
> Note:  
> A.length == 4  
> 0 <= A[i] <= 9  

# :bento: Solution

```

class Solution {
    public String largestTimeFromDigits(int[] arr) {
        int i,j,k,l;
        String res="",hr,time,min;
        for(i=0;i<4;i++){
            for(j=0;j<4;j++){
                for(k=0;k<4;k++){
                    if(i==j || j==k || k==i){
                        continue;
                    }
                    hr=""+arr[i]+arr[j];
                    min=""+arr[k]+arr[6-i-j-k];
                    time=hr+":"+min;
                    if(hr.compareTo("24")<0 && min.compareTo("60")<0 && res.compareTo(time)<0){
                        res=time;
                    }
                }
            }
        }
          return res;
    }
  
}
```
