# Snakify UNIT 2

## Integer and float numbers

### Last digit of integer

#### code

```.py
number = int(input())
last_digit = number % 10
print (last_digit)
```

#### test results

![](lastdigit.png)

### Two digits

#### code

```.py
number = int(input())
a= number%10
b=number//10%10
print(str(b) + " " + str(a))
```

#### test results

### Swap digits

#### code

```.py
number = int(input())
a = number%10
b = number//10
print(str(a) + str(b))
```
#### test results

### last two digits

#### code

```.py
a=int(input())
x=a%100
print(x)
```
#### Tens digit

### Tens digit

#### code

```.py
number = int(input())
tens_digit = (number//10%10)
print(tens_digit)
```

#### test results

![](tens.png)

### sum of digits

#### code

```.py
number = int(input())
last_digit = number % 10
second_digit = number // 10 % 10
third_digit = number // 100
sum = (last_digit + second_digit + third_digit)
print(sum)
```
#### test results

![](sum.png)

### reverse three digits

#### code

```.py
number = int(input())
j = number%10
d = number//10%10
s = number//100
print(str(j) + str(d) + str(s))
```
#### test results

### merge two numbers

#### code

```.py
a= int(input())
b=int(input())
d1= a%10
d2= a//10
d3= b%10
d4=b//10
print(str(d2) + str(d4) + str(d1) + str(d3))
```
#### test results

### cyclic rotation

#### code

```.py
a=int(input())
j=a%10
d=a//10%10
s=a//100%10
h=a//1000
print(str(d) + str(j) + str(h) + str(s))
```
#### test results

### fractional part

#### code

```.py
number = float(input())
print(number%1)
```
#### test results

![](fractional_part.png)

### car route

#### code

```.py
from math import ceil
n = int(input())
m = int(input())
days = ceil (m/n)
print (days)
```
#### test results

![](car_route.png)

### day of the week

#### code

```.py
K = int(input())
print((K-4)%7)
```

#### test results

### digital clock

#### code

```.py
N=int(input())
hours = N//60
minutes = N - (hours * 60)
print(hours,minutes)
```

#### test results

### total cost

#### code

```.py
A = int(input())
B = int(input())
N = int(input())
price = ((A*100) + B) * N
dollars = price//100
cents = price - (dollars*100)
print(dollars, cents)
```

#### test results

### century

#### code
 ```.py
 from math import ceil
year = int(input())
print(ceil(year/100))
```
#### test results

### snail

#### code

```.py
from math import ceil
H = int(input())
A = int(input())
B = int(input())
C = ceil((H-A)/(A-B)) + 1
print(C)
```
#### test results

### clock face -1

#### code

```.py
H = int(input())
M = int(input())
S = int(input())
hours_to_seconds = H * 3600
minutes_to_seconds = M * 60
total_seconds = hours_to_seconds + minutes_to_seconds + S
print ((total_seconds) / 120)
```
#### test results

### clock face -2

#### code

```.py
minutes = float(input())
print(minutes % 30 *12)
```
#### test results
