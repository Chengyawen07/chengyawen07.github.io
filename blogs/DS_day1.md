---
layout: page
permalink: /blogs/DS_day1/index.html
title: DS_day1
---


# day1：二分法

# 704 二分法

## 题目：

给定一个 `n` 个元素有序的（升序）整型数组 `nums` 和一个目标值 `target` ，写一个函数搜索 `nums` 中的 `target`，如果目标值存在返回下标，否则返回 `-1`。

**提示：**

1. 你可以假设 `nums` 中的所有元素是不重复的。
2. `n` 将在 `[1, 10000]`之间。
3. `nums` 的每个元素都将在 `[-9999, 9999]`之间。



# 思路：

1. 一般写左闭又闭[ ]，或者左闭右开[ )
2. 对于区间的定义，会影响写二分法时的边界处理

**这里，我们选择 左闭右闭 的方法**：(不确定用什么符号时，可以假设数组中只有一个1时，你会用什么符号 )



## 伪代码

```cpp
// 伪代码
Left = 0;
right = num -1;

While (left <= right) { 
	mid = (left - right) / 2;
	
	if (nums[mid] > target):
	 right = mid - 1;
	else if (nums[mid] < target):
		left = mid + 1;
	else: return mid;
}
return -1;

```



## c++实现：

```cpp
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int left = 0;
        int right = nums.size() - 1;
        while (left <= right) {
            int mid = (left + right) / 2;
            if (nums[mid] > target) {
                right = mid - 1;
            }else if (nums[mid] < target) {
                left = mid + 1;
            }else return mid;
        }
        return -1;
    }
};
```



























