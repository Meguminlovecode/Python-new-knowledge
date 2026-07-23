# Python Basic and my leetcode's trainning

## Leetcode 1:Two sum
 ```class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        mapp = {}

        for i, n in enumerate(nums):
            complement = target - n
            if complement in mapp:
                return [i, mapp[complement]]

            mapp[n] = i

        return [] ```
