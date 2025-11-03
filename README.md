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
mkdir my-folder

<img width="956" height="279" alt="image" src="https://github.com/user-attachments/assets/531c3816-27b7-4842-a506-3b60e404405f" />


## COMMAND AND OUTPUT

Remove the directory "my-folder"

rmdir my-folder
<img width="955" height="117" alt="image" src="https://github.com/user-attachments/assets/abd1419b-4e12-41c8-87a5-484ce7f9b464" />



## COMMAND AND OUTPUT


Create the file Rose.txt

COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
^Z
1 file(s) copied
dir Rose.txt

<img width="958" height="459" alt="image" src="https://github.com/user-attachments/assets/d09fdb5a-d5df-45ad-9c0d-ce3620c174a0" />



## COMMAND AND OUTPUT


Create the file hello.txt using echo and redirection

echo “hello world” > hello.txt
type hello.txt

<img width="958" height="207" alt="image" src="https://github.com/user-attachments/assets/5deec43c-2b4f-4083-8988-417ed4297845" />


## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
copy hello.txt hello1.txt

<img width="953" height="227" alt="image" src="https://github.com/user-attachments/assets/3ace5e9f-a68b-49b3-bf07-06ac00426aee" />


## COMMAND AND OUTPUT

Remove the file hello1.txt

del hello1.txt
dir hello1.txt

<img width="957" height="284" alt="image" src="https://github.com/user-attachments/assets/8191835d-2995-4a33-ad9f-67c1ccb7dfd8" />


## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory

assoc | more

<img width="955" height="637" alt="image" src="https://github.com/user-attachments/assets/5dd71960-bf1f-4ddd-95c8-9a725098f6ee" />


## COMMAND AND OUTPUT

List out all the associated file extensions 

fc hello.txt Rose.txt

<img width="956" height="305" alt="image" src="https://github.com/user-attachments/assets/ab7331bc-9bf8-4fb7-8ab7-46bd6bc961c6" />



## COMMAND AND OUTPUT


Compare the file hello.txt and rose.txt



## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

BATCH SCRIPT
Open Notepad with filename 1.bat and type the following batch script
@echo off
set name=John
echo Hello, %name%!
pause





## OUTPUT

<img width="961" height="395" alt="image" src="https://github.com/user-attachments/assets/6c47f0a7-c26b-4d6f-9dba-86720ab1d213" />

Execute the batch file 1.bat

<img width="957" height="164" alt="image" src="https://github.com/user-attachments/assets/b14b6d15-12ae-4342-9af1-3c94ee320a8c" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

Open Notepad with filename 2.bat and type the following and execute 2.bat
@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause


## OUTPUT

<img width="953" height="321" alt="image" src="https://github.com/user-attachments/assets/859c769c-812f-44f7-a886-3ba454e20e08" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

Open Notepad with filename 3.bat and type the following and execute 3.bat
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause



## OUTPUT

<img width="960" height="265" alt="image" src="https://github.com/user-attachments/assets/07e77ccb-35ff-462a-ab2e-5f25a510abb8" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

Open Notepad with filename 4.bat and type the following and execute 4.bat
Then create the file sample.txt and execute 4.bat

@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause


## OUTPUT

<img width="957" height="302" alt="image" src="https://github.com/user-attachments/assets/998d53f5-6343-4b8c-8a47-474c44dca44d" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.



Open Notepad with filename 5.bat and type the following and execute 5.bat

@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause



## OUTPUT

<img width="962" height="523" alt="image" src="https://github.com/user-attachments/assets/15e51e1f-ac37-46eb-a42b-32c37aeb5b04" />



# RESULT:
Thus the windows commands and Batch scripting is executed successfully.

