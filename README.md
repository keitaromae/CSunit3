# Record of Task

This table reflects the five stages of design: Planning, design, development, testing and implementation.

| Task # | Planned Action | Expected outcome | Time Estimated | Target Completion | Criteria |
|--------|----------------|------------------|----------------|-------------------|----------|
|    1   | **Planning:** meeting with client for the first conversation | Asked basic questions to get some ideas about the offer | 30 min |         yes          |     A     |
|    2   | **Planning:** meeting with client to check our success criteria and measurabe outcomes | Got some several additions to my criteria | 10 min |          yes         |      A    |
|    3   | **Designing:** meeting with my client to sort out their favorite UI designs | Creating rough draft on Qt designer                 | 50 mins total including designing time               |       yes            |    B      |
|    4   | **Designing:** Brushing up all the UI designs by actually converting it into pycharm | Export from Qt convert it into pycharm | 1hr50min | yes | B & C|
|    5   | **Development:** Editting few codes on pycharm. ex.changing button placements and adding links to them | More of a connecting several "pages" I created on Qt into one solid program by using pycharm | 2hr apx |yes | C |
|    6   | **Development:** Adding more features, secured logins and tables that suits client's needs | hashlib password and login system, simple graph chart to make inventory visible | 2hrs apx |yes | C |
|    7   | **Testing:** testing and trouble shooting | I did the first test on checking button links and pages appearing | 1hr |yes | D |
|    8   | **Testing:** testing and trouble shooting | login system and editting inventory graph | 3hrs |yes | D |
|    9   | **Evaluation:** reviewing my own work using success criteria I made with my client | Make sure all the box will be ticked without any problem | 5 mins |yes | E? |

Table of contents
----
1. [Planning](#Planning)
1. [Design](#Design)
1. [Development](#Development)
1. [Testing](#Testing)
1. [Evaluation](#Evaluation)
1. [References](#References)

Planning
-------
### Defining problem
Knowing the issues that client is facing and reason why they need this program for.
This is the email sent from my client.
```
Hello, Keitaro

Currently, my desk is messy because of a lot of books and I'm not really good at organizing my stuff. 
At the moment, there isno way to organize my books. Besides, I would like to categorize these books 
and have something like a database so that I can pick up a proper book whenever I want. In the database,
I want you to record the title, the author, the genre, pages and until where I read. 
Lastly, I want the system to be only accessed by me!
Thank you!

Fuma Ito
```

### Solution proposed

Creating online database that can store books virtually. This database should show every book that he owns and several data of each of his books. It should organize books by its title, author, genre and pages that client last read. This database will be only used by one user(Fuma).

### Success criteria
**Book inventory:**
These are the measurable outcomes

1. Database can be edit by the user. (del, add and rewrite)
1. Every book should have labeled title, author, genre and pages.
1. Database should be organized by its genre or by an author.
1. Every instruction or manpage will be written in easy language not in technical words.
1. Need software that can be used by himself. (secured account)

### Connecting a database file
**Creating Fuma's Book table:**
Creating the table by using .csv db
By deciding the number of list at first and then inputting your clients data.
ex. "La metamorfosi....."
```
title, year, author, pg#, last_read, last_pg, genre
La metamorfosi, 1915, Franz Kafka, ?, ?, ?, Fantasy Fiction
Le Petit Prince, 1943, Saint-Exupery, ?, ?, ?, juvenile literature
```

Design
-----
### Ui Concept
Ui design concept of "the fumabook" are inside the folder "the fumabook" unit 3 repository.


Development
-----

### hashlib
```
import myLib

myLib.me()

# Define cities' location
cities = [(3, 5), (9, 10), (7, 8), (15, 7)]


for index in range(4):
    cityA = cities[index]
    for index_2 in range(index+1, 4):
        cityB = cities[index_2]
        d = myLib.distance(target=cityA, origin=cityB)
        print("Distance between city {} and {} is {}".format(index, index_2, d))

import hashlib
import os
# testing the hash algorithm
password = "123456"
salt = os.urandom(32)
key = hashlib.pbkdf2_hmac('sha256', password.encode('utf-8'), salt, 1000)
print(key)

password_entered = "12345"
key_check = hashlib.pbkdf2_hmac('sha256', password_entered.encode('utf-8'), salt, 1000)
if key == key_check:
    print("Login successful")
else:
    print("Login invalid")
```

### Registration
1. Input username
2. Input password
3. Confirm password
4. Generate salt
5. Use the hash lib function
6. store info user_dict
```
import hashlib
import os
import binascii
import getpass


user = {'username': None, 'password-hash': None, 'salt': None}

print("1 - Register ")
print("2 - Log in")
print("3 - Exit")

opt = 10
while opt > 3:
    opt = int(input("Enter option (1, 2, or 3) "))

# User entered #1 Registration

username = input("Enter your username: ")
confirmed = False
while not confirmed:
    password = ("Enter your password: ")
    password_test = ("Confirm your password: ")
    if password == password_test:
        confirmed = True

    # confirmed = True if password_test == password else False
salt = os.urandom(32) # 32 bytes
key = hashlib.pbkdf2_hmac('sha256', password.encode('utf-8'), salt, 1000)
# This library is converting bits on the key into characters for us to read
print(binascii.hexlify(key))

user['username'] = username
user['password-hash'] = key
user['salt'] = salt
```
I've imported "getpass" but it didn't work out in my code.
Getpass is the line that makes your inputted password non-visible.

### Manipulating strings
```
# Question 1
# open the txt file
file = open("extract", "r")
extract = file.read()

print(extract)

words = extract.split()
print(words)
print("Answer to Q1: ", len(words), "words")
print(" ")

# Question 2
keywords = ('house', 'worker', 'master', 'hard', 'responsible', 'skillful')

for kwd in keywords:
    print("Checking for word {} in the text: ".format(kwd))
    print(kwd in extract)
    print(" ")

# Question 3
name = 'john'
print(f"hello {name}")
print(" ")
countAlpha = 0
for letter in extract:
    if letter.isalpha():
        countAlpha += 1

print(f'There are {countAlpha} letters out of {len(extract)} total.')

# Q4. Make the text all lowercase.
print(extract.upper()) # every thing in to upper case extract.capitalize makes first letter upper
print(extract.lower()) # every letter in lower case

# Q5 text longer than 5 characters
wordsLong = list(filter(lambda x: len(x)>5, words))
len(wordsLong)
print(len(wordsLong))
print('#'.join(wordsLong))

# code below does the same
# for word in words:
    # if len(word)>5:
        # print('#', word)

# Question 6
total = 0
for letter in extract:
    total += ord(letter)

print(total)
```
### Encrypting the message
```
print("This program encrypts the inputted letter into unicode")
print("Type your message here: ")

message = input()
print("Type your additional # here: ")
add = int(input())

for letter in message:
    newletter = chr(ord(letter) + add)
    print(newletter)
```

### Bank account
```
customer1 = {'FirstName': 'Filip',
             'LastName': 'Keitaro',
             'AccNum': '00001',
             'PIN': '1119',
             'Balance': '5B',
             'Age': '18',
             'contact': 'filip@keitaro.jp'}

def deposit(CustomerDict, Amount):
    # This function deposits amount in the customer dictionary
    CustomerDict['Balance'] += Amount
    print(f'New balance is {CustomerDict["Balance"]}')

def checkbalance(CustomerDict):
    # This function prints the amount of balance left in the account
    print(f'Your current balance is {CustomerDict["Balance"]}')

def withdraw(CustomerDict, Amount):
    # This function subtracts inputted amount from the bank account
    CustomerDict['Balance'] - Amount
    print(f'You withdraw {Amount} and {CustomerDict["Balance"]} left in Account')
```
### My first OOP
```
class Dogs:
    # Class
    species = 'mammal'
    # Initializer
    def __init__(self, name, age):
        self.name = name
        self.age = age

def get_biggest_number (*args):
    biggest = max(args)
    print(f'The oldest is {biggest}')

# Instantiate the Dog object
a = Dogs("Kei", 3)
b = Dogs("Taro", 2)
c = Dogs("Mae", 7)

get_biggest_number(a.age, b.age, c.age)
```

### Maxima.py
```
import math

import matplotlib.pyplot as plt


step = 0.001
max_t = 50
number_points = max_t / step
t = [0]
for n in range(number_points):
    t.append(t[-1] + step)
f = [abs(3*math.sin(0.3*x)) for x in t]

plt.plot(t, f)
plt.show()

diff = [0, 0]
zeros = [0, 0]
for x in range(number_points-1):
    diff.append(f[x]-f[x+1])



print(len(t), len(diff))
plt.plot(t, diff, 'r')
plt.show()
```

### thefumabook_ui.py
trouble shooting and discovering way to show new windows.
```
from thefumabook_ui import Ui_MainWindow
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow
from register_ui import Ui_register_2


class thefumabook_ui(QMainWindow, Ui_MainWindow):
    def __init__(self, parent=None):
        super(thefumabook_ui, self).__init__(parent)
        self.setupUi(self)

        # call back
        self.username_in.setPlaceholderText(" Enter username")
        self.password_in.setPlaceholderText(" Enter password")
        self.pushButton_register.clicked.connect(self.regpg)

    def regpg(self):
        page = register(self)
        page.show()

class register(Ui_register_2):
    def __init__(self, parent=None):
        super(register, self).__init__(parent)
        self.setupUi(self)

        # call back
        self.username_in.setPlaceholderText(" Enter username")
        self.password_in.setPlaceholderText(" Enter password")
        self.pushButton_back.clicked.connect(self.mainmenu)

    def mainmenu(self):
        page = thefumabook_ui()
        page.show()





# small program to start the application
app = QApplication(sys.argv)
form = thefumabook_ui()
form.show()
app.exec_()
```

### Log in password
created log in system by using hash code and salt protection.
```
import hashlib, binascii, os

def hash_password(password):
    """Hash a password for storing"""
    salt = hashlib.sha256(os.urandom(60)).hexdigest().encode('ascii')
    pwdhash = hashlib.pbkdf2_hmac('sha512', pssword.encode('utf-8'), salt, 100000)
    pedhash = binascii.hexlify(pwdhash)
    return (salt + pwdhash).decode('ascii')

def verify_password(stored_password, provided_password):
    """Verify a stored password against one provided by user"""
    salt = stored_password[:64]
    stored_password = stored_password[64:-1]
    pwdhash = hashlib.pbkdf2_hmac('sha512', provided_password.encode(utf-8), salt.encode('ascii'), 100000)
    pwdhash =binascii.hexlify(pwdhash).decode('ascii')
    return pwdhash == stored_password
```


Testing
-----
### Connecting link to the button
**Tested if the button actually works**

In my previous work, I added some page links to button "register" and "exit."

- As you can see from the code below, I defined regpg which will open new tab.
```
class thefumabook_ui(QMainWindow, Ui_MainWindow):
    def __init__(self, parent=None):
        super(thefumabook_ui, self).__init__(parent)
        self.setupUi(self)

        # call back
        self.username_in.setPlaceholderText(" Enter username")
        self.password_in.setPlaceholderText(" Enter password")
        self.pushButton_register.clicked.connect(self.regpg)
        self.pushButton_exit.clicked.connect(self.close)


    def regpg(self):
        page = register(self)
        page.show()
```

- Although button didn't work as I wished. So I thought something is wrong with my register_ui.py page.
\original code
```
class Ui_register_2(MainWindow):

    def setupUi(self, register_2):
        register_2.setObjectName("register_2")
        register_2.resize(804, 600)
        register_2.setStyleSheet("background-color: rgb(255, 255, 255);")
        self.label_thefumabook_2 = QtWidgets.QLabel(register_2)
        self.label_thefumabook_2.setGeometry(QtCore.QRect(210, 130, 361, 71))
        self.label_thefumabook_2.setStyleSheet("font: 50pt \"Facebook Letter Faces\";\n"
"color: rgb(80, 98, 168);\n"
"\n"
"\n"
"")
```
- realized the error on first line
instead of ```class Ui_register_2(MainWindow):```
it should be ```class Ui_register_2(QDialog):```

- After rewriting this 1 line it worked fine.

Evaluation
-------
### Summary

**Book inventory:**
These are the measurable outcomes

1. Database can be edit by the user. (del, add and rewrite)
1. Every book should have labeled title, author, genre and pages.
1. Database should be organized by its genre or by an author.
1. Every instruction or manpage will be written in easy language not in technical words.
1. Need software that can be used by himself. (secured account)

Regarding to this success criteria, program "The fumabook" is acquiring its benchline. 
Every book owned by Fuma can be add, delete and reedit by him. All of its information will be stored and also shown by graph on database. He has his own secured account and password created by hashlib. This program also comes with easy, understandable
instruction manual without any terminologies.


References
-------
