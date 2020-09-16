# :japanese_goblin: Question-Length of last word

> Given a string s consists of upper/lower-case alphabets and empty space characters ' ', return the length of last word (last word means the last   
> appearing word if we loop from left to right) in the string.  
> If the last word does not exist, return 0.  
> Note: A word is defined as a maximal substring consisting of non-space characters only.  
> Example:  
> Input: "Hello World"  
> Output: 5  

# :bento: Solution

```
class Solution {
    public int lengthOfLastWord(String s) {
        String st[]=s.split(" ");
        int l=st.length;
        if(s==null){
            return 0;
        }
        if(l<=0)
            return 0;
        
        String lastword=st[l-1];
        return lastword.length();
    }
}
```
