## Selection Sort

"Select the smallest, put it in place."

Breakdown:

- Outer loop → "Pick the position" (we’re deciding where the next smallest element should go).

- Inner loop → "Find the smallest in the rest" (search the unsorted part of the array).

- Swap once → "Put it in place" (move that smallest to the current position).

### Code

min or max position is selected and then swaping to that position happens outside the inner loop

```
arr = [1, 4, 3, 7, 5, 2, 3]
n = len(arr)
for i in range(n):
    min = i
    for j in range(i + 1, n):
        if arr[min] > arr[j]:
            min = j
    arr[i], arr[min] = arr[min], arr[i]
print(arr)
```
