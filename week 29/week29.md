### ①　Unit 3:

***UPDATES ON MY "record of tasks" md***

### ②　Coding practice:
**Q1**
```
first = input("Enter your first name: ")
last = input("Enter your last name: ")
num = int(input("Enter a random number from range 1-100: "))

if num > 100:
    print("Please input number less than 100 bigger than 0")

elif num < 0:
    print("Please input number bigger than 0 less than 100")

else:
    print("This is your new account")
    print("{}.{}{}@uwcisak.jp".format(first, last, num))
```

**Q2**
```
import uuid

x=int(input("How long your code to be: "))

def randompass(string_length = x):
    random = str(uuid.uuid4())
    random = random.upper()
    random = random.replace("-", "")
    return random[0:string_length]

print(randompass(x))
```

**Q3**
scatter graph:

comparison of Corona cases in japan and price of gold in both April's data.

**x axis:** number of cases in Japan

**y axis:** price of gold
```
import matplotlib.pyplot as pyplot
import csv

with open('covid-19.csv') as corona:
    data = []
    values = csv.reader(corona, delimiter=",")
    for row in values:
        data.append(row)

print(data)
#date
x = data[0]
#number
y = data[1]

pyplot.plot(x, y)
pyplot.xlabel('covid cases in Japan (per million)')
pyplot.ylabel('gold price (USD/oz)')

pyplot.show()
```

```
15, 17, 20, 23, 25, 28, 30, 30, 33, 36 #cases per million
1580, 1580, 1625, 1635, 1634, 1661, 1661, 1738, 1738, 1742 #(USD/oz)
```

### ③　Syllabus Questions:
Building my own PC

In 2020, it is possible to create a very high tier machine with a budget of 5000 USD. On this occasion, I would like to build 
gaming PC that can kick out at least 200 fps on benchmarks like, cs:go, fortninte, Apex legend etc....

MSI GeForce RTX 2080 TI GAMING X TRIO 11GB Graphics Card
(Link) - https://amzn.to/2XAEc16

Intel Core i9 9900K Processor
9th Gen BX80684I99900K
(Link) - https://amzn.to/2EJDXsW

NZXT Kraken X72 360mm AIO Liquid Cooler
(Link) - https://amzn.to/2Heeb1R

ASUS ROG Maximus XI Hero Gaming Motherboard 
(Link) - https://amzn.to/2UgSuBK

CORSAIR Vengeance RGB PRO 32GB DDR4 RAM 3200
(Link) - https://amzn.to/2tKJ6Lc

CORSAIR RM850x 80+ Gold Certified Power Supply
(Link) - https://amzn.to/2XBA0Ov

WD Blue 500GB SSD
(Link) - https://amzn.to/2HbKLkN

Seagate BarraCuda 2TB Hard Drive
(Link) - https://amzn.to/2SFYlij

NZXT H700i ATX Computer Case
(Link) - https://amzn.to/2XxNgUt

Total budget: apx $2500

RTX 2080 Ti 11GB for the GPU. ***GPU graphics processing unit is a specialized electronic circuit designed to rapidly manipulate and alter memory to accelerate the creation of images in a frame buffer intended for output to a display device.***

Intel core i9 9900K processor. ***electronic circuitry within a computer that executes instructions that make up a computer program.***

CORSAIR Vengeance RGB PRO 32GB DDR4 RAM 3200. ***form of computer memory that can be read and changed in any order, typically used to store working data and machine code.***

NZXT Kraken X72 360mm AIO Liquid Cooler. ***using NZXT's liquid cooler for our cooling system, compare to normal air cooling, it is more efficient and also visually attractive.***
