# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
~~~
mkdir my-folder
~~~
<img width="387" height="53" alt="560035203-3a075c08-253f-4ec2-b716-a5cdd81adeda" src="https://github.com/user-attachments/assets/fd53a6fd-0907-4494-992b-71b8083c1c7b" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
~~~
rmdir my-folder
~~~
<img width="408" height="50" alt="560035333-6d6cb208-70ee-43ee-bd3e-3703cb8cd181" src="https://github.com/user-attachments/assets/e0bff300-37d7-4d07-9de8-2d68145b99df" />


Create the file Rose.txt

## COMMAND AND OUTPUT
~~~
type nul > Rose.txt
~~~
<img width="439" height="55" alt="560035412-84cd462e-a30e-4fe8-a495-d66ae8bbc3af" src="https://github.com/user-attachments/assets/13b13521-f73e-4b74-9d54-598afe0eb6c8" />


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
~~~
echo Hello World > hello.txt
~~~
<img width="558" height="52" alt="560035555-fe0c708d-1afa-4bd4-9dff-38fa470b5729" src="https://github.com/user-attachments/assets/9dd9adc7-a8ea-46d0-8fdc-333042750fc1" />


Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
~~~
copy hello.txt hello1.txt
~~~
<img width="497" height="69" alt="560035710-afd61f81-66df-4651-bb13-6efe1d93ae9c" src="https://github.com/user-attachments/assets/85be8345-8a4b-429e-a032-d1efac0eeeef" />

Remove the file hello1.txt

## COMMAND AND OUTPUT
~~~
del hello1.txt
~~~
<img width="390" height="49" alt="560035878-c4e5e8d7-0d66-47b4-be7e-8ef62483f427" src="https://github.com/user-attachments/assets/0e463fa7-8199-40cd-9454-218ed845bba4" />


List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
~~~
dir hello1.txt
~~~

<img width="438" height="182" alt="560036013-48d01c9c-26e2-4ed7-ac80-6b1f1ba63f9b" src="https://github.com/user-attachments/assets/38b0a00b-2e31-40bc-a678-34e70a5ebedd" />

List out all the associated file extensions 

## COMMAND AND OUTPUT
~~~
assoc
~~~

<img width="625" height="880" alt="560036114-04b089c4-9d44-41b6-b1c1-b2f7ea7a4100" src="https://github.com/user-attachments/assets/5ad3a677-5dc7-4cb6-a131-d5871e80efd8" />

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
~~~
fc hello.txt Rose.txt
~~~

<img width="536" height="159" alt="560036226-f12d5e7f-d762-4486-ad88-fd5b1db3a4f9" src="https://github.com/user-attachments/assets/82b3b68d-925a-4c9d-ba0e-b1d50d19eaad" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

code 
~~~
set name=John
echo Hello, %name%
pause
~~~

## OUTPUT
<img width="494" height="77" alt="560036534-bb7895a7-bde6-4fda-a608-7216e6ea1dd0" src="https://github.com/user-attachments/assets/9bf96c14-192d-42e3-b724-c1b0a41562f6" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

code
~~~
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE

:END
echo Thank you!
pause
~~~

## OUTPUT

<img width="656" height="202" alt="560036709-229bad6e-d53f-457a-b22b-faf2603cf3ea" src="https://github.com/user-attachments/assets/d583a53b-bdef-46c6-966b-676953c0b2a8" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

code
~~~
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
~~~


## OUTPUT

<img width="457" height="165" alt="560036921-e3cdc272-99fa-4dd3-b531-48d145451c84" src="https://github.com/user-attachments/assets/bceece9b-23b0-498a-a1df-02183870b26b" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

code 
~~~
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
~~~

## OUTPUT

<img width="422" height="52" alt="560037249-ea50421b-b4e2-4a1d-b73f-366d54486412" src="https://github.com/user-attachments/assets/387d100a-cbc0-49da-919c-7c6cc95cef73" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

code
~~~
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU

:EXIT
echo Goodbye!
pause
exit
~~~

## OUTPUT 1
<img width="410" height="192" alt="560037721-ad1e018e-2cbf-414c-a0dd-877ec4291be3" src="https://github.com/user-attachments/assets/d7753be9-17f8-474c-90fd-de0a74cb1b0d" />

## OUTPUT 2

<img width="441" height="203" alt="560037770-fc0d33f5-9b38-4ded-a478-8653ed123913" src="https://github.com/user-attachments/assets/7962ffea-6aeb-4570-90e1-36c8fafd7cab" />

## OUTPUT 3

<img width="431" height="197" alt="560037797-06ff93e7-cc66-4ec4-80d7-7213715f9be4" src="https://github.com/user-attachments/assets/14144fd5-4afc-4e2a-b2ae-8a7fea60ce8a" />


# RESULT:
The commands/batch files are executed successfully.

