```python3
class Solution:
    def reverseWords(self, s: str) -> str:
        return " ".join (list(s.split())[::-1]) 
```
**need to understand the split()🔹 If you don’t pass anything, split():**
**Splits on any whitespace (spaces, tabs, newlines) Automatically ignores extra spaces**
