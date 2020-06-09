# Partition Array

Given an array nums of integers and an int k, partition the array \(i.e move the elements in "nums"\) such that:

* All elements &lt; k are moved to the left
* All elements &gt;= k are moved to the right

Return the partitioning index, i.e the first index i nums\[i\] &gt;= k.

#### Example

If nums = \[3,2,2,1\] and k=2, a valid answer is 1.

```java
public class Solution {
   /** 
     * @param nums: The integer array you should partition
     * @param k: As description
     * return: The index after partition
     */
    public int partitionArray(int[] nums, int k) {
          if(nums.length == 0) return 0;
	   			int cur = 0, largePointer = nums.length-1;
	   			while(cur < largePointer){
	        			if(nums[cur] < k){
	            			cur++;
	        			} else{
	            			nums[cur] += nums[largePointer];
	            			nums[largePointer] = nums[cur] - nums[largePointer];
	            			nums[cur] = nums[cur] - nums[largePointer];
	            			largePointer--;
	        			}
	        }
	    		return nums[cur] < k ? cur+1 : cur;
    }
}
```



