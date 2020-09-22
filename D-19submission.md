# :japanese_goblin: Question-Sequential Digits

> An integer has sequential digits if and only if each digit in the number is one more than the previous digit.  
> Return a sorted list of all the integers in the range [low, high] inclusive that have sequential digits.  
>   
> Example 1:  
> Input: low = 100, high = 300  
> Output: [123,234]  
> Example 2:  
> Input: low = 1000, high = 13000  
> Output: [1234,2345,3456,4567,5678,6789,12345]  

# :bento: Solution

```
class Solution {
    public List<Integer> sequentialDigits(int low, int high) {
        String s = "123456789";
        List<Integer> ans = new ArrayList();
        for(int i = 2; i < 10; ++i) {
            for(int j = 0; i + j < 10; ++j) {
                int t = Integer.parseInt(s.substring(j, i + j));
                if(t >= low) {
                    if(t <= high) {
                        ans.add(t);
                    } else {
                        return ans;
                    }
                }
            }
        }
        return ans;
    }
}
```
