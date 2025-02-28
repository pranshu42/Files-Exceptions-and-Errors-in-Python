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


# TASK2 DETAILS:-
This Python program demonstrates how to write user input to a file, append additional content to the file, and then read the content from the file to display it. Here's a detailed breakdown of the program:

Program Breakdown
User Input for Writing to the File:

user_input = input("Enter some text to write to the file: ")
The input() function prompts the user to enter a string of text.
The entered text is stored in the variable user_input.
Writing the User Input to the File:


with open('output.txt', 'w') as file:
    file.write(user_input + "\n")
The open() function is used to open (or create) the file output.txt in write mode ('w').
If the file already exists, the 'w' mode will overwrite its contents.
The write() method writes the user_input to the file. The + "\n" ensures that a newline character is added at the end, making the content appear on a new line.
The with statement ensures that the file is properly closed after writing.
User Input for Appending to the File:


additional_data = input("Enter some additional text to append to the file: ")
The input() function prompts the user again, asking for additional text to append to the file.
The entered text is stored in the variable additional_data.
Appending the Additional Data to the File:


with open('output.txt', 'a') as file:
    file.write(additional_data + "\n")
The open() function is used to open the output.txt file in append mode ('a').
In append mode, new data is added to the end of the file without overwriting the existing content.
The write() method appends the additional_data to the file, again adding a newline character at the end for formatting.
Reading the Final Content of the File:


with open('output.txt', 'r') as file:
    final_content = file.read()
The open() function is used to open the output.txt file in read mode ('r').
The read() method reads the entire content of the file into the final_content variable.
Displaying the Final Content:


print("\nFinal content of 'output.txt':")
print(final_content)
Finally, the program prints the content of the file to the console, showing the result of the initial write and the subsequent append operation.
Example Walkthrough
Let’s go through an example of how this program would work with user input.

First Input (for writing to the file):

User is prompted with: Enter some text to write to the file:
Suppose the user enters: Hello, this is the first line!
The program writes this text to output.txt.
Second Input (for appending to the file):

User is prompted with: Enter some additional text to append to the file:
Suppose the user enters: And here's the second line!
The program appends this text to output.txt.
Reading and Displaying File Content:

The program reads the content of the file and displays it as follows:

Final content of 'output.txt':
Hello, this is the first line!
And here's the second line!
File Handling Summary:
Write Mode ('w'): Opens the file for writing. If the file exists, it is overwritten. If the file doesn't exist, it is created.
Append Mode ('a'): Opens the file for appending. Data is added to the end of the file without modifying the existing content.
Read Mode ('r'): Opens the file for reading. The content is read from the file as a whole.
Potential Scenarios:
File Creation:

If output.txt doesn't exist when the program is run, it will be created during the write() operation.
Appending:

The program appends new text without affecting the previous content. This is useful for adding logs, notes, or continuous data to a file.
File Content Display:

The final content of output.txt is displayed in the console, allowing the user to see both the original input and any appended data.
Example Output
If the user enters the following:

First Input: This is the first line.
Second Input: This is the appended line.
The final output displayed would be:

Final content of 'output.txt':
This is the first line.
This is the appended line.
Conclusion:
This program is a simple example of basic file handling in Python, where it demonstrates how to write to, append to, and read from a file. The use of open() with different modes ('w', 'a', 'r') and the with statement ensures proper file handling and closure.









