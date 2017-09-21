题目链接：https://leetcode.com/problems/maximum-subarray/description/

题目大意：最大子串和。（存在负值的数组）

### best
规则：一个正数加上一个负数<原正数
思路：本题目属于动态规划问题
```python
class Solution(object):
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if not nums:
            return 0
        curSum=maxSum=nums[0]
        for item in nums[1:]:
            curSum=max(item,curSum+item)
            maxSum=max(maxSum,curSum)
        return maxSum
```
