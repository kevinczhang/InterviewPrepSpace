# KMP

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

