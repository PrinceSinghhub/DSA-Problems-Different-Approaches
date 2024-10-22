# Single Number Problem

This document contains the implementation of the "Single Number" problem, where every element in the array appears an even number of times except for one. The goal is to find the element that occurs an odd number of times.

## Code Implementation

```python
class Solution:
    def SingleNumber(self, arr):
        # Approach 1: Nested Loop (Brute Force)
        def find_odd_occurrence_brute_force(arr):
            for val in arr:
                count = 0
                for num in arr:
                    if num == val:
                        count += 1
                if count % 2 != 0:
                    return val
            return None

        # Approach 2: Using a HashMap
        def find_odd_occurrence_hashmap(arr):
            frequency = {}
            for num in arr:
                if num in frequency:
                    frequency[num] += 1
                else:
                    frequency[num] = 1
            for key, count in frequency.items():
                if count % 2 != 0:
                    return key
            return None

        # Approach 3: Using XOR
        def find_odd_occurrence_xor(arr):
            result = 0
            for num in arr:
                result ^= num
            return result 
        return find_odd_occurrence_xor(arr)

# Example usage
sol = Solution()
result = sol.SingleNumber([1, 1, 2, 2, 2])
print(result)  
# Output: 2
