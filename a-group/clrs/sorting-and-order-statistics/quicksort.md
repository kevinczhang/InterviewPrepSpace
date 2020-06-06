# Quicksort

## Overview

Quicksort, like merge sort, applies the divide-and-conquer paradigm. Here is the three-step divide-and-conquer process for sorting a typical subarray A\[p .. r\]:

* **Divide:** Partition \(rearrange\) the array A\[p .. r\] into two \(possibly empty\) subarrays A\[p .. q -1\] and A\[q + 1 .. r\].
* **Conquer:** Sort the two subarrays A\[p .. q -1\] and A\[q + 1 .. r\] by recursive calls to quicksort.
* **Combine:** Because the subarrays are already sorted, no work is needed to combine them: the entire array A\[p .. r\] is now sorted.

## Standard version

### QUICKSORT\(A, p, r\)

```bash
if p < r
    q = PARTITION(A, p, r)
    QUICKSORT(A, p, q - 1)
    QUICKSORT(A, q + 1, r)
```

### PARTITION\(A, p, r\)

```bash
x = A[r]
i = p - 1
for j = p to r - 1
    if A[j] <= x
        i = i + 1
        exchange A[i] with A[j]
exchange A[i + 1] with A[r]
return i + 1
```

## Randomized version

### RANDOMIZED-PARTITION\(A, p, r\)

```bash
i = RANDOM(p, r)
exchange A[r] with A[i]
return PARTITION(A, p, r)
```

### RANDOMIZED-QUICKSORT\(A, p, r\)

```bash
if p < r
    q = RANDOMIZED-PARTITION(A, p, r)
    RANDOMIZED-QUICKSORT(A, p, q - 1)
    RANDOMIZED-QUICKSORT(A, q + 1, r)
```

