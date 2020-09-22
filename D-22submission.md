# :japanese_goblin: Question-Majority Element II

> Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.
> Note: The algorithm should run in linear time and in O(1) space.
> Example 1:
> Input: [3,2,3]
> Output: [3]
> Example 2:
> Input: [1,1,1,3,3,2,2,2]
> Output: [1,2]

# :bento: Solution
```
class Solution {
    public List<Integer> majorityElement(int[] nums) {
        HashMap<Integer,Integer> hm=new HashMap<Integer,Integer>();
        List<Integer>list=new ArrayList<Integer>();
        int i,n=nums.length;
        for(i=0;i<n;i++){
            if(!hm.containsKey(nums[i])){
                hm.put(nums[i],1);
            }
            else{
                hm.put(nums[i],hm.get(nums[i])+1);
            }
        }
        for(Integer it: hm.keySet()){
            if(hm.get(it)>nums.length/3)
                list.add(it);
        }
        return list;
    }
}
```
