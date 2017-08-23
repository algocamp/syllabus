# Merge Sort

Merge sort is a divide and conquer algorithm. The purpose of dividing the input is to simplify the problem so that it can be solved efficiently.

In the case of merge sort, the input list is divided until all the sublist are themselves sorted. As we don't know anything about the order of the list items, they must be divided into sub lists that each contain just a single (sorted!) value.

## How it works

To understand why it is necessary to first divide the input array, it helps to first learn how the merge step works.

A merge function takes 3 arguments: `listToBeSorted`, `firstHalfOfListSorted` and `secondHalfOfListSorted`.

For example: `merge([4,2,5,6,1], [2,4,5], [1,6])`

Notice how the 2 halves are already sorted. When this is know the merge operation can be performed in a single iteration. The `merge` function steps through the input list and at each iteration pulls the lowest number from the one of the two halves.

```c
[4,2,5,6,1] [2,4,5] [1,6]
 |           |       |

[1,2,5,6,1] [2,4,5] [_,6]
   |         |         |

[1,2,5,6,1] [_,4,5] [_,6]
     |         |       |

[1,2,4,6,1] [_,_,5] [_,6]
     |           |     |

[1,2,4,5,1] [_,_,_] [_,6]
         |             |

[1,2,4,5,6] [_,_,_] [_,_] 👍
```

How then do we get the two halves sorted? This is where dividing comes into play. By dividing the input array into the smallest possible halves - a sublist with just a single value - the halves can be considered sorted, and therefore can be merged.

To bring it all together (or conquer), we can write a recursive function `mergeSort` that, keeps dividing the input into sublists of a single item, then merges the sublists back together into a sorted array:


Divide:
```c
[4,1,5,0,8]
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

## Complexity

Todo

## Practice

- https://www.hackerrank.com/contests/hw1/challenges/merge-sort
- https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/p/challenge-implement-merge-sort (JavaScript)

## Resources
- https://en.wikipedia.org/wiki/Merge_sort
- https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/a/divide-and-conquer-algorithms
