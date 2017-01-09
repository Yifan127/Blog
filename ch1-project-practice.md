### Ch1 Project practice

#### Function description
    
    1. Input city, output weather info
    2. Input 'h' or 'help', print usage guide
    3. Exit the scipt
    4. Print all the query record before quit

#### Break down to small tasks

    1. Read a txt file named 'weather_info.txt'.
    2. Get the data from the file, then save the data in dictionary.
    3. Chinese character decoding and encoding.
    4. What does "\_\_name\_\_" mean?
    5. How to write help for script?

#### To implement the function, I need to understand:
* **Read file**
* **Dictionary**
* **Character decoding and encoding**
    * ASCII
    * GBK
    * Unicode, UTF-8
    * String and bytes in Python3 vs. unicode and 8-bit Python2
* **Loop**
* **\_\_name\_\_**
* **Writing help for script**

#### Recording all the thinkings when I solve the problem.
* **Read File**

    * 3 ways to read a file:
    
        1. Read the entire file, return string or bytes

        ```python
        # open a file in read mode
        file = open("weather_info.txt")
        str_read = file.read()
        print(str_read)
        # close the file
        file.close()
        
        ```
        output:
        
        ![](/assets/ch1practice/read.PNG)
        2. Read a single line of a file
        ```python
        # open a file in read mode
        file = open("weather_info.txt",'r')
        str_readline = file.readline()
        print(str_readline)
        # close the file
        file.close()
        
        ```
        output:
        
        ![](/assets/ch1practice/readline.PNG)
        3. Read all the lines of a file in a list 
        ```python
        # open a file in read mode
        file = open("weather_info.txt",'r')
        list_readlines = file.readlines()
        print(list_readlines)
        # close the file
        file.close()
        
        ```
        output:
        
        ![](/assets/ch1practice/readlines.PNG)
    
         **Summary one**: Use readlines().
         
 * Good practice to use **with** when deadling with file object:
 
      ```python
      with open("weather_info.txt
      ```     















