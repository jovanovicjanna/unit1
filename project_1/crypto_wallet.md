# Unit 1 project - Crypto Wallet
![](cryptogif.gif)  
<sub>Illustration for Glenn Harvey</sub>
# Criterion A: Planning

## Problem definition

Ms. Sato is a local trader who is interested in the emerging market of cryptocurrencies. She has started to buy and sell electronic currencies, however at the moment she is tracking all his transaction using a ledger in a spreadsheet which is starting to become burdensome and too disorganized. It is also difficult for Ms Sato to find past transactions or important statistics about the currency. Ms Sato is in need of a digital ledger that helps her track the amount of the cryptocurrency, the transactions, along with useful statistics. 

Apart for this requirements, Ms Sato is open to explore a cryptocurrency selected by the developer.

An example of the data stored is 

| Date | Description | Category | Amount  |
|------|-------------|----------|---------|
| Sep 23 2022 | bought a house | Expenses | 10 BTC |
| Sep 24 2022 | food for house celebration | Food | 0.000001 BTC |

## Proposed Solution

Design statement:
I will to design and make a digital ledger for a client who is local trader. The digital ledger will be about keeping track of cryptocurrency transactions and is constructed using the software Python. It will take one week to make and will be evaluated according to the criteria listed bellow.

### Justifying the softwer selected
I will be using python because it is easy to learn and use, codes can be easily written and executed much faster than other programming languages. Furthermore, Python is one of the most user-friendly programming languages since it has a simple syntax and is not overly complex, putting more of an emphasis on natural language.

### Justifying the structure of the proposal solution
I'll create a Python project in Pycharm using a First Screen python file to implement the digital ledger. Several functions that have already been defined in my library Python file will be called by this file. Programming is made simpler to manage and adjust when various functions are written individually. As a result, code will be simpler to read and more approachable.

## What is LiteCoin?

Litecoin is a cryptocurrency founded in 2011, two years after Bitcoin, by a former Google engineer named Charlie Lee.
It shares similar features with Bitcoin but has a different algorithm. The cryptocurrency's goal is to become a medium for daily transactions.
Litecoin has a faster transaction processing time compared to Bitcoin.

McFarlane, G. (2022, April 14). What is Litecoin (LTC)? Investopedia. Retrieved September 29, 2022, from https://www.investopedia.com/articles/investing/040515/what-litecoin-and-how-does-it-work.asp 

## Success Criteria
1. The electronic ledger is a text-based software (Runs in the Terminal).
2. The electronic ledger display the basic description of the cyrptocurrency selected.
3. The electronic ledger allows to enter, withdraw and record transactions.
4. The electronic ledger allows user to enter just if the password is corect. 
5. The electronic ledger display 10 biggest transactions.
6. The electronic ledger show transactions of last month.
# Criterion B: Design
## System diagram

![](Screen%20Shot%202022-10-09%20at%2019.06.53.png)

Fig 1. System diagram of this program

## Flow diagrams
![](big.jpg)

Fig 2. Flow diagram of the biggest transaction function.

![](log.jpg)

Fig 3. Flow diagram of the login function.

![](reg.jpg)

Fig 4. Flow diagram of the register or login function.

# Criterion C: Development
## Code
```.py
def validate_int_input(msg:str)->int:
    number=input(msg)
    while not number.isdigit():
        number = input( f'error, {msg}')
    return int(number)
cs_red = "\33[0;31m"
cs_cyan = "\33[0;36m"
end_code = "\033[00m"

# first thing that would appear, choosing between those two
def register_or_login()->int:
    welcome_msg = "Welcome to your digital ledger".center(50, '*')
    prompt_msg = "Now please enter an option [1-2]"

    content = "options"
    menu ='''1. Register
    2. Login
    '''
    print(cs_cyan, welcome_msg, end_code)
    print(content.center(50))
    print(menu)
    option = validate_int_input(prompt_msg)

    while option < 1 or option > 2:
        option = validate_int_input(f"{cs_red}invalid option, {prompt_msg}{end_code}")
    return option

# option 1 register
def register (username:str,password:str):
    with open("db.csv", "w") as file:
        file.write(f"{username},{password} \n")
        registered= "Well done! You are registered. Now you can login."
        print(cs_cyan, registered, end_code)

# option 2 login
def login(username:str, password:str)->bool:
    with open("db.csv", "r") as file:
        register_data = file.read().strip()
        register_data1 = register_data.split(",")
        if username==register_data1[0] and password==register_data1[1]:
            return True
        else:
            return False
        output = False
        return output
# new options
def my_wallet():
    login_msg = "Well done! You are logged in! Let's start."
    prompt_msg1 = "please enter an option [1-4]"
    content1 = "options"
    menu1 ='''1. Basic description of cryptocurrency
    2. Create a transaction
    3. Show 10 biggest transactions
    4. Show transactions of last month
    '''
    print(cs_cyan, login_msg, end_code)
    print(prompt_msg1)
    print(content1.center)
    print(menu1)
    option1 = validate_int_input(prompt_msg1)

    while option1 < 1 or option1 > 4:
        option1 = validate_int_input(f"{cs_red}invalid option, {prompt_msg1}{end_code}")
        return option1
# Basic description of cryptocurrency
if option1==1:
    print(cs_cyan, "1. Basic description of cryptocurrency ", end_code)
    print("What is LiteCoin?")
    print('''
    Litecoin is a cryptocurrency founded in 2011, two years after Bitcoin,
    by a former Google engineer named Charlie Lee. It shares similar features 
    with Bitcoin but has a different algorithm. The cryptocurrency's goal is 
    to become a medium for daily transactions. Litecoin has a faster transaction
    processing time compared to Bitcoin.
    ''')
# Create a transaction
def deposit(date:str, description:str, category:str, amount:str):
    '''
    db.csv
    :param date: date a string
    :param description: description a string
    :param category: category a string
    :param amount: amount a string
    :return: nothing
    '''
    file = open("db.csv", "a")
    file.write(f"{date}{description}{category}{amount}\n")
def withdrawal(date:str, description:str, category:str, amount:str):
    '''
    db.csv
    :param date: date a string
    :param description: description a string
    :param category: category a string
    :param amount: amount a string
    :return: nothing
    '''
    file = open("db.csv", "a")
    file.write(f"{date}{description}{category}{amount}\n")
if option1==2:
    transaction = int(input("Type (1) for deposit and (2) for withdrawal.")
    if transaction == 1:
        enter_date= input("Enter today's date:")
        enter_description=input("Enter description of deposit:")
        enter_category=input("Enter category of deposit:")
        enter_amount=input("Enter amount of deposit:")
        deposit(date=enter_date, description=enter_description, category=enter_category, amount=enter_amount)
        print({f"{cs_cyan} Deposit is successfully entered! {end_code}"})
    if transaction == 2:
        enter_date = input("Enter today's date:")
    enter_description = input("Enter description of withdrawal:")
    enter_category = input("Enter category of withdrawal:")
    enter_amount = input("Enter amount of withdrawal:")
    deposit(date=enter_date, description=enter_description, category=enter_category, amount=enter_amount)
    print({f"{cs_cyan} Withdrawal is successfully entered! {end_code}"})
delete_transaction = input("Type (1) for entering transaction or (2) to quit:")
# 10 biggest transactions
with open("db.csv","r") as file:
    for line in ("db.csv").readlines


# 10 last transactions
```


