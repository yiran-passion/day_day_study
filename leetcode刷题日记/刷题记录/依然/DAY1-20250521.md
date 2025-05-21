## 704. 二分查找

### 详情

[代码随想录讲解](https://programmercarl.com/0704.%E4%BA%8C%E5%88%86%E6%9F%A5%E6%89%BE.html)

[题目链接](https://leetcode.cn/problems/binary-search/description/)

### 解法

#### 一、二分法

- 代码：

  ```js
  const search = function(nums, target) {
    let left = 0, right = nums.length - 1
    while (left <= right) {
      const mid = Math.floor((left + right) / 2)
      if (nums[mid] < target) {
        left = mid + 1
      } else if (nums[mid] > target) {
        right = mid - 1
      } else {
        return mid
      }
    }
    return -1
  };
  ```

- 复杂度

  - 时间复杂度：O(logn)
  - 空间复杂度：O(1)


## 27. 移除元素

### 详情

[代码随想录讲解](https://programmercarl.com/0027.%E7%A7%BB%E9%99%A4%E5%85%83%E7%B4%A0.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)

[题目链接](https://leetcode.cn/problems/remove-element/description/)

### 解法

#### 一、双指针

- 代码：

  ```js
  const removeElement = function(nums, val) {
    let slowIndex = 0
    for (let fastIndex = 0, len = nums.length; fastIndex < len; fastIndex ++) {
      if (nums[fastIndex] !== val) {
        nums[slowIndex] = nums[fastIndex]
        slowIndex ++
      }
    }
    return slowIndex
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)


## 977. 有序数组的平方

### 详情

[代码随想录讲解](https://programmercarl.com/0977.%E6%9C%89%E5%BA%8F%E6%95%B0%E7%BB%84%E7%9A%84%E5%B9%B3%E6%96%B9.html)

[题目链接](https://leetcode.cn/problems/squares-of-a-sorted-array/description/)

### 解法

#### 一、双指针

- 代码：

  ```js
  const sortedSquares = function(nums, result = []) {
    let left = 0, right = nums.length - 1
    while (left <= right) {
      if (Math.pow(nums[left], 2) < Math.pow(nums[right], 2)) {
        result.unshift(Math.pow(nums[right], 2))
        right --
      } else {
        result.unshift(Math.pow(nums[left], 2))
        left ++
      }
    }
    return result
  };
  ```

- 复杂度

  - 时间复杂度：O(n)
  - 空间复杂度：O(1)
