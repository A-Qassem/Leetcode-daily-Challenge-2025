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

