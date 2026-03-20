#  Experiment 4: Minimum Swaps to Bring Elements ≤ k Together

##  Question
Given an array `arr` and a number `k`. You can perform swap operations any number of times (swap any two elements).
Find the **minimum number of swaps required** to bring all elements **less than or equal to `k` together** (make them a contiguous subarray).

---

##  Code
```python
class Solution:
    def minSwap(self, arr, k):
        n = len(arr)

        # Step 1: Count elements <= k
        good = 0
        for num in arr:
            if num <= k:
                good += 1

        # Step 2: Count bad elements in first window
        bad = 0
        for i in range(good):
            if arr[i] > k:
                bad += 1

        # Step 3: Sliding window
        ans = bad
        i = 0

        for j in range(good, n):
            # Remove left element
            if arr[i] > k:
                bad -= 1

            # Add right element
            if arr[j] > k:
                bad += 1

            # Update answer
            ans = min(ans, bad)

            i += 1

        return ans
```

## Output
![Output](Images/Output4.png)