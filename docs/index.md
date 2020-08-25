## **Dev:** *Kellen Hunter*  
## **Date:** *08/24/20*  

# Assignment 7 - Pickling and Structured Error  

## Introduction
Pickling is creating a list or dictionary and saving it to a file. A file can be "unpickled" for data retrieval. Unpickling can be dangerous because there could contain viruses or malware inside the data set. This is why it is important to only unpickle data you have generated or received from a trusted source. This is because dat files are used for pickling and the files are obscure, which means they are NOT secured.

Error and Exception handling are coded in error messages that help the user identify how to solve that issue if it happens. There are 3 types of errors compile time (Syntax), logical, and run time. Compile errors also known as syntax could include an incorrect spelling or missing character. Logical errors are created when an output is incorrect or impossible, for example 1+1 =3. Since 3 is does not equal 1+1 a logical error is created. Run time error occur during the run time of the script by something the user did. These can occur when the user divides by 0. Exceptions can be coded into scripts to display a message or loop into an if statement if an error occurs.

```
#------------------------------------------------- #
# Title: Assignment 07
# Description: Pickling and Structured Errors
# ChangeLog: (Who, When, What)
# Kellen Hunter, 08/24/20, created Script
# ------------------------------------------------- #
import pickle # This imports code from another code file!
# Data -------------------------------------------- #
strFileName = 'Grades.dat'
lstGrades = []
class FileNotDATError(Exception):
# #  """ File extension must end with DAT to indicate it is a DAT file """
    def __str__(self):
        return 'File extension not DAT'
gradeslist = {'Kellen': ['A'],
          'Steve':['B'],
          'Kyle':['D'],
          'Tiffany':['B'],
          'Paul':['A'],
          'Simon':['B'],
          'Kelsey':['C']
          }
# Processing -------------------------------------- #
def save_data_to_file(file_name, grades):
#pass # TODO: Add code here
    file = open(file_name, "wb")
    pickle.dump(grades, file)
    file.close()
def read_data_from_file(file_name):
#pass # TODO: Add code here
    file = open(file_name, "rb")
    grades = pickle.load(file)
    file.close()
    return grades
# Presentation ------------------------------------ #
# TODO: Get ID and NAME From user, then store it in a list object
strName = str(input("Enter a Name "))
if strName.isnumeric():
     raise Exception('Do not use numbers')
     print("Must enter in letter only for names")
strGrade= str(input("Enter in their Grade: "))
try:
    if strName.isnumeric():
        raise Exception('Do not use numbers')
        print("Must enter in letter only for names")
except Exception as e:
    print("There was a non-specific error!")
    print("Built-In Python error info: ")
    print(e, e.__doc__, type(e), sep='\n')
lstGrades = [strName, strGrade]
# TODO: store the list object into a binary file
save_data_to_file(strFileName, lstGrades)
# TODO: Read the data from the file into a new list object and display the contents
print(read_data_from_file(strFileName))
print(gradeslist)

![Command Prompt Pic](https://kbhunter5.github.io/IntroToProg-Python-Mod07/CommandPrompt.png "Command Prompt Pic")
### Picture of code working in the Command Prompt.

![PyCharmCompilation](https://kbhunter5.github.io/IntroToProg-Python-Mod07/PyCharmCompilation.png "PyCharm Compilation")
### Picture of code working in PyCharm.

![Grades Pic](https://kbhunter5.github.io/IntroToProg-Python-Mod07/Grades.png "Picture of Grades Dat File")
### Picture of Grades Dat File.
```

## Summary
For this assignment I was able to create a pickle and extract that data out of a binary .dat file. After, the data was successfully saved and extracted from the pickle table, I was able to go back and add in the exceptions. For this script the exception I used was the "isnumeric" one, while asking the user to input a name and a letter grade. The script is designed to error out and show "Do not use numbers, Must enter in letter only for names". This way the user knows what the error is and they can now rerun the script and fix the error. Below are the sources I found useful for this assignment.


## Sources
Pickling:  

https://www.youtube.com/watch?v=Bzt6vlf865k - Using Pickle to write to and read from a file in Python [Part 3]
https://www.youtube.com/watch?v=IrLQ8ckLpWo - Python Basics Pickle Load Method

Error and Execption Handling:  

https://www.youtube.com/watch?v=NIWwJbo-9_8 - Python Tutorial: Using Try/Except Blocks for Error Handling
https://www.youtube.com/watch?v=6SPDvPK38tw - #63 Python Tutorial for Beginners | Exception Handling


