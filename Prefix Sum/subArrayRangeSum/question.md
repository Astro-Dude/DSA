# Problem: SubArrayRangeSum

## Problem Statement

You are given an array of integers `arr` of size `n`, and two integers `l` and `r`. Your task is to calculate the sum of elements in the subarray from index `l` to `r` (both inclusive). Assume 0-based indexing for the array.

### Input Format
- The first line contains an integer `n` — the size of the array.
- The second line contains `n` integers — the elements of the array.
- The third line contains two integers `l` and `r` — the range of indices for which the sum is to be calculated.

### Output Format
- Print a single integer — the sum of elements in the subarray from index `l` to `r`.

### Constraints
- \( 1 \leq n \leq 10^5 \)
- \( -10^4 \leq \text{arr[i]} \leq 10^4 \)
- \( 0 \leq l \leq r < n \)

## Examples

### Example 1
#### Input
```plaintext
5
1 2 3 4 5
1 3
```
#### Output
```plaintext
9
```
#### Explanation
The subarray from index `1` to `3` is `[2, 3, 4]`. The sum of these elements is `2 + 3 + 4 = 9`.

### Example 2
#### Input
```plaintext
3
-1 -2 -3
0 2
```
#### Output
```plaintext
-6
```
#### Explanation
The subarray from index `0` to `2` is `[-1, -2, -3]`. The sum of these elements is `-1 + (-2) + (-3) = -6`.

### Example 3
#### Input
```plaintext
4
10 20 30 40
2 2
```
#### Output
```plaintext
30
```
#### Explanation
The subarray from index `2` to `2` is `[30]`. The sum of these elements is `30`.
