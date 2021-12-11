# FileIO & Exceptions

## Files
* Are contingous set of bytes that is used to store data.
* The data can be anything such as text or more complex stored in specific format.
* Files are composed of Header (information about the content), Data (the actual data) and EOF(end of file).
* Different file formats have different exention .txt, .gif, .csv, .png etc

## File Paths
* To access a file, we need the full file path including folder, file name and file extension etc
* Using (`../`) moves us one directory above and can be repeated to move up to more directories.
* (`\n`), (`\r`) and (`\r\n`) are the standard newline characters.
* Different OS have different standards which might complicate file processing.
* Encoding is translating a byte code (ASCII/UNICODE) to human readable code.

## Opening Closing a File in Python
* To process a file we must first open it using the `open()` method.
* After processing the file we close it using the `close()` method.
``` 
file = open('somefile.tx')
tr:
  process file...
finally: 
  file.close()
```
* We can also use `with open('filename.txt') as file:` to automatically close the file after processing.

## Reading a file
* Files modes include `r` for read, `w` for write `rb` for open in binary `wb` read in binary.
* Text files are the most common files, but there are also buffered binary files and raw files.
* `.read(size = -1)` reads entire file.
* `.readLine(size = -1)` reads entire file.
* To read specific amount of characters, we can specify the number inside the read function 
```
with open('filename.txt', 'r') as output:
    print(output.readline(5))
```
* We can read the file as a list using 
```
output = open('filename.txt')
    list.(output
```
* Reading the entire file using a loop:
```
with open('filename.txt') as output:
    line = output.readline()
    while line != '':
        print(line, end='')
        line = output.readline()
```
## Writing a file
* `.write(string)` writes a string to the file
* `.writelines(seq)` writes the sequence to the file.
```
with open('filename.txt') as input:
     filename = input.readlines()
```
* To append to a file we use the 'a' mode when writing.


# Python EXceptions

* Sntax Errors occur when parser detects wrong syntax.
* Exception Errors occur when something like diving by zero happens.
* `raise` can be used to throw an exception.
* `assert` can be used to run a code when specific condition is true, if false then the program throws an exception
* `try` and `catch` are used to handle exceptions. 
* `except is used to handle specific exception
* `else` runs in a `try` when no exceptions happened.
* `finally` used to always run a code no matter what exception happens.

#### References:
[Reading and Writing Files in Python](https://realpython.com/read-write-files-python/)

[Python Exceptions: An Introduction](https://realpython.com/python-exceptions/)

[go to home](README.md)