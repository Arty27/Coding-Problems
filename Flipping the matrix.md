## Flipping the Matrix

Link: https://www.hackerrank.com/challenges/flipping-the-matrix/problem

You’re given a 2n × 2n matrix. You can flip any row or column as many times as you want.
Your goal: maximize the sum of the elements in the n × n submatrix in the top-left corner.

```
112  42  83  119
56   125 56  49
15   78  101  43
62   98  114  108
```

O/P = 414

Flip column 2 and row 0

Therefor result = 119+56+125+114 = 414

### Trick for this problem

<b>Key observation:</b>
For any position (i, j) in the top-left quadrant, you can bring the maximum of four possible positions into it by flipping rows/columns.

The four candidates for (i, j) are:

```
matrix[i][j]
matrix[i][2n - 1 - j]
matrix[2n - 1 - i][j]
matrix[2n - 1 - i][2n - 1 - j]
```

By always picking the maximum of these four, we ensure the maximum sum in the top-left n × n.

You can flip how many times you want, but it will always between these for the top left quadrant

```
For (0, 0) → candidates are 112, 119, 62, 108 → pick 119
For (0, 1) → candidates are 42, 83, 98, 114 → pick 114
For (1, 0) → candidates are 56, 49, 15, 43 → pick 56
For (1, 1) → candidates are 125, 56, 78, 101 → pick 125
```

### Code

```
def flippingMatrix(matrix):
    n = len(matrix) // 2
    total = 0

    for i in range(n):
        for j in range(n):
            total += max(
                matrix[i][j],
                matrix[i][2*n - 1 - j],
                matrix[2*n - 1 - i][j],
                matrix[2*n - 1 - i][2*n - 1 - j]
            )
    return total
```
