# Record of Task

This table reflects the five stages of design: Planning, design, development, testing and implementation.

| Task # | Planned Action | Expected outcome | Time Estimated | Target Completion | Criteria |
|--------|----------------|------------------|----------------|-------------------|----------|
|    1   | **Planning:** meeting with client for the first conversation | Asked basic questions to get some ideas about the offer | 30 min |                   |          |
|    2   |                |                  |                |                   |          |
|    3   |                |                  |                |                   |          |

Table of contents
----
1. [Planning](#Planning)
1. [Design](#Design)
1. [Development](#Development)
1. [Testing](#Testing)

Planning
-------

Design
-----

Development
-----

**hashlib**
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

**Registration**
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
**manipulating strings**

Testing
-----
