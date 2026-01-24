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
