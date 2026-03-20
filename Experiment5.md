#  Experiment 5: Check if All Elements are Palindrome

##  Question
Given an array `arr[]` of positive integers, return **true** if all the array elements are palindrome, otherwise return **false**.

---

## Code

```python
def isPalinArray(arr):
    for num in arr:
        # Convert to string and check reverse
        if str(num) != str(num)[::-1]:
            return False
    
    return True
```

## Output
![Output](Images/Output5.png)