Problem:  
We are given an array `[1, 1, 2, 2, 2]`, where every element appears an even number of times except for one. The task is to find the element that occurs an odd number of times. (GeeksforGeeks Problem)

Constraints:  
- Array size: `1 ≤ arr.size() ≤ 10^6`  
- Element values: `0 ≤ arr[i] ≤ 10^5`

Approach 1 (Naive):  
Initially, you might think to count the occurrences of each element and return the one with an odd count:
```python
if arr.count(val) % 2 != 0:
  return val
```
However, this approach results in TLE since it iterates through the entire array multiple times.

Approach 2 (Optimized):  
A better solution involves using a hashmap (dictionary) to store frequencies, or even a clever use of the XOR operator.  
- XOR operation cancels out pairs of the same number, leaving only the odd-occurring element in the end.  
This method is faster and successfully passes the constraints!

Key Lesson:  
When dealing with large input sizes, optimization is crucial. A brute-force solution may work on small inputs, but optimizing your approach is the key to success on competitive coding platforms!