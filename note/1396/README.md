# [找出数组中的幸运数](https://leetcode-cn.com/problems/find-lucky-integer-in-an-array/)

## Description

在整数数组中，如果一个整数的出现频次和它的数值大小相等，我们就称这个整数为「幸运数」。

给你一个整数数组 arr，请你从中找出并返回一个幸运数。

* 如果数组中存在多个幸运数，只需返回 最大 的那个。
* 如果数组中不含幸运数，则返回 -1 。


### Example 1:

````
输入：arr = [2,2,3,4]
输出：2
解释：数组中唯一的幸运数是 2 ，因为数值 2 的出现频次也是 2 。
````

### Example 2:

````
输入：arr = [1,2,2,3,3,3]
输出：3
解释：1、2 以及 3 都是幸运数，只需要返回其中最大的 3 。
````

### Example 3:

```
输入：arr = [2,2,2,3,3]
输出：-1
解释：数组中不存在幸运数。
```

### Example 4:

```
输入：arr = [5]
输出：-1
```

### Example 5:

```
输入：arr = [7,7,7,7,7,7,7]
输出：7
```

### Note:

> 1 <= arr.length <= 500
>
> 1 <= arr[i] <= 500

## 思路 :

前缀和 + 状态压缩

## 代码
```` Go
func findLucky(arr []int) int {
    frequency := [500]int{} 

    for _,vaule := range arr {
        frequency[vaule-1]++
    }
    res := -1
    for index,fre := range frequency {
        if index+1 == fre && fre > res{
            res = fre
        }
    }
    return res
}
````
