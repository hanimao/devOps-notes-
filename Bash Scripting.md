
Write scripts, manipulate files, process data, automate backups and perform complex operation through the power of scripting.

**=='Shebang' Line==** 
- #!/bin/bash - tells the OS to interpret the script using binary bash.
- The path after the ! points to the specific interpreter/shell that should handle the script. 

**==Changing the file permission==**
- chmod +x filename.sh

Executing the file
- ./filename.sh

**==Comments==** 

Benefits
- Improve readability
- Faster collaboration

- hashtag # Prints greeting to the console 
 :  ' This is a multi line comment
 '
 
 A bash script that renames all txt files in a directory to have a .BAK extension
 vi extension.sh 
 

![[Screenshot 2025-05-07 at 12.12.34.png]]

==**Run Script from Anywhere!**==
(without specifying its path)

1. Place the script in one of the directories thats in our path environment variable. 
2. Path environment variable tells the shells which directories to search for executable files in response to commands.

- echo $PATH
A common directory to place user script
- /usr/local/bin

==**Variables**==

- stores and manipulate data
- In bash variable are like containers that hold data such as text strings, number and arrays
- Provide a way to store values that can be accessed and modified throughout the script.

**==How are variable created?==**

To access the value of the variable, prop-end the variable name with a dollar sign.
![[Screenshot 2025-05-07 at 14.06.52.png]]

==**Variables interpolation**==

- Use variables within strings to create dynamic output ![[Screenshot 2025-05-07 at 14.35.07.png]]

**==Parameters==** 

How to pass parameters to a bash script?

- By allowing inputs in the command line you can make your scripts more versatile and interactive 
- Bash scripts can receive input values, known as parameters or arguments from the command line when they are executed. These parameters allow you to customise the behaviour of your script and make it more flexible.
- $1 = grabs the value of the parameters passed when the script is ran. 
- When executing the scripts with parameters, the values passed on the command line will be substituted into the scripts parameter variables, dollar one etc.
 
 Because you only passed the first 2 parameters, it only prints the first two. 
 
 ![[Screenshot 2025-05-08 at 13.00.36.png]]![[Screenshot 2025-05-08 at 13.01.11.png]]

**How to access all the parameters passed into a script?**

Using a special variable

echo "All Parameters: $@"

==Arithmetic Scripting== 

Allows us to preform calculations using the values of variables and parameters, which provides a convenient way to incorporate dynamic calculations into our scripts.

![[Screenshot 2025-05-08 at 17.07.14.png]]


**==Arithmetic with parameters==** 

Allows us to take input from the user or from command and arguments and perform calculations based on those values. 

Use the positional parameters to assign the values passed as **command line arguments to these variables** 

**==IF statements==**

If statements allows you to execute code blocks based on conditions. Conditions are formed using comparison operators and logical operators.
![[Screenshot 2025-05-12 at 14.28.35.png]]![[Screenshot 2025-05-12 at 14.34.36.png]]



**==else and elif==** 

- the else clause provides an alternative code block to be executed when the if condition evaluates to false.


Else

![[Screenshot 2025-05-12 at 15.37.06.png]]

**elif**

- adds another condition if the first else is false

**Nested if statements**

- embedding if statements with other if statements.
- allow the evaluation of multiple conditions 

**while loops**

- allows you to repeatedly execute a block of code as long as a certain condition remains true until a specific condition becomes false.
- Process data from arrays or files allowing you to automate tasks that involve iterative operations. 


![[Screenshot 2025-05-13 at 12.14.06.png]]







**What is an index?**
The variable index is used to keep track of the current index in the array.

- Set the condition in square braces which compares the value of index with the number of elements in the fruit array.


![[Screenshot 2025-05-13 at 12.13.14.png]]

==**For Loops**==

- iterate over a sequence of values and perform repetitive tasks. They are a powerful tool for automating operations and processing data.
- Enable you to repeat a block of code for a specified number of iterations over a sequence of values.


