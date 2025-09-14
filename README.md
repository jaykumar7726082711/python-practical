# python-practical 
## 1.a python program to find roots of quadratic equation 
```import cmath # Import cmath for handling complex numbers

def find_quadratic_roots(a, b, c):
    """
    Finds the roots of a quadratic equation ax^2 + bx + c = 0.

    Args:
        a (float): Coefficient of x^2.
        b (float): Coefficient of x.
        c (float): Constant term.

    Returns:
        tuple: A tuple containing the roots.
               If two distinct real roots, returns (root1, root2).
               If one real root (repeated), returns (root1,).
               If two complex roots, returns (root1, root2).
               Returns an empty tuple if 'a' is zero and 'b' is also zero (not a quadratic equation).
    """
    if a == 0:
        if b == 0:
            return () # Not a quadratic equation if a and b are both zero
        else:
            # Linear equation: bx + c = 0 => x = -c/b
            return (-c / b,)

    # Calculate the discriminant
    discriminant = (b**2) - 4 * a * c

    if discriminant > 0:
        # Two distinct real roots
        root1 = (-b - cmath.sqrt(discriminant)) / (2 * a)
        root2 = (-b + cmath.sqrt(discriminant)) / (2 * a)
        return root1, root2
    elif discriminant == 0:
        # One real root (repeated)
        root = -b / (2 * a)
        return root,
    else:
        # Two complex roots
        root1 = (-b - cmath.sqrt(discriminant)) / (2 * a)
        root2 = (-b + cmath.sqrt(discriminant)) / (2 * a)
        return root1, root2

# Example usage:
if __name__ == "__main__":
    print("Enter the coefficients of the quadratic equation (ax^2 + bx + c = 0):")
    try:
        a = float(input("Enter a: "))
        b = float(input("Enter b: "))
        c = float(input("Enter c: "))

        roots = find_quadratic_roots(a, b, c)

        if not roots:
            print("This is not a quadratic equation (a and b cannot both be zero).")
        elif len(roots) == 1:
            print(f"The equation has one real root: {roots[0]}")
        else:
            print(f"The roots of the equation are: {roots[0]} and {roots[1]}")

    except ValueError:
        print("Invalid input. Please enter numerical values for coefficients.")
```
# 2 . Write a program to accept a number 'n' and a. Check if 'n' is prime b. Generate all prime numbers till 'n' c. Generate first 'n' prime numbers This program may be done using functions
# Function to check if a number is prime
```
def is_prime(num):
    if num <= 1:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True


def primes_till_n(n):
    primes = []
    for i in range(2, n + 1):
        if is_prime(i):
            primes.append(i)
    return primes



def first_n_primes(n):
    primes = []
    num = 2
    while len(primes) < n:
        if is_prime(num):
            primes.append(num)
        num += 1
    return primes
n = int(input("Enter a number: "))

if is_prime(n):
    print(f"{n} is a Prime number.")
else:
    print(f"{n} is NOT a Prime number.")


print(f"Prime numbers till {n}: {primes_till_n(n)}")

print(f"First {n} prime numbers: {first_n_primes(n)}")
```
## 3 . Write a program to create a pyramid of the character **" and a reverse pyramid
```

def pyramid(n):
    """Function to print pyramid of *"""
    for i in range(1, n + 1):
        print(" " * (n - i) + "*" * (2 * i - 1))

def reverse_pyramid(n):
    """Function to print reverse pyramid of *"""
    for i in range(n, 0, -1):
        print(" " * (n - i) + "*" * (2 * i - 1))

# Main program
rows = int(input("Enter number of rows: "))

print("\nPyramid:")
pyramid(rows)

print("\nReverse Pyramid:")
reverse_pyramid(rows) 
```
## 4. Write a program that accepts a character and performs the following:



### a. print whether the character is a letter or numeric digit or a special character
```



ch = input("Enter a single character: ")

if len(ch) != 1:
    print("Please enter exactly one character.")
else:
    if ch.isalpha():
        print("It is a letter.")
    elif ch.isdigit():
        print("It is a numeric digit.")
    else:
        print("It is a special character.")
 ```
### b. if the character is a letter, print whether the letter is uppercase or lowercase
```


ch = input("Enter a single character: ")

if len(ch) != 1:
    print("Please enter exactly one character.")
else:
    if ch.isalpha():
        print("It is a letter.")
        if ch.isupper():
            print("The letter is uppercase.")
        else:
            print("The letter is lowercase.")
    elif ch.isdigit():
        print("It is a numeric digit.")
    else:
        print("It is a special character.")
```
### c.if the character is a numeric digit, prints its name in text (e.g., if input is 9, )
```

ch = input("Enter a single character: ")

if len(ch) != 1:
    print("Please enter exactly one character.")
else:
    if ch.isalpha():
        print("It is a letter.")
        if ch.isupper():
            print("The letter is uppercase.")
        else:
            print("The letter is lowercase.")

    elif ch.isdigit():
        print("It is a numeric digit.")
        digit_names = {
            '0': "zero",
            '1': "one",
            '2': "two",
            '3': "three",
            '4': "four",
            '5': "five",
            '6': "six",
            '7': "seven",
            '8': "eight",
            '9': "nine"
        }
        print(f"The digit name is: {digit_names[ch]}")

    else:
        print("It is a special character.")
```
## 5. Write a program to perform the following operations on a string

### a. Find the frequency of a character in a string.
# a. Frequency of a character
```
s = input("Enter a string: ")
ch = input("Enter a character: ")

count = s.count(ch)
print("Frequency of", ch, "=", count)
```
## b. Replace a character by another character in a string
```
s = input("Enter a string: ")
old = input("Enter character to replace: ")
new = input("Enter new character: ")

new_str = s.replace(old, new, 1)   # replace first occurrence
print("String after replacement:", new_str)
```

### c.Remove the first occurrence of a character
```
s = input("Enter a string: ")
ch = input("Enter a character to remove: ")

new_str = s.replace(ch, "", 1)
print("String after removing first occurrence:", new_str)
```

## d. Remove all occurrences of a character
```
s = input("Enter a string: ")
ch = input("Enter a character to remove: ")

new_str = s.replace(ch, "")
print("String after removing all occurrences:", new_str)

```


## 6. Write a program to swap the first n characters of two strings.
```
s1 = input("Enter first string: ")
s2 = input("Enter second string: ")
n = int(input("Enter number of characters to swap: "))

new_s1 = s2[:n] + s1[n:]
new_s2 = s1[:n] + s2[n:]

print("After swapping:")
print("String 1 =", new_s1)
print("String 2 =", new_s2)
```
## 7. Write a function that accepts two strings and returns the indices of all the occurrences of the second string in the first string as a list. If the second string is not present in the first string then it should return -1.
```

def find_occurrences(s, sub):
    indices = []
    start = 0
    while True:
        pos = s.find(sub, start)
        if pos == -1:
            break
        indices.append(pos)
        start = pos + 1
    return indices if indices else -1

s = input("Enter main string: ")
sub = input("Enter substring: ")
print("Occurrences =", find_occurrences(s, sub))
```
## 8. Write a program to create a list of the cubes of only the even integers appearing in the input list (may have elements of other types also) using the following:

### a. 'for' loop
```
lst = [1, 2, "hi", 4, 5, 6.5, 8]
cubes = []
for x in lst:
    if isinstance(x, int) and x % 2 == 0:
        cubes.append(x**3)
print("Cubes using for loop:", cubes)

## b. Using list comprehension

cubes2 = [x**3 for x in lst if isinstance(x, int) and x % 2 == 0]
print("Cubes using list comprehension:", cubes2)
```
## 9. Write a program to read a file



### a. Print the total number of characters, words and lines in the file.
```
filename = "input.txt"   # make sure this file exists

with open(filename, "r") as f:
    lines = f.readlines()
chars = sum(len(line) for line in lines)
words = sum(len(line.split()) for line in lines)
print("Characters:", chars)
print("Words:", words)
print("Lines:", len(lines))
```
### b. Calculate the frequency of each character in the file. Use a variable of dictionary type to maintain the count.

```
freq = {}
for line in lines:
    for ch in line:
        freq[ch] = freq.get(ch, 0) + 1
print("Character frequency:", freq)
```
### c. Print the words in reverse order.
```
all_words = " ".join(lines).split()
print("Words in reverse:", " ".join(all_words[::-1]))
```
### d. Copy even lines of the file to a file named 'Filel and odd lines to another file named 'File2'.
```
with open("File1.txt", "w") as f1, open("File2.txt", "w") as f2:
    for i, line in enumerate(lines, 1):
        if i % 2 == 0:
            f1.write(line)
        else:
            f2.write(line)
```
## 10. Write a program to define a class Point with coordinates x and y as attributes. Create relevant methods and print the objects. Also define a method distance to calculate the distance between any two point objects.
```
import math

class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def show(self):
        print("Point(", self.x, ",", self.y, ")")
    
    def distance(self, other):
        return math.sqrt((self.x - other.x)**2 + (self.y - other.y)**2)

p1 = Point(2, 3)
p2 = Point(5, 7)
p1.show()
p2.show()
print("Distance =", p1.distance(p2))
```
## 11. Write a function that prints a dictionary where the keys are numbers between 1 and 5 and the values are cubes of the keys.
```
d = {}
for i in range(1, 6):
    d[i] = i**3
print(d)
```
## 12. Consider a tuple 11=(1, 2, 5, 7, 9, 2, 4, 6, 8, 10), Write a program to perform following operations: 
### a. Print half the values of the tuple in one line and the other half in the next line.
```
t1 = (1, 2, 5, 7, 9, 2, 4, 6, 8, 10)
print("First half:", t1[:len(t1)//2])
print("Second half:", t1[len(t1)//2:])
```
## b. Print another tuple whose values are even numbers in the given tuple.

```
even_tuple = tuple(x for x in t1 if x % 2 == 0)
print("Even numbers tuple:", even_tuple)
```

## c. Concatenate a tuple 12-(11,13,15) with t1.
```
t2 = (11, 13, 15)
print("Concatenated tuple:", t1 + t2)
```
### d. Return maximum and minimum value from this tuple
```

print("Maximum =", max(t1))
print("Minimum =", min(t1))
```
## 13. Write a program to accept a name from a user. Raise and handle appropriate exception(s) if the text entered by the user contains digits and/or special characters.
```
name = input("Enter your name: ")

try:
    if not name.isalpha():
        raise ValueError("Name should contain only letters!")
    print("Valid name:", name)
except ValueError as e:
    print("Error:", e)
    ```

