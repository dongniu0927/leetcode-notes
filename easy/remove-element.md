题目链接：https://leetcode.com/problems/remove-duplicates-from-sorted-array/discuss/

题目大意：删除数组中与给定值相同的值，并返回新数组长度。  

### own
```python
class Solution(object):
    def removeElement(self, nums, val):
        """
        :type nums: List[int]
        :type val: int
        :rtype: int
        """
        if not nums:
            return 0
        i=0
        l=len(nums)
        while i<l:
            if(nums[i]==val):
                nums.pop(i)
                l-=1
                i-=1
            i+=1
        return len(nums)
```
时间复杂度O(n)  
通过

### best
```python
def removeElement(self, nums, val):
    try:
        while True:
            nums.remove(val)
    except:
        return len(nums)
```
时间复杂度O(n^2)  

注意点：
 + for i in range(len(nums)) 循环中的上限值跟i都不能被改变，当删除某一个值后，实际的长度会缩短，这样会有移除问题，如果循环中要删除，可以考虑使用while，或者在for中加边界判断
