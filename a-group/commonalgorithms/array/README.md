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
			mid = (start + end) / 2;
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
			mid = (start + end) / 2;
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

