# Python Code Problems Collection

A collection of Python programs focused on problem solving, logic building, object-oriented programming, file handling, and NumPy-style data manipulation practice.

## Repository Overview

This repository contains a set of useful Python coding problems that demonstrate core programming concepts and practical implementation skills. Each program is written by hand and reflects real practice with loops, functions, classes, input handling, file operations, and string/list processing.

## Programs Included

| No. | Program Name |
|---|---|
| 1 | Matrix Multiplication Using Nested Loops |
| 2 | Complex Number Addition Using Class |
| 3 | Snake Water Gun Game |
| 4 | Student Result Tracker Using OOP |
| 5 | File Creation and Reading Using `os` Module |
| 6 | Loan File Reader and EMI Calculator |
| 7 | Star Pattern Printing: Reverse Triangle |
| 8 | Star Pattern Printing: Hollow Square |
| 9 | Find Second Largest Number in a List |
| 10 | Remove Duplicate Items While Preserving Order |
| 11 | Count Vowels and Consonants in a String |
| 12 | Palindrome Checker |

## 1. Matrix Multiplication Using Nested Loops

### Problem Statement
Multiply two matrices if their dimensions are compatible.

### Python Code
```python
def matrix_multiply(m1,m2):
    rows_m1=len(m1)
    cols_m1=len(m1)
    rows_m2=len(m2)
    cols_m2=len(m2)
    if cols_m1!=rows_m2:
        print(f"matrix multiplication of {m1} and {m2} is not possible")
    else:
        result=[]
        for i in range(rows_m1):
            row=[]
            for j in range(cols_m2):
                total=0
                for k in range(rows_m2):
                    total=total+m1[i][k]*m2[k][j]
                row.append(total)
            result.append(row)
        print(f"matrix multiplication of {m1}*{m2}={result}")

matrix_multiply([,],[,,,])[1][2][3][4][5][6][7]
```

### What This Program Does
- Checks whether matrix multiplication is possible.
- Uses nested loops to calculate each value in the result matrix.
- Prints the multiplied matrix.

### Concepts Used
- Functions
- Nested loops
- Lists
- Matrix logic

## 2. Complex Number Addition Using Class

### Problem Statement
Create a class to store complex numbers and add two complex numbers entered by the user.

### Python Code
```python
class complex_op:
    def __init__(self,real_part,img_part):
        self.real_part=real_part
        self.img_part=img_part
    
    def complex_num_display(self):
        if self.img_part>=0:
            return (f"{self.real_part} + i{self.img_part}")
        else:
            return (f"{self.real_part} - i{abs(self.img_part)}")
    
    def complex_sum(self,second_complex_no):
        sum_real=self.real_part+ second_complex_no.real_part
        sum_img=self.img_part + second_complex_no.img_part
        return complex_op(sum_real,sum_img)

real_value1=int(input("enter the real part of first no. :"))
img_value1=int(input("enter the imginary value of first no. :"))
num1=complex_op(real_value1,img_value1)

real_value2=int(input("enter the real part of 2nd no. :"))
img_value2=int(input("enter the imginary value of 2nd no. :"))
num2=complex_op(real_value2,img_value2)

result=num1.complex_sum(num2)
print(f"first complex no. is : {num1.complex_num_display()}")
print(f"2nd complex no. is : {num2.complex_num_display()}")
print(f"the sum of two complex no is : {result.complex_num_display()}")
```

### What This Program Does
- Stores real and imaginary parts in a class.
- Displays complex numbers in readable form.
- Adds two complex numbers using a method.

### Concepts Used
- Classes and objects
- `__init__` method
- Methods
- User input

## 3. Snake Water Gun Game

### Problem Statement
Build a simple game where the user plays against the computer.

### Python Code
```python
your_choice=int(input("Enter 1 for SNAKE, 2 for GUN and 3 for WATER "))
if your_choice==1:
    your_choice="Snake"
elif your_choice==2:
    your_choice="Gun"
else:
    your_choice="Water"
import random
Computer_choice=random.randint(4,6)
if Computer_choice==4:
    Computer_choice="Snake"
elif Computer_choice==5:
    Computer_choice="Gun"
elif Computer_choice==6:
    Computer_choice="Water"
if your_choice==Computer_choice:
    print(f"your choice is {your_choice} and computer choose {Computer_choice} so it' a DRAW.")
elif your_choice=="Snake" and Computer_choice=="Gun":
    print(f"you choose {your_choice}, computer choose {Computer_choice}, so you LOOSE.")
elif your_choice=="Snake" and Computer_choice=="Water":
    print(f"you choose {your_choice}, computer choose {Computer_choice}, so you WIN.")
elif your_choice=="Gun" and Computer_choice=="Snake":
    print(f"you choose {your_choice}, computer choose {Computer_choice}, so you WIN.")
elif your_choice=="Gun" and Computer_choice=="Water":
    print(f"you choose {your_choice}, computer choose {Computer_choice}, so you LOOSE.")
elif your_choice=="Water"and Computer_choice=="Snake":
    print(f"you choose {your_choice}, computer choose {Computer_choice}, so you LOOSE.")
elif your_choice=="Water"and Computer_choice=="Gun":
    print(f"you choose {your_choice}, computer choose {Computer_choice}, so you WIN.")
```

### What This Program Does
- Takes user choice as input.
- Randomly generates the computer choice.
- Compares both choices and prints the result.

### Concepts Used
- Conditionals
- Random module
- User input
- Game logic

## 4. Student Result Tracker Using OOP

### Problem Statement
Create a student class that stores marks and calculates total, average, and grade.

### Python Code
```python
class student_info:
    def __init__(self,name,standard,section,roll_no,marks):
        self.name=name
        self.standard=standard
        self.section=section
        self.roll_no=roll_no
        self.marks=marks
    
    def total_marks(self):
        total=0
        for i in self.marks:
            total=total+i
        return total
    
    def avg_marks(self):
        return self.total_marks()/len(self.marks)
    
    def grade(self):
        if self.avg_marks()>=90:
            return 'A'
        elif self.avg_marks()>=75:
            return 'B' 
        elif self.avg_marks()>=60:
            return 'C'
        else:
            return 'D'
    
    def student_result(self):
        print(f"name : {self.name}, roll_no : {self.roll_no}")
        print(f"your total marks is {self.total_marks()}")
        print(f"your average marks is {self.avg_marks()}")
        print(f" your final grade is {self.grade()}")

subjects = ["english", "math", "physics", "chem", "economics"]
marks1 = []
for i in subjects:
    i= int(input(f"dear Tom enter marks for {i}: "))
    marks1.append(i)

marks2=[]
for i in subjects:
    i= int(input(f"dear Alex enter marks for {i}: "))
    marks2.append(i)

tom=student_info("tom",12,"F",37,marks1)
alex=student_info("alex",12,"F",31,marks2)
tom.student_result()
alex.student_result()
```

### What This Program Does
- Stores student details and marks.
- Calculates total and average marks.
- Assigns grade based on average marks.
- Prints a complete result summary.

### Concepts Used
- Classes and objects
- Methods
- Lists
- Loops
- Grade logic

## 5. File Creation and Reading Using `os` Module

### Problem Statement
Create a file, write content into it, and read it back using the `os` module.

### Python Code
```python
import os
folder_path=r"C:\Users\saury\OneDrive\Desktop\PYTHON_OS_module"
file_name="orders.csv"
file_path=os.path.join(folder_path,file_name)

with open(file_path,"w",encoding="utf-8") as f:
    f.write(f"""Today is cloudy and raining all day.\nI was waiting for rain to
stop but it does not stop.\nI do not like this behaviour of rain""")

with open(file_path,"r")as f:
    file_content=f.read()

print(file_content)
files=os.listdir(folder_path)
print(files)
```

### What This Program Does
- Creates a file path.
- Writes text into a file.
- Reads the file content back.
- Lists files in the folder.

### Concepts Used
- File handling
- `os` module
- Reading and writing files
- Working with paths

## 6. Loan File Reader and EMI Calculator

### Problem Statement
Read loan records from a text file and calculate EMI for each record.

### Python Code
```python
import os

def read_loan_file(path):
    with open(path,"r",encoding="utf-8") as f:
        file_content=f.readlines()

    print(file_content)
    loan_header=file_content.strip().split(",")
    print(loan_header)
    values_float_f=[]
    for items in file_content[1:]:
        item=items.strip().split(",")
        values_float=[]
        for i in item:
            if i=="":
                values_float.append(0.0)
            else:
                values_float.append(float(i))
        values_float_f.append(values_float)
    print(values_float_f)
    result_f=[]
    for i in values_float_f:
        result={}
        for x,y in zip(loan_header,i):
            result[x]=y
        result["emi"]=((result["loan_amount"]-result["loan_downpayment"])*(result["loan_interest_rate"]/100)*((1+(result["loan_interest_rate"]/100))**result["loan_duration"])) / (((1+(result["loan_interest_rate"]/100))**result["loan_duration"])-1)
        result_f.append(result)

    print(result_f)
    folder_path=r"C:\Users\saury\OneDrive\Desktop\PYTHON_OS_module"
    file_name="loan_data"
    file_path=os.path.join(folder_path,file_name)
    with open(file_path,"w+",encoding="utf-8") as f:
        f.write(str(result_f))
        loan_data_content=f.read()
    print(loan_data_content)

read_loan_file(r"C:\Users\saury\OneDrive\Desktop\new_loan_testing.txt")
```

### What This Program Does
- Reads loan data from a text file.
- Converts values into numeric format.
- Stores each record in dictionary form.
- Calculates EMI for each loan.
- Saves the processed result.

### Concepts Used
- File handling
- `os` module
- Dictionary creation
- Formula-based calculation
- Data cleaning

## 7. Star Pattern Printing: Reverse Triangle

### Problem Statement
Print a reverse triangle star pattern.

### Python Code
```python
reverse_num=[]
def pattern(n):
    for i in range(1,n+1):
        reverse_num.append(i)

num=int(input("Enter the no. to get special pattern "))
pattern(n=num)
reverse_num.reverse()
a="*"
for k in reverse_num:
    b=a*k
    print(b)
```

### What This Program Does
- Stores numbers in a list.
- Reverses the list.
- Prints stars in decreasing order.

### Concepts Used
- Lists
- Functions
- Loops
- Pattern printing

## 8. Star Pattern Printing: Hollow Square

### Problem Statement
Print a hollow square star pattern.

### Python Code
```python
num=int(input("Enter the no. to get special pattern "))
b=" "
a="*"
for i in range(1,num+1):
    if (i==1 or i==num):
        print(a*num)
    else:
        print(a+(b*(num-2))+a)
```

### What This Program Does
- Prints full star rows on top and bottom.
- Prints hollow rows in the middle.

### Concepts Used
- Loops
- Conditionals
- String repetition
- Pattern printing

## 9. Find Second Largest Number in a List

### Problem Statement
Find the second largest number entered by the user.

### Python Code
```python
num=input("Enter the inter or decimal no. by single space only: ")
num=num.strip()
num_list=num.split(" ")
num_list_new=[]
for i in num_list:
    i.strip()
    numbers=float(i)
    num_list_new.append(numbers)
print(f"Your entered numbers are {num_list_new}")
num_list_new.sort()
num_list_new.reverse()
print(f"Your numbers in descending order is {num_list_new}")
print(f"2nd largest number in your list is {num_list_new}")
```

### What This Program Does
- Takes multiple numbers as input.
- Converts them to float.
- Sorts them in descending order.
- Prints the second largest value.

### Concepts Used
- Lists
- Sorting
- User input
- Type conversion

## 10. Remove Duplicate Items While Preserving Order

### Problem Statement
Remove duplicate items from a list without changing the original order.

### Python Code
```python
data=input("Enter your any tpe of data only using space: ")
data=data.strip()
data=data.split(" ")
print(data)
data_new1=[]
for k in data:
    k.strip()
    data_new1.append(k)


data_new2=[]
for i in data:
    if i in data_new2:
        continue
    else:
        data_new2.append(i)
print(f"your{data_new1} now have unique items {data_new2} keeping original order")
```

### What This Program Does
- Accepts a list of items from the user.
- Creates a new list with only unique items.
- Preserves original order.

### Concepts Used
- Lists
- Loops
- Duplicate checking
- Order preservation

## 11. Count Vowels and Consonants in a String

### Problem Statement
Count vowels and consonants in a string entered by the user.

### Python Code
```python
word=input("Enter your word or sentence to total no. of Vowels and consonants in it: ")
word=word.strip()
word_list=word.split(" ")
word=""
for m in word_list:
    word=word+m

word=word.lower()
print(word)
vowels=["a","e","i","o","u"]
consonants=["b", "c", "d","f", "g", "h","j", "k", "l", "m",
          "n", "p", "q", "r", "s", "t","v", "w", "x", "y", "z"]

num_vowels_list=[]
for i in vowels:
    if i in word:
        num_vowels=word.count(i)
        num_vowels_list.append(num_vowels)

print(f"vowels count list= {num_vowels_list}")

total_vowels=0
for k in num_vowels_list:
    total_vowels=total_vowels+k
print(f"Total no. of vowels in your word={total_vowels}")
num_consonants_list=[]
for n in consonants:
    if n in word:
        num_consonants=word.count(n)
        num_consonants_list.append(num_consonants)

print(f"consonant count list= {num_consonants_list}")

total_consonants=0
for p in num_consonants_list:
    total_consonants=total_consonants+p

print(f"Total no. of consonants in your word= {total_consonants}")
```

### What This Program Does
- Removes spaces.
- Converts text to lowercase.
- Counts vowels.
- Counts consonants.

### Concepts Used
- Strings
- Lists
- Loops
- Counting characters

## 12. Palindrome Checker

### Problem Statement
Check whether the entered text is a palindrome.

### Python Code
```python
data= input("enter your text to check whether it is palimdrome or not")
lis=[]
for i in data:
    lis.append(i)
print(lis)
lis.reverse()
print(lis)
data_rev=""
for k in lis:
    data_rev= data_rev+k

print(data_rev)
if data==data_rev:
    print("it's palimdrome")
else:
    print("not palimdrome")
```

### What This Program Does
- Breaks the string into characters.
- Reverses the list.
- Rebuilds the string.
- Compares original and reversed text.

### Concepts Used
- Strings
- Lists
- Reversal
- Conditionals

## Skills Demonstrated

This repository demonstrates practical Python skills in:

- Problem solving
- Logic building
- Classes and objects
- File handling
- String processing
- List processing
- Pattern generation
- User input handling
- Working with modules

## Why This Repository Matters

This project collection is useful as a learning portfolio because it shows consistent Python practice across multiple small but important coding problems. It reflects improvement in core Python concepts and problem-solving ability.

## Author

**Surya Prakash**  
Data Analyst / Business Analyst  
India
