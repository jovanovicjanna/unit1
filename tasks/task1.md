# Task 1
## Python code

```.py
#task 1: print a list of 2400 lockers and their color
number_lockers=2400
colors=['red', 'white', 'yellow', 'blue']
ce="\033[0m"

for locker_number in range(1, number_lockers+1, 1):
    color = colors[locker_number % 4 - 1]
    if color=="red":
        cs="\033[31m"
    if color=="yellow":
        cs="\033[33m"
    if color=="blue":
        cs="\033[34m"
    if color=="white":
        cs="\033[37m"

    print(f"locker No.{locker_number}, {cs+ color.center(50, '.').upper()+ce}")

```

# Task 2
## Python code

```.py
#task 2: print the color of the inputted locker number
colors=['red', 'white', 'yellow', 'blue']
locker_number = int(input('please input your locker number from 1 to 2400: '))
if locker_number<0 or locker_number>2400:
    locker_number = int(input('please input your locker number from 1 to 2400: '))
color=colors[locker_number % 4 -1]
print(f'Your locker is {color.upper()}')
```
