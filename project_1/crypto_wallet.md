# Unit 1 project - Crypto Wallet
![](ltc1.webp)  
<sub>Litecoin by Team Luno</sub>
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
![](big.png)

Fig 2. Flow diagram of the biggest transaction function.

![](log.png)

Fig 3. Flow diagram of the login function.

![](reg.png)

Fig 4. Flow diagram of the register or login function.

## Record of Tasks
| Task No | Planned Action                                                | Planned Outcome                                                                                                 | Time estimate | Target completion date | Criterion |
|---------|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|---------------|------------------------|-----------|
| 1       | Create system diagram                                         | To have a clear idea of the hardware and software requirements for the proposed solution.                        | 10min         | Sep 24                 | B         |
| 2       | Meet with the client                                        | Discuss the issues that the client is experiencing and develop a plan to assist the client in resolving the issues.                      | 20min         | Sep 24                 | A         |
| 3      | Write a problem solution for the client                                       | An explanation that makes sence for the client and developer.| 15min         | Sep 24                 | A         |
| 4      | Write success criterias                                       | A clear success criteria that suits the client and developer. | 10min         | Sep 24                 | A         |
| 5      | Create a registration and login system                                       | To develop a program that allows the client to register and login setting up a username and password. | 45min         | Sep 25                 | C         |
| 6      | Code main menu| To allow client choosing between 2 different options from the menu and interacting with the program.| 30min         | Sep 26                 | C         |
| 7      | Code a menu for transactions| Code menu that allows client to choose between 2 options: deposit or withdrawal. | 30min         | Sep 27                 | C         |
| 8      | Code function that allows client to see the biggest transaction| Create a code that allows client to see an amount of the biggest transaction made. | 50min         | Sep 29                 | C         |
| 9      | Code function that allows client to see last 5 transactions| Create a code that allows client to see 5 latest transactions entered. | 15min         | Sep 30                 | C         |
| 10      | Validate client's input for all option choices| Create a code that that would make sure that client's inputs follow certin requirements. | 1hr        | Oct 1                 | C         |
| 11      | Draw flow diagrams| Draw flow diagrams to have clear idea of functions' structure. | 1hr        | Oct 3                 | B        |
| 12      | Meet with the client| Have a feedback about the program's present state. | 20min        | Oct 7                 | B         |
| 13      | Final fix| Final changes based on the customer's feedback. | 2hrs        | Oct 9                 | C         |
# Criterion C: Development
## Techniques used:
1. Functions
2. For/While loops
3. Input validation
4. If statements
5. 
## Code

## Main screen
```.py
from my_library import *
# welcome to your digital ledger
welcome()
# register or login
register_or_login()
# options
login_msg = "Well done! You are logged in! Let's start."
prompt_msg1 = "Please enter an option [1-4]"
content1 = "OPTIONS"
menu1 = '''
    1. Basic description of cryptocurrency
    2. Create a transaction
    3. Show biggest transaction
    4. Show 5 last transactions
    '''
enter_option = " Enter your option: "
print(cs_green, login_msg, end_code)
print(content1.center(50))
print(menu1)
print(cs_cyan, prompt_msg1, end_code)
option1 = validate_int_input(enter_option)
while option1 < 1 or option1 > 4:
    option1 = validate_int_input(f"{cs_red} Invalid option. Please enter an option [1-4]: {end_code}")
# basic description of cryptocurrency
if option1 == 1:
    basic_description()
# deposit or withdrawal
if option1 == 2:
    transaction()
# the biggest transaction
if option1==3:
    biggest_transaction()
# 5 last transactions
if option1==4:
    recent_transactions()
```

## my library

```.py
import csv
cs_red = "\33[0;31m"
cs_green = "\33[0;32m"
cs_cyan = "\33[0;36m"
end_code = "\033[00m"

# input validation function
def validate_int_input(msg: str) -> int:
    number = input(msg)
    while not number.isdigit():
        number = input(f' {cs_red}Error.{msg}{end_code}')
    return int(number)

# welcome function
def welcome():
    welcome_msg = "WELCOME TO YOUR DIGITAL LEDGER".center(50, '*')
    prompt_msg = "Please enter an option [1-2]"
    content = "OPTIONS"
    menu = '''
    1. Register
    2. Login
        '''
    print(cs_cyan, welcome_msg, end_code)
    print(content.center(50))
    print(menu)
    print(cs_cyan, prompt_msg, end_code)

# register or login
def register_or_login():
    option = validate_int_input(" Enter an option: ")
    while option < 1 or option > 2:
        option = validate_int_input(f"{cs_red} Invalid option. Please enter an option [1-2]: {end_code}")
    if option == 1:
        uname = input(" Enter new username: ")
        pwd = input(" Enter new password: ")
        register(username=uname, password=pwd)
    uname = input(" Enter username: ")
    pwd = input(" Enter password: ")
    result = login(username=uname, password=pwd)
    if result == False:
        print(f"{cs_red} You have entered an invalid username or password.{end_code}")
        exit()

# register
def register(username: str, password: str):
    with open("users.csv", "w") as file:
        file.write(f"{username},{password} \n")
        registered = "Well done! You are registered. Now you can login."
        print(cs_green, registered, end_code)

# login
def login(username: str, password: str) -> bool:
    output = False
    with open("users.csv", "r") as file:
        all_users=file.readlines()
        for user in all_users:
            register_data = user.strip()
            register_data1 = register_data.split(",")
            if username == register_data1[0] and password == register_data1[1]:
                output = True
    return output

# basic description of cryptocurrency
def basic_description():
    print(cs_cyan, "1. Basic description of cryptocurrency ", end_code)
    print(" What is LiteCoin?")
    print('''
        Litecoin is a cryptocurrency founded in 2011, two years after Bitcoin,
        by a former Google engineer named Charlie Lee. It shares similar features 
        with Bitcoin but has a different algorithm. The cryptocurrency's goal is 
        to become a medium for daily transactions. Litecoin has a faster transaction
        processing time compared to Bitcoin.
        ''')

# transaction function
def transaction():
    transaction = validate_int_input(" Enter 1 for deposit or 2 for withdrawal: ")
    while transaction < 1 or transaction > 2:
        transaction = validate_int_input(f"{cs_red} Invalid option. Please enter an option [1-2]: {end_code}")
    if transaction == 1:
        enter_date = input(" Enter today's date (DD/MM/YYYY): ")
        enter_description = input(" Enter description of deposit: ")
        enter_category = input(" Enter category of deposit: ")
        enter_amount = input(" Enter amount of deposit (LTC): ")
        deposit(date=enter_date, description=enter_description, category=enter_category, amount=enter_amount)
        print(f"{cs_green} Deposit is successfully entered!{end_code}")

    if transaction == 2:
        enter_date = input(" Enter today's date (DD/MM/YYYY): ")
        enter_description = input(" Enter description of withdrawal: ")
        enter_category = input(" Enter category of withdrawal: ")
        enter_amount = input(" Enter amount of withdrawal (LTC): ")
        withdrawal(date=enter_date, description=enter_description, category=enter_category, amount=enter_amount)
        print(f"{cs_green} Withdrawal is successfully entered! {end_code}")

# deposit function
def deposit(date: str, description: str, category: str, amount: str):
    '''
    db.csv
    :param date: date a string
    :param description: description a string
    :param category: category a string
    :param amount: amount a string
    :return: nothing
    '''
    file = open("db.csv", "a")
    file.write(f"{date},{description},{category},{amount}\n")
    file.close()

# withdrawal function
def withdrawal(date: str, description: str, category: str, amount: str):
    '''
    db.csv
    :param date: date a string
    :param description: description a string
    :param category: category a string
    :param amount: amount a string
    :return: nothing
    '''
    file = open("db.csv", "a")
    file.write(f"{date},{description},{category},{amount}\n")
    file.close()

# the biggest transaction
def biggest_transaction():
    with open('db.csv', 'r') as file:
        all_data = file.readlines()
        max_amount = -1
        count = 0
        for user in all_data:
            data_stripped = user.strip()
            data_list = data_stripped.split(",")
            #date = data_list[0]
            #description = data_list[1]
            #category = data_list[2]
            amount = data_list[3]
            if int(amount) > int(max_amount):
                max_amount = amount
            count +=1

    print(f" The amount of the biggest transaction is {max_amount}.")

# the last 5 transactions
def recent_transactions():
    # opening the csv file
    with(open('db.csv', "r")) as f:
        # reading the csv file
        data = list(csv.reader(f))
        # printing the last 5 items of the csv file (:number means counting backwards and 5t the number of items)
        print(data[-5:])
```
## Register and login system
```.py
# register or login
def register_or_login():
    option = validate_int_input(" Enter an option: ")
    while option < 1 or option > 2:
        option = validate_int_input(f"{cs_red} Invalid option. Please enter an option [1-2]: {end_code}")
    if option == 1:
        uname = input(" Enter new username: ")
        pwd = input(" Enter new password: ")
        register(username=uname, password=pwd)
    uname = input(" Enter username: ")
    pwd = input(" Enter password: ")
    result = login(username=uname, password=pwd)
    if result == False:
        print(f"{cs_red} You have entered an invalid username or password.{end_code}")
        exit()

# register
def register(username: str, password: str):
    with open("users.csv", "w") as file:
        file.write(f"{username},{password} \n")
        registered = "Well done! You are registered. Now you can login."
        print(cs_green, registered, end_code)

# login
def login(username: str, password: str) -> bool:
    output = False
    with open("users.csv", "r") as file:
        all_users=file.readlines()
        for user in all_users:
            register_data = user.strip()
            register_data1 = register_data.split(",")
            if username == register_data1[0] and password == register_data1[1]:
                output = True
    return output
```
Making a registration and login system 
## Video of the program
[Video of the program](video.mov)
