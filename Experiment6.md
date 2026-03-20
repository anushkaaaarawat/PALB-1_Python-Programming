# Experiment 6: Find Median of an Array

## Question
Given an array `arr[]` of integers, calculate the **median**.

Median is:
- Middle element (if odd number of elements)
- Average of two middle elements (if even number of elements)

---

## Code

```python
class Solution:
    def findMedian(self, arr):
        arr.sort()
        n = len(arr)

        # Odd case
        if n % 2 == 1:
            return arr[n // 2]

        # Even case
        else:
            return (arr[n // 2 - 1] + arr[n // 2]) / 2
```

## Output
![Output](Images/Output6.png)