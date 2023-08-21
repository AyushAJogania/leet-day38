# leet-day38

# Climbing Stairs

## Problem Description

You are climbing a staircase. It takes `n` steps to reach the top. Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

## Examples

**Example 1:**
Input: `n = 2`
Output: `2`
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps

**Example 2:**
Input: `n = 3`
Output: `3`
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

## Constraints

- `1 <= n <= 45`

## Approach and Explanation

To solve this problem, we can use dynamic programming. The key insight is that to reach the `nth` step, we can either come from the `(n-1)th` step or the `(n-2)th` step. Therefore, the number of distinct ways to reach the `nth` step is the sum of the number of ways to reach the `(n-1)th` step and the number of ways to reach the `(n-2)th` step.

We can initialize two variables, `prev1` and `prev2`, to keep track of the number of ways to reach the `(n-1)th` and `(n-2)th` steps, respectively. We start with `prev1 = 1` (since there's only 1 way to reach the 1st step) and `prev2 = 2` (since there are 2 ways to reach the 2nd step).

Then, we iterate from the `3rd` step (`i = 3`) up to `n`, and for each step, we calculate the number of ways to reach the current step (`curr`) as the sum of `prev1` and `prev2`. After that, we update `prev1` to be `prev2` and `prev2` to be `curr`. This way, we keep moving forward step by step until we reach the `nth` step.

Finally, we return `prev2`, which holds the number of distinct ways to reach the `nth` step.

## Complexity Analysis

The time complexity of this solution is `O(n)`, where `n` is the input value. We only need to iterate through the steps once to calculate the number of ways.

The space complexity is `O(1)`, as we are using a constant amount of extra space regardless of the input value.

## How to Use

You can use the provided C++ code to implement the solution for the "Climbing Stairs" problem on platforms like LeetCode or your local development environment. Simply copy the code into a C++ compiler and provide the value of `n` to get the number of distinct ways to climb the stairs.

```cpp
#include <iostream>

class Solution {
public:
    int climbStairs(int n) {
        if (n <= 2) {
            return n;
        }
        
        int prev1 = 1; // Number of ways to reach the 1st step
        int prev2 = 2; // Number of ways to reach the 2nd step
        
        for (int i = 3; i <= n; i++) {
            int curr = prev1 + prev2; // Number of ways to reach the current step
            prev1 = prev2;
            prev2 = curr;
        }
        
        return prev2; // Number of ways to reach the nth step
    }
};

int main() {
    Solution solution;
    int n = 5; // Change this value to test with different n
    int ways = solution.climbStairs(n);
    std::cout << "Number of distinct ways to climb " << n << " steps: " << ways << std::endl;
    return 0;
}
```

Replace the `n` value in the `main()` function to test the solution with different input values. Run the code to see the number of distinct ways to climb the stairs for the given input `n`.
