# Problem: SubArrayRangeSum

## Problem Statement

You are given an array of integers `arr` of size `n`, and multiple queries, each consisting of two integers `l` and `r`. For each query, your task is to calculate the sum of elements in the subarray from index `l` to `r` (both inclusive). Assume 0-based indexing for the array.

### Input Format
- The first line contains two integers `n` and `q` — the size of the array and the number of queries, respectively.
- The second line contains `n` integers — the elements of the array.
- The next `q` lines each contain two integers `l` and `r` — the range of indices for which the sum is to be calculated.

### Output Format
- For each query, print a single integer — the sum of elements in the subarray from index `l` to `r`.

### Constraints
- \( 1 < n < 10^5 \)
- \( -10^4 < arr[i] < 10^4 \)
- \( 1 < q < 10^5 \)
- \( 0 < l < r < n \)

## Examples

### Example 1
#### Input
```plaintext
5 3
1 2 3 4 5
1 3
0 4
2 2
```
#### Output
```plaintext
9
15
3
```
#### Explanation
- Query 1: The subarray from index `1` to `3` is `[2, 3, 4]`. The sum is `2 + 3 + 4 = 9`.
- Query 2: The subarray from index `0` to `4` is `[1, 2, 3, 4, 5]`. The sum is `1 + 2 + 3 + 4 + 5 = 15`.
- Query 3: The subarray from index `2` to `2` is `[3]`. The sum is `3`.

### Example 2
#### Input
```plaintext
6 2
-1 2 -3 4 -5 6
1 4
0 5
```
#### Output
```plaintext
-2
3
```
#### Explanation
- Query 1: The subarray from index `1` to `4` is `[2, -3, 4, -5]`. The sum is `2 + (-3) + 4 + (-5) = -2`.
- Query 2: The subarray from index `0` to `5` is `[-1, 2, -3, 4, -5, 6]`. The sum is `-1 + 2 + (-3) + 4 + (-5) + 6 = 3`.

### Example 3
#### Input
```plaintext
4 1
10 20 30 40
2 3
```
#### Output
```plaintext
70
```
#### Explanation
- Query 1: The subarray from index `2` to `3` is `[30, 40]`. The sum is `30 + 40 = 70`.
