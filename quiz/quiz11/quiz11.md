# Quiz 11: Create a function that shows the days of your birthday’s month for the year 2022.
## Code
```.py
def bestmonth (month:int)->str:
    out = " "
    dayofweek = ["We","Th","Fr","Sa","Su","Mo","Tu"]
    for i in range(1,32):
        days = f"{dayofweek[i%7]} {i} \n"
        out += days
    return out
month = 30
test1 = bestmonth(month)
print (test1)
```
## Test
![](Screen%20Shot%202022-10-10%20at%2020.10.52.png)


