# [Climbing Stairs](https://leetcode-cn.com/problems/climbing-stairs/)

## Description

ou are climbing a stair case. It takes n steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

### Example 1:

````
Input: 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
````

### Example 2:

````
Input: 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
````

## Constraints:

```
1 <= n <= 45
```

## 思路

回归斐波那契算法，可使用动态规划。

## 代码

```` Go
func climbStairs(n int) int {
    dp := make([]int,n+1)
    dp[0],dp[1] = 1,1
    for i:=2; i<=n; i++ {
        dp[i] = dp[i-1]+dp[i-2]
    }
    return dp[n]
}
````

```` Go
func climbStairs(n int) int {
    a,b := 1,1
    for i:=1; i<=n; i++ {
        a,b = b,a+b
    }
    return a
}
````

