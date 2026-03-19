# Experiment 2: Smallest Subarray with Sum Greater than X

##  Question
Given a number `x` and an array of integers `arr`, find the **smallest subarray** with sum greater than the given value.
If such a subarray does not exist, return `0`in that case.

---

## Code

```python
class Solution:
    def smallestSubWithSum(self, x, arr):
        n = len(arr)

        min_length = float('inf')
        curr_sum = 0
        start = 0

        for end in range(n):
            curr_sum += arr[end]

            # Shrink window while sum is greater than x
            while curr_sum > x:
                min_length = min(min_length, end - start + 1)
                curr_sum -= arr[start]
                start += 1

        if min_length == float('inf'):
            return 0

        return min_length
```

## Output
![Output](Images/Output2.png)