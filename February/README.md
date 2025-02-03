# LeetCode Daily Challenge Problems for February

## Problems:

## 1)  [Special Array I](https://leetcode.com/problems/special-array-i/description/)

### Difficulty

![](https://img.shields.io/badge/Easy-green?style=for-the-badge)

### Related Topic

`Array`

### Code

```cpp
class Solution {
public:
    bool isArraySpecial(vector<int>& nums) {
        bool x = nums[0] % 2;
        for (int i = 1; i <= nums.size(); i++) {
            if (i % 2 != 0) {
                if ((nums[i - 1] % 2 != 0) != x)
                    return 0;
            } else {
                if ((nums[i - 1] % 2 != 0) == x)
                    return 0;
            }
        }
        return 1;
    }
};
```

## 2)  [Check if Array Is Sorted and Rotated](https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/)

### Difficulty

![](https://img.shields.io/badge/Easy-green?style=for-the-badge)

### Related Topic

`Array`

### Code

```cpp
class Solution {
 public:
  bool check(vector<int>& nums) {
    const int n = nums.size();
    int rotates = 0;
    for (int i = 0; i < n; ++i){
      if (nums[i] > nums[(i + 1) % n] && ++rotates > 1)
        return false;
    }
    return true;
  }
};
```

## 3)  [Longest Strictly Increasing or Strictly Decreasing Subarray](https://leetcode.com/problems/longest-strictly-increasing-or-strictly-decreasing-subarray/)

### Difficulty

![](https://img.shields.io/badge/Easy-green?style=for-the-badge)

### Related Topic

`Array`

### Code

```cpp
class Solution {
public:
    int longestMonotonicSubarray(vector<int>& nums) {
        int n = nums.size();
        int ans = 1, ln = 1;
        for (int i = 1; i < n; i++) {
            if (nums[i] > nums[i - 1])
                ln++;
            else {
                ans = max(ans, ln);
                ln = 1;
            }
        }
        ans = max(ans, ln);
        ln = 1;
        for (int i = n - 2; i >= 0; i--) {
            if (nums[i] > nums[i + 1])
                ln++;
            else {
                ans = max(ans, ln);
                ln = 1;
            }
        }
        ans = max(ans, ln);
        ln = 1;
        return ans;
    }
};
```

