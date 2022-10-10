# Quiz 9: Create a function that receives as input a string and returns the string ciphered with a shift 13.

## Code 
```.py
def stringciphered(shift: int, user_input) -> str:
    out = ""
    for letter in user_input:
        ord_1 = ord(letter)
        if ord_1 == 32:
            ord_2 = 32
        else:
            ord_2 = ord_1 + shift
        if ord_2 > 122:
            ord_2 -= 26
        out += chr(ord_2)
    return out

user_input = input("Enter string: ")
user_input = user_input.lower()
shift = int(input("Enter shift: "))
shift = shift % 26

test = stringciphered(shift, user_input)
print(test)
```
## Flow chart
## Test
![](Screen%20Shot%202022-10-10%20at%2018.51.35.png)
