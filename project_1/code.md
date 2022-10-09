# Code

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
