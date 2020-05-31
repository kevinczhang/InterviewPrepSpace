# Heapsort

## Heap

The \(binary\) heap data structure is an **array object** that we can view as a nearly complete **binary tree**. The tree is completely filled on all levels except possibly the lowest, which is filled from the left up to a point.

An array _A_ that represents a heap is an object with two attributes:

* A.length, which \(as usual\) gives the number of elements in the array
* A.heap-size, which represents how many elements in the heap are stored within array A.

That is may only the elements where 0 ~ A.heap-size are valid elements of the heap.

The root of the tree is A\[0\], and given the index i of a node, we can easily compute the indices of its parent, left child, and right child:

* PARENT index of node i : \(i -1\)/2
* LEFT node index of node i: 2i
* RIGHT node index of node i: 2i + 1

