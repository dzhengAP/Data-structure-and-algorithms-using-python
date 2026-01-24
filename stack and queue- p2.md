**RPN**
```Python
class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        if not tokens:
            return 0
        stack = []
        for t in tokens:
            if t not in "+-*/":
                stack.append(int(t))
            elif t == "+":
                temp1=stack.pop()
                temp2=stack.pop()
                stack.append((int(temp2+temp1)))  
            elif t == "-":
                temp1=stack.pop()
                temp2=stack.pop()
                stack.append(int(temp2-temp1))
            elif t == "*":
                temp1=stack.pop()
                temp2=stack.pop()
                stack.append(int(temp2*temp1))           
            elif t == "/":
                temp1=stack.pop()
                temp2=stack.pop()
                stack.append(int(temp2/temp1))  
        return stack[0]
```
**Sliding Window**
```Python
from collections import deque
class Solution:
    def slidingwindow(self, nums, k) -> int:
        ans=[]
        l, r = 0, 0
        while r<=len(nums)-1:
            while dq and dq[-1][1]<=nums[r]:
                dq.pop()
            dq.append((r,nums[r]))
            if r-l+1>=k:
                ans.append(dq[1][1])
                l+=1
                if dq[0][0]<l:
                    dq.popleft()
            r+=1
        return ans
```
**TopK**
```Python
from collections import Counter
class Solution:
    def TopK(self, nums,k):
        ans=[]
        n=len(nums)
        bucket=[[] for _ in range(n+1)]
        count=Counter(nums)
        for num, freq in count.items():
            bucket[freq].append(num)
        for i in range(n, -1, -1):
            for num in bucket[i]:
                ans.append(num)
                if len(ans)==k:
                    return ans
```
