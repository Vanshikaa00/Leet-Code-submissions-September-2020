# :japanese_goblin: Question-Partition Labels

> A string S of lowercase English letters is given. We want to partition this string into as many parts as possible so that each letter   
> appears in at most one part, and return a list of integers representing the size of these parts.  
> Example 1:  
> Input: S = "ababcbacadefegdehijhklij"  
> Output: [9,7,8]  
> Explanation:  
> The partition is "ababcbaca", "defegde", "hijhklij".  
> This is a partition so that each letter appears in at most one part.  
> A partition like "ababcbacadefegde", "hijhklij" is incorrect, because it splits S into less parts.  
> Note:  
> S will have length in range [1, 500].  
> S will consist of lowercase English letters ('a' to 'z') only.  


# :bento: Solution

```
class Solution {
    public List<Integer> partitionLabels(String S) {
        List <Integer> ans=new ArrayList<>();
        int[] lastindex=new int[26];
        int i,j,end;
        for(i=0;i<S.length();i++){
            lastindex[S.charAt(i)-'a']=i;
        }
        i=0;
        while(i<S.length()){
            end=lastindex[S.charAt(i)-'a'];
            j=i;
            while(j!=end){
                end=Math.max(end,lastindex[S.charAt(j++)-'a']);
            }
            ans.add(j-i+1);
            i=j+1;
        }
        return ans;
    }
}
```
