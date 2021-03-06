---
description: Common algorithms for array
---

# Array

## Binary search

### Find First and Last Position of Element in Sorted Array

Given an array of integers `nums` sorted in ascending order, find the starting and ending position of a given `target` value.

Your algorithm's runtime complexity must be in the order of _O_\(log _n_\).

If the target is not found in the array, return `[-1, -1]`.

**Example 1:**

```text
Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
```

**Example 2:**

```text
Input: nums = [5,7,7,8,8,10], target = 6
Output: [-1,-1]
```

```java
public class Solution {
    public int[] searchRange(int[] A, int target) {
		int[] result = { -1, -1 };
		if (A.length == 0)
			return result;

		result[0] = searchLow(A, target);
		if (result[0] != -1)
			result[1] = searchHigh(A, target, result[0]);

		return result;
	}

	private int searchLow(int[] A, int target) {
		int start = 0, end = A.length - 1, mid;
		while (start < end) {
			mid = start + (end - start) / 2;
			if (A[mid] < target) {
				start = mid + 1;
				continue;
			}
			end = mid;
		}
		return (A[start] == target) ? start : -1;
	}

	private int searchHigh(int[] A, int target, int start) {
		int end = A.length-1, mid;
		while (start <= end) {
			mid = start + (end - start) / 2;
			if (A[mid] > target) {
				end = mid-1;
				continue;
			}
			start = mid + 1;
		}
		return (A[end] == target) ? end : -1;
	}
}
```

## Quick sort/select

### Kth Largest Element in an Array

Find the **k**th largest element in an unsorted array. Note that it is the kth largest element in the sorted order, not the kth distinct element.

**Example 1:**

```text
Input: [3,2,1,5,6,4] and k = 2
Output: 5
```

**Example 2:**

```text
Input: [3,2,3,1,2,4,5,5,6] and k = 4
Output: 4
```

**Note:**  
You may assume k is always valid, 1 ≤ k ≤ array's length.

```java
class Solution {
    public int findKthLargest(int[] nums, int k) {
        shuffle(nums);
        int start = 0, end = nums.length - 1, index = nums.length - k;
        while (start < end) {
            int pivot = partion(nums, start, end);
            if (pivot < index)
                start = pivot + 1;
            else if (pivot > index)
                end = pivot - 1;
            else
                return nums[pivot];
        }
        return nums[start];
    }
    // Shuffle array to O(N) guaranteed running time + O(1) space
    private void shuffle(int a[]) {
        final Random random = new Random();
        for(int ind = 1; ind < a.length; ind++) {
            final int r = random.nextInt(ind + 1);
            swap(a, ind, r);
        }
    }
    // Partition function
    private int partion(int[] nums, int start, int end) {
        int pivot = start;
        while (start <= end) {
            while (start <= end && nums[start] <= nums[pivot]) start++;
            while (start <= end && nums[end] > nums[pivot]) end--;
            if (start > end) break;
            swap(nums, start, end);
        }
        swap(nums, end, pivot);
        return end;
    }
    // excahnge function
    private void swap(int[] a, int i, int j) {
        final int tmp = a[i];
        a[i] = a[j];
        a[j] = tmp;
    }
}
```

