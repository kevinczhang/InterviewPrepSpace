---
description: Common algorithm for string matching
---

# KMP

Implement [strStr\(\)](http://www.cplusplus.com/reference/cstring/strstr/).

Return the index of the first occurrence of needle in haystack, or **-1** if needle is not part of haystack.

**Example 1:**

```text
Input: haystack = "hello", needle = "ll"
Output: 2
```

**Example 2:**

```text
Input: haystack = "aaaaa", needle = "bba"
Output: -1
```

## Solution

For a given source string and a target string, you should output the first index\(from 0\) of target string in source string. If target does not exist in source, just return -1.

```java
class Solution {
    public int strStr(String haystack, String needle) {
		if (needle == null || haystack == null || needle.length() > haystack.length())
            return -1;
        if (needle.length() == 0){
            return 0;
        }
		
		int[] prefixInds = getPrefix(needle);
		int haystackInd = 0;
		while (haystackInd <= haystack.length() - needle.length()) {
			int needleInd = 0;
			while (needleInd < needle.length()) {
				if(haystack.charAt(haystackInd + needleInd) != needle.charAt(needleInd)) {
					haystackInd = needleInd == 0 ? haystackInd + 1 : 
						haystackInd + needleInd - prefixInds[needleInd - 1];
					break;
				}
				needleInd++;
			}
			if (needleInd == needle.length()) {
				return haystackInd;
			}				
		}
		return -1;
    }

	// Generate prefix function for the pattern
	private int[] getPrefix(String pattern) {
		int[] res = new int[pattern.length()];
		res[0] = 0;
		for (int i = 1; i < pattern.length(); i++) {
			int ind = res[i - 1];
			while (ind > 0 && pattern.charAt(ind) != pattern.charAt(i)) {
				ind = res[ind - 1];
			}
			res[i] = (pattern.charAt(ind) == pattern.charAt(i)) ? ind + 1 : 0;
		}		
		return res;
	}
}
```
