```Python
class Solution:
    def removeDuplicates(self, s: str) -> str:
        if not s: returns
        stack=[]
        for char in s:
            if not stack or char != stack[-1]:
                stack.append(char)
            else: 
                while stack and char == stack[-1]:
                        stack.pop()
        return "".join(stack)
        
```
