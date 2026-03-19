# Experiment 3: Three Way Partitioning

##  Question
Given an array and a range `a`, `b`. The task is to partition the array around the range such that the array is divided into three parts:

1. All elements smaller than `a` come first  
2. All elements in range `a` to `b` come next  
3. All elements greater than `b` appear at the end  
The individual elements of three sets can appear in any order. You are required to 
return the modified array.

---

## Code

```python
class Solution:
    # Function to partition the array around the range [a, b]
    def threeWayPartition(self, arr, a, b):
        low = 0
        mid = 0
        high = len(arr) - 1

        while mid <= high:

            # If element is smaller than a
            if arr[mid] < a:
                arr[low], arr[mid] = arr[mid], arr[low]
                low += 1
                mid += 1

            # If element is greater than b
            elif arr[mid] > b:
                arr[mid], arr[high] = arr[high], arr[mid]
                high -= 1

            # If element is in range [a, b]
            else:
                mid += 1
```

## Output
![Output](Images/Output3.png)