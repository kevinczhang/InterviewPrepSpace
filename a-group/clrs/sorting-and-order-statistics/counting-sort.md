# Linear sort

## **Counting sort**

**Counting sort** assumes that each of the n input elements is an integer in the range 0 to k, for some integer k. When k = O\(n\), the sort runs in ~~O~~\(n\) time.

### COUNTING-SORT\(A, B, k\)

```bash
let C[0 .. k] be a new array
for i = 0 to k
    C[i] = 0
for j = 1 to A.length
    C[A[j]] = C[A[j]] + 1
// C[i] now contains the number of elements equal to i
for i = 1 to k
    C[i] = C[i] + C[i-1]
// C[i] now contains the number of elements less than or equal to i
for j = A.length downto 1
    B[C[A[j]]] = A[j]
    C[A[j]] = C[A[j]] - 1
```

An important property of counting sort is that it is stable: numbers with the same value appear in the output array in the same order as they do in the input array.

## Radix sort

Radix sort is the algorithm used by the card-sorting machines you now find only in computer museums.

