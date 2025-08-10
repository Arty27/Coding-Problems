## Bubble Sort

Roles of the loops

- Outer loop → How many passes we make
  Think: “How many times do we bubble items to their correct place at the end.”
  After each pass, the largest remaining element is in place, so we reduce the range.

- Inner loop → The bubbling itself
  Goes through the list comparing adjacent elements (j and j+1) and swapping if they’re in the wrong order.

### Code

Inner loop compares adjacent elements `j and j+1 `

```
arr = [1, 4, 3, 7, 5, 2, 3]
n = len(arr)
for i in range(n):
    for j in range(0, n - i - 1):
        if arr[j] < arr[j + 1]:
            arr[j], arr[j + 1] = arr[j + 1], arr[j]
print(arr)
```

### Complexities

<b>Time</b>: Best Case = <code>O(n)</code> with swap flag Worst Case: <code>O(n<sup>2</sup>)</code>

<b>Space:</b> Always <code>O(1)</code> since no extra space needed other than few variables
