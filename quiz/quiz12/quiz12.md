# Quiz 12: Create a function that receives integer 2<N<10, and returns the multiplication table for the number up to 9.
## Code
```.py
def mulTable(num:int):
    out=[]
    for i in range(1,10):
        mult=num*i
        out.append(f"{num} x {i} = {mult}")
    return out

user_input = int(input("Enter a number between 1 and 9: " ))
for i in mulTable(user_input):
    print(i)
```
