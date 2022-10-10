# Quiz 10: Create a function that produces the powers of ten from pico, to tera for a number provided as an input.

## Code
```.py
def powers_ten(quantity:int)->str:
    out = ""
    prefix = ["unit", "kilo", "mega", "giga", "tera" ]
    smaller_prefix = ["milli", "micro", "nano", "pico"]
    for power in range(4,-1,-1):
        value=f"{quantity}{'0' * 3 * power}".ljust(25) + prefix[power]
        out+= value + "\n"
    for power in range(0, 4, 1):
        value= f"0.00{'0' * 3 * power}{quantity}".ljust(25) + smaller_prefix[power]
        out += value +"\n"
    return out
out = powers_ten(quantity=1)
print(out)
```
## Test
![](Screen%20Shot%202022-10-10%20at%2018.51.35.png)

