## Practice octobar 6
```.py
def count_letter(msg:str, letter:str):
    count=0
    for i in range(len(msg)):
        if msg[i]==letter:
            count+=1
    return count

test1=count_letter("hello", "l")
print(test1)
```
