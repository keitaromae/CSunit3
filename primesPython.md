|No.|Prime number in python      |
|-|------------- |
|①| First code, simply using for loop to check every possibility and list out the answers. **although it took so much time**  | 
|②| Second code, using for loop to check out until the square root of the number this program made the entire process more simple and efficient. |
|③| Last code, added some line that tests only odd divisors when the n is an even number. This makes the program to do less work. |

```
import math
def is_prime_v1(n)
if n == 1:
        return False # 1 is not prime
for d in range(2, n):
        if n % d == 0:
            return False
return True

def is_prime_v2(n):
    if n == 1:
        return False # 1 is not prime

max_divisor = math.floor(math.sqrt(n))
for d in range(2, 1 + max_divisor):
        If n % d == 0:
            return False
return True

def is_prime_v3(n):
    if n == 1:
        return False # 1 is not prime
    if n == 2:
        return True
    if n > 2 and n % 2 == 0:
        return False
    return True
    
    
for n in range (1, 21)
  print(n, is_prime_v3(n))
```
