# Leetcode 20 Valid
```python3 []
class Solution:
    def isValid(self, s: str) -> bool:
        valid={")":"(","}":"{","]":"["}
        stack=[]
        for char in s:
            if stack and char in ")]}" and valid[char]==stack[-1]:
                stack.pop()
                continue
            stack.append(char)
        return True if not stack else False
        
```

# Remove Dulicates
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
