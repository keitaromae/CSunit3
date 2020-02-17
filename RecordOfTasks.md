# Record of Task

This table reflects the five stages of design: Planning, design, development, testing and implementation.

| Task # | Planned Action | Expected outcome | Time Estimated | Target Completion | Criteria |
|--------|----------------|------------------|----------------|-------------------|----------|
|    1   | **Planning:** meeting with client for the first conversation | Asked basic questions to get some ideas about the offer | 30 min |                   |     A     |
|    2   | **Planning:** meeting with client to check our success criteria and measurabe outcomes | Got some several additions to my criteria | 10 min |                   |      A    |
|    3   |                |                  |                |                   |          |

Table of contents
----
1. [Planning](#Planning)
1. [Design](#Design)
1. [Development](#Development)
1. [Testing](#Testing)

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

These are measurable outcomes

1. Database can be edit by the user. (del, add and rewrite)
1. Every book should have labeled title, author, genre and pages.
1. Database should be organized by its genre or by an author.
1. Every instruction or manpage will be written in easy language not in technical words.
1. Need software that can be used by himself. (secured account)

Design
-----

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

Testing
-----
