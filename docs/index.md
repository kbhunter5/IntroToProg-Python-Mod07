# Assignment 7 - Pickling and Structured Error
## **Dev:** *Kellen Hunter*  
## **Date:** *08/24/20*  
## Introduction
## Summary

```
post code here

try:
    quotient = 5/1
    f = open('SomeFile.txt', 'r+')  # the read plus option gives an error if filed does not exist
    f.write(quotient)  # causes an error if the file does not exist
except ZeroDivisionError as e:
    print("Please do no use Zero for the second number!")
    print("Built-In Python error info: ")
    print(e, e.__doc__, type(e), sep='\n')
except FileNotFoundError as e:
    print("Text file must exist before running this script!")
    print("Built-In Python error info: ")
    print(e, e.__doc__, type(e), sep='\n')
except Exception as e:
    print("There was a non-specific error!")
    print("Built-In Python error info: ")
    print(e, e.__doc__, type(e), sep='\n')

![pic2](https://github.com/kbhunter5/IntroToProg-Python-Mod07/blob/master/docs/pic2.png "Pic2")


##### FIGURE 2
