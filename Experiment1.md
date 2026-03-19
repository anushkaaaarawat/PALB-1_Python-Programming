# 🐍 Experiment 1: Chocolate Distribution Problem

## 📌 Question
Given an array `arr[]` of positive integers, where each value represents the number of chocolates in a packet. Each packet can have a variable number of chocolates.  

There are `m` students. The task is to distribute chocolate packets among `m` students such that:

1. Each student gets exactly one packet  
2. The difference between the maximum and minimum number of chocolates given to students is **minimum**

👉 Return the **minimum possible difference**

---

## 💻 Python Code

```python
class Solution:
    def findMinDiff(self, arr, M):
        n = len(arr)

        # If students are more than packets
        if M > n:
            return -1

        # Sort the array
        arr.sort()

        # Initialize minimum difference
        min_diff = float('inf')

        # Check all possible groups of size M
        for i in range(n - M + 1):
            diff = arr[i + M - 1] - arr[i]
            min_diff = min(min_diff, diff)

        return min_diff
```

## Output 
![Output](Images/Output1.png)