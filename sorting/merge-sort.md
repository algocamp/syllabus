# Merge Sort

Merge sort is a divide and conquer algorithm with 3 steps: divide, conquer, and merge.

To understand why it is necessary to first divide the input array, it helps to first learn how the merge step works.

The merge function takes 3 arguments: `arrayToBeSorted`, `firstHalfOfArraySorted` and `secondHalfOfArraySorted`.

For example: `merge([4,2,5,6,1], [2,4,5], [1,6])`

The 2 halves of `array` are merged in order. This operation can be performed in constant time because the 2 halves are already sorted. The `merge` function here steps through the input array in a single loop and at each iteration pulls the lowest number from the halves.

How then do we get the two halves sorted? This is where dividing comes into play. By dividing the input array into the smallest possible halves - 2 single digits - the two halves can be considered sorted, and therefore can be merged.

To bring it altogether, `conquer`, using recursion, divides the array until it is small enough to merge, and merges until the original array is sorted.

So in summary, we use:

a) **Divide**: take an input array and divide it in half e.g. `[4,1,5,8,0] -> [[4,1,5], [0,8]]`

and

b) **Merge**: take 2 sorted halves and merge them into a sorted array:
```c
[[1,4,5], [0,8]] -> [0,1,4,5,8]
```

To achieve:


**Conquer**: using recursion, keep dividing the halves until every halve is a single item, and then combine the halves together

Divide:
```c
[[4,1,5], [0,8]]
[[[4,1], [1]]], [[0], [[8]]]
[[[[4],[1]], [1]]], [[0], [[8]]]
```
Merge:
```c
[[[[4],[1]], [1]]], [[0], [[8]]]
[[[1, 4]], [1]], [[0, 8]]]
[[1, 1, 4], [0, 8]]
[0, 1, 1, 4, 8]]
```

## Practice

- https://www.hackerrank.com/contests/hw1/challenges/merge-sort
- https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/p/challenge-implement-merge-sort (JavaScript)

## Resources
- https://en.wikipedia.org/wiki/Merge_sort
- https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/a/divide-and-conquer-algorithms
