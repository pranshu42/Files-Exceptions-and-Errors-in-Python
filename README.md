# Files-Exceptions-and-Errors-in-Python
# TASK1 DETAILS:-
The provided Python code is a basic file handling program that attempts to open and read a file called sample.txt. Here’s a detailed explanation of how it works:

Program Breakdown
Opening the file:


with open('sample.txt', 'r') as file:
The open() function is used to open the file named sample.txt in read mode ('r').
The with statement ensures that the file is properly opened and automatically closed once the block of code is executed, even if an error occurs during the execution of that block. This helps prevent resource leaks, such as leaving the file open after you're done with it.
Reading the file:


for line in file:
    print(line.strip())
The for loop iterates over each line of the file. For each iteration, the line variable contains one line of text from the file.
line.strip() removes any leading and trailing whitespace or newline characters from the line before printing it. This ensures that there are no unwanted blank spaces or newlines in the output.
Error handling:


except FileNotFoundError:
    print("Error: The file 'sample.txt' does not exist.")
If the file sample.txt does not exist in the specified location, a FileNotFoundError will be raised. In that case, the program will print an error message: "Error: The file 'sample.txt' does not exist.".
The exception handling mechanism ensures that the program doesn’t crash abruptly and provides a more user-friendly error message.
Handling unexpected errors:


except Exception as e:
    print(f"An unexpected error occurred: {e}")
This except block is a generic handler for any exceptions that weren’t caught by the previous except blocks.
The Exception as e syntax allows the program to capture and print the actual error message if any unexpected error occurs. The error message is stored in the variable e and is printed in the format: "An unexpected error occurred: <error message>".
How It Works:
If the file sample.txt exists, it will be opened, and each line will be read and printed without any leading or trailing whitespace.
If the file does not exist, a message will be printed indicating that the file couldn’t be found.
If an unexpected error occurs (such as permission issues or another kind of error), it will be caught and displayed with a descriptive message.
Example Scenarios:
File exists:

If sample.txt contains:

Hello
World
Python
The output will be:
nginx
Copy
Hello
World
Python
File does not exist:

If sample.txt is missing, the output will be:
Error: The file 'sample.txt' does not exist.
Unexpected error (e.g., permission issue):

If there’s an error opening the file due to permissions, the output will be something like:
An unexpected error occurred: [error message]
Summary:
This program handles file reading while gracefully handling potential errors such as the file not being found or any unexpected issues that might arise during execution. The with statement ensures the file is closed automatically, and the error handling ensures the program provides meaningful error messages without crashing.




