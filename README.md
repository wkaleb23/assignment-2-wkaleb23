[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/gs2jt4wO)
# Assignment 2
Assignment 2, EE P 509a, Fall 2023

## Overview

* We've learned a lot about lists, strings, types, functions, and so on in Python this week. This assigment allowws you to apply what we've learned.
  * It's okay to start with the easiest way to get things working, and then iterate to see if you can make it "nicer"
  * Every time you have your code working, then start to try something new (a refactoring), you should first commit your code so you don't lose track of what worked before!
* Work in either a notebook or use a `.py` file-- your choice.
  * A notebook might be nice to help you describe and show off your code, but not required
* Do make sure your code is nice and clean before you submit

# Details

## Problem 1: Valid ID numbers

The United States Postal Service (USPS) sells money orders identified by an 11-digit number $x_{1}x_{2}x_{3}\dots x_{11}$. The first ten digits identify the money order, and the last one x<sub>11</sub> is a check digit that satisfies: 

$$x_{11} = x_{1} + x_{2} + \dots x_{10}\pmod{9}$$

Write a Python function that takes one input argument, a 5-digit number, and similar to the validity check for the USPS mony order, check whether or not the given number is valid by checking that the last digit satisfies equation:

$$x_{5} = x_{1} + x_{2} + x_{3} + x_{4} \pmod{5}$$

Your function should return true if the given digit is valid, and false otherwise.  

#### Sample Input and Expected Output

Valid IDs (your program should return `True` with these inputs:
* 12340
* 11114
* 11119
* 00000
* 00101 

Invalid IDs (your program should return `False`):
* 12346
* 92437
* 1232123

### Notes

* Make sure you have a function `checkId(money_order_id)` that takes in a 5-digit number, performs the check described above, and returns `True` or `False` depending on if it is a valid money order identifier.
* Your code should be readable, clean, and easy to determine whether it is doing the right thing by looking at it (not necessarily running it!)
* It may be helpful (but is not required!) to utilize ASCII character mappings (e.g. https://www.asciitable.com/). 
  * In Python, `ord(char)` provides the ASCII int value of a given character
  * `chr(int)` provides the character that is represented by the provided int value
* The `join()` function might be helpful to convert a list (or any sequence, such as a tuple) to a string
  * Example: If `my_list = ['a, 'b', 'c']`, then `"+".join(my_list)` will produce a string `a+b+c`
  * Reference: https://www.w3schools.com/python/ref_string_join.asp


## Problem 2: Shift Ciphers

The {\bf Shift cipher} is one of the oldest known cryptosystems, often attributed to Julius Caesar. The idea used in this cryptosystem is to replace each letter in an alphabet by another letter at a distance $K$ from it. 

Formally, let's associate each letter $A,B,...,Z$ with an integer $0,\ldots,25$. If we allow the key $K$ to be any integer with $0 \leq K \leq 25$, the _shift cipher_ can be defined as:

$$\begin{eqnarray*}
\text{Encoding: }y&=&e_K(x)=(x+K)\hspace{-0.1in} \mod{26},\\
\text{Decoding: }x&=&d_K(y)=(y-K)\hspace{-0.1in} \mod{26}.
\end{eqnarray*}$$

So, for a shift cipher with $K = 19$, `encode('A')` will return the string `'T'`. `decode(A)` will return the string `'H'`. 

### Notes

* Do have at least 2 functions:
  * `encrypt(message, k)`: Takes in a string and returns an string encrypted with a $k$-shift cipher
  * `decrypt(payload, k)`: Takes in a string and returns a string decrypted with a $k$-shift cipher
  * Feel free to create additional helper functions if that helps

## Problem 3: Is Magical

Given a 2D N x N array matrix of ints, return True if the matrix is a magic square, False otherwise.

A magic square is defined as one that is filled with distinctintegers in the range $1, 2, ..., n^2$ and in which every row, column, and diagonal add up to the same number.
 
Example: 
 * `is_magical([[8, 1, 6],[3, 5, 7],[4, 9, 2]])` returns `True`
 * `is_magical([[1, 2],[3, 4]])` returns `False` 

# Changes

* In Problem 2: 
  * Added notes about how to use `ord()` and `chr()` if desired
  * Added example for `join()`
* In Problem 1, added some examples for good/bad ID values


