# [不同路径](https://leetcode-cn.com/problems/unique-paths/)

## Description

一个机器人位于一个 m x n 网格的左上角 （起始点在下图中标记为 “Start” ）。

机器人每次只能向下或者向右移动一步。机器人试图达到网格的右下角（在下图中标记为 “Finish” ）。

问总共有多少条不同的路径？


### Example 1:

![img.png](img.png)

````
输入：m = 3, n = 7
输出：28
````

### Example 2:

````
输入：m = 3, n = 2
输出：3
解释：
从左上角开始，总共有 3 条路径可以到达右下角。
1. 向右 -> 向下 -> 向下
2. 向下 -> 向下 -> 向右
3. 向下 -> 向右 -> 向下
````

### Example 3:

````
输入：m = 3, n = 3
输出：6
````

### 提示：

```
* 1 <= m, n <= 100
* 题目数据保证答案小于等于 2 * 109
```

## 思路

动态规划，套用模板

## 代码
```` Go
func uniquePaths(m int, n int) int {
    dp := make([][]int,m)
    for i := range dp {
        dp[i] = make([]int,n)
    }
    for i:=m-1; i>=0; i-- {
        for j:=n-1; j>=0; j-- {
            if i == m-1 || j == n-1 {
                dp[i][j]=1
            } else {
                dp[i][j] = dp[i+1][j] + dp[i][j+1]
            }
        }
    }
    return dp[0][0]
}}
````

