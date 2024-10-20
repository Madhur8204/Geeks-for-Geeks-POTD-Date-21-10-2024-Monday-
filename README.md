# Geeks-for-Geeks-POTD-Date-21-10-2024-Monday
Split the Array. 

**Statement:**

Given an array **arr**[]  of integers, the task is to count the number of ways to split given array elements into two disjoint groups such that the XOR of elements of each group is equal.
**Note:** The answer could be very large so print it by doing modulo with 109 + 7

**Examples:**

**Input 1:**

arr[] = [1, 2, 3]

**Output 1:**

3
**Explanation:**

{(1),(2, 3)}, {(2),(1, 3)}, {(3),(1, 2)} are three ways with equal XOR value of two groups.

**Input 2:** arr[] = [5, 2, 3, 2]

**Output 2:** 0

**Explanation:** No way to split into  two groups whose XOR is equal.

**Expected Time Complexity:** O(n).

**Expected Auxiliary Space:** O(1).

**Constraints:**

1<=arr.size()<=106

1<=arr[i]<=106


**Python Code:**

#User function Template for python3

class Solution:

    def countgroup(self, arr): 
    
        # Define the modulo constant to handle large numbers
        
        MOD = (10**9) + 7
        
        # Step 1: Calculate the XOR of all elements in the array
        
        total_xor = 0
        
        for num in arr:
        
            total_xor ^= num  # Compute cumulative XOR
        
        # Step 2: Check if the total XOR is non-zero
        
        if total_xor != 0:
        
            # If the XOR is not zero, return 0 as it's impossible to split the array
            
            return 0
        
        # Step 3: Calculate the number of valid groups
        
        n = len(arr)  # Get the number of elements in the array
        
        result = pow(2, n - 1, MOD) - 1  # Calculate (2^(n-1) - 1) % MOD
        
        # Return the result ensuring it's non-negative by taking modulo
        
        return result % MOD
        
#{
 
if __name__ == "__main__":

    t = int(input())
    
    while t > 0:
    
        arr = list(map(int, input().split()))
        
        ob = Solution()
        
        res = ob.countgroup(arr)
        
        print(res)
        
        t -= 1

}#





