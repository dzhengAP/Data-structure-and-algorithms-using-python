
Given four integer arrays nums1, nums2, nums3, and nums4 all of length n, return the number of tuples (i, j, k, l) such that:

0 <= i, j, k, l < n
nums1[i] + nums2[j] + nums3[k] + nums4[l] == 0
 
#Example 1:

Input: nums1 = [1,2], nums2 = [-2,-1], nums3 = [-1,2], nums4 = [0,2]
Output: 2
Explanation:
The two tuples are:
1. (0, 0, 0, 1) -> nums1[0] + nums2[0] + nums3[0] + nums4[1] = 1 + (-2) + (-1) + 2 = 0
2. (1, 1, 0, 0) -> nums1[1] + nums2[1] + nums3[0] + nums4[0] = 2 + (-1) + (-1) + 0 = 0


```Python
class Solution:
    def fourSumCount(self, nums1: List[int], nums2: List[int], nums3: List[int], nums4: List[int]) -> int:

        seen12,seen34={},{}
        ans=0
        for m, n4 in enumerate(nums4):
            for k, n3 in enumerate(nums3):
                seen34[n4+n3]=seen34.get(n4+n3,0)+1
                
        for i, n1 in enumerate(nums1):
            for j, n2 in enumerate(nums2):
                seen12[n1+n2]=seen12.get(n1+n2,0)+1

        for k, v in seen12.items():
            if -k in seen34.keys():
                ans+=v*seen34[-k]
                
        return ans
```
