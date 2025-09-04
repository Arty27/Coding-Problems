### Shortcuts

1. Count the number of digits in an integer

   Instead of dividing by 10 in a loop:

   ```
   import math
   n = 123456
   digits = int(math.log10(n)) + 1   # → 6
   ```
