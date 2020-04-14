### ①　Unit 3:
in my record of tasks inventory

### ②　Coding practice:
**Q1**
```
s = input("Input a string")
d=l=0
for c in s:
    if c.isdigit():
        d=d+1
    else if c.isalpha():
        l=l+1
    else:
        pass
print("letters", l)
print("digits", d)
```

**Q2**
```
n=int(input("Enter a number:"))
d={x:x*x for x in range(1,n+1)}
print(d)
```

**Q3**
```
items = input("Input comma separated sequence of words")
words = [word for word in items.split(",")]
print(",".join(sorted(list(set(words)))))
```

**Q4**

**Q5**
```
n=int(input("Enter your dogs age:"))
young=n*10.5
old=2*10.5 + 4*(n-2)
if n > 2:
    print("your dogs age is {} years old".format(old))
elif n <= 2:
    print("your dogs age is {} years old".format(young))
```
**Q6**



### ③　Syllabus Questions:
**Q1** In order to dsign an app for mobile devices, it is crucial to think about the letter and font sizes.
there are some people who has visus senilis or some other visual problems.

**Q2**
A, B,	A and B,	C,	AB nor C

0	0	0	0	1

0	1	0	0	1

1	0	0	1	0

1	1	1	1	0

**Q3**
Protocol means a set of rules or procedures for transmitting data between electronic devices.

**Q4**
A very fast Von Neumann CPU has several slot of "registers." Register is a role of a box with very useful data stored for
the CPU. These data allows CPU to "fetch", "decode" and "execute" the instructions held in RAM that are part of the program.

**Q5**
I didn't get the question.
