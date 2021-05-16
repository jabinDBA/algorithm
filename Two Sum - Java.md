# Two Sum

## Question

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to `target`*.

You may assume that each input would have ***exactly\* one solution**, and you may not use the *same* element twice.

You can return the answer in any order.

**Example :**

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Output: Because nums[0] + nums[1] == 9, we return [0, 1].
```



## Solution 01 - Brute Force

Time Complexity = O(n^2)

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        int[] result = new int[2];
        
        for(int i=0; i<nums.length; i++){
            for(int j=i+1; j<nums.length; j++){
                if(nums[i] + nums[j] == target){
                    result[0] = i;
                    result[1] = j;
                    break;
                }
            }
        }
        
        return result;
    }
}
```



## Solution 02 - HashMap

Time Complexity = O(n)

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
    
        HashMap<Integer, Integer> map = new HashMap<Integer, Integer>();
        
        int[] result = new int[2];
        
        for(int i=0; i<nums.length; i++){
            if(map.containsKey(target-nums[i])){
                result[0] = map.get(target-nums[i]);
                result[1] = i;
            } else {
                map.put(nums[i], i);
            }
        }
        
        return result;
        
    }

}
```

