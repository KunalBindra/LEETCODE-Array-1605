# LEETCODE-Array-1605
To understand the functionality of the `restoreMatrix` method, let's walk through a dry run with a specific example. We will take arrays `rowSum` and `colSum` and trace the operations performed by the method step-by-step.

### Example

Let's consider the following input:
- `rowSum = [3, 8]`
- `colSum = [4, 7]`

### Initialization

- `m = rowSum.length = 2`
- `n = colSum.length = 2`
- `ans = new int[m][n] = new int[2][2] = [[0, 0], [0, 0]]`

### Loop Execution

#### First Iteration (i = 0)

- For `j = 0`:
  - `ans[0][0] = Math.min(rowSum[0], colSum[0]) = Math.min(3, 4) = 3`
  - Update `rowSum[0] -= ans[0][0] => rowSum[0] = 3 - 3 = 0`
  - Update `colSum[0] -= ans[0][0] => colSum[0] = 4 - 3 = 1`
  - `ans = [[3, 0], [0, 0]]`

- For `j = 1`:
  - `ans[0][1] = Math.min(rowSum[0], colSum[1]) = Math.min(0, 7) = 0`
  - Update `rowSum[0] -= ans[0][1] => rowSum[0] = 0 - 0 = 0`
  - Update `colSum[1] -= ans[0][1] => colSum[1] = 7 - 0 = 7`
  - `ans = [[3, 0], [0, 0]]`

#### Second Iteration (i = 1)

- For `j = 0`:
  - `ans[1][0] = Math.min(rowSum[1], colSum[0]) = Math.min(8, 1) = 1`
  - Update `rowSum[1] -= ans[1][0] => rowSum[1] = 8 - 1 = 7`
  - Update `colSum[0] -= ans[1][0] => colSum[0] = 1 - 1 = 0`
  - `ans = [[3, 0], [1, 0]]`

- For `j = 1`:
  - `ans[1][1] = Math.min(rowSum[1], colSum[1]) = Math.min(7, 7) = 7`
  - Update `rowSum[1] -= ans[1][1] => rowSum[1] = 7 - 7 = 0`
  - Update `colSum[1] -= ans[1][1] => colSum[1] = 7 - 7 = 0`
  - `ans = [[3, 0], [1, 7]]`

### Final Matrix

The final matrix `ans` is:

```
[[3, 0],
 [1, 7]]
```

This matrix satisfies the conditions where the sum of each row matches the corresponding value in `rowSum` and the sum of each column matches the corresponding value in `colSum`.

### Summary

The method works by iteratively assigning the minimum possible value to each cell while updating the `rowSum` and `colSum` arrays to reflect the remaining sums. This approach ensures that the final matrix will have row and column sums that match the given input arrays.
