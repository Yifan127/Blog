### Ch1 Project practice

#### Function description
    
    1. Input city, output weather info
    2. Input 'h' or 'help', print usage guide
    3. Exit the scipt
    4. Print all the query records before quit

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

#### Recording all the thinking when I solve the problem.
* **Reading Unicode File**

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
        file = open("weather_info.txt")
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
        file = open("weather_info.txt")
        list_readlines = file.readlines()
        print(list_readlines)
        # close the file
        file.close()
        
        ```
        output:
        
        ![](/assets/ch1practice/readlines.PNG)
    
         **Summary 1**: Use readlines().
         
 * Good practice to use **with** 
 
      ```python
      with open("weather_info.txt") as file:
          list = file.readlines()
      print(file.closed)
      ```  
      
     output
     
        True
        
       **Summary 2**: Use **with** to deadling with file object, the advantage is:  **file is properly closed**, even if an exception is raised. 

  * After reading the file to a list, loop over the list to get each line
  
      ```python
      with open("weather_info.txt") as file:
          for line in file.readlines():
              processing_line()
      ```
  * There are **Chinese characters** in weather_info.txt, so I get this exception:
  
      UnicodeDecodeError: 'gbk' codec can't decode byte 0xb4 in position 9: illegal multibyte sequence
      
      **Thinking**:
  
      1. The data in weather_info.txt is encoding in utf-8
      2. Python needs to decode the unicode 
      3. But get the decode error: gbk can't decode
      4. In Windows CMD, default encoding is gbk
      5. So the question is : how to read unicode data from a file, and decode the data?
      
    **Solution**: from [Python3 docs Unicode Howto](https://docs.python.org/3/howto/unicode.html)
      
      ```python
      with open("weather_info.txt", encoding = "utf-8") as file:
          for line in file.readlines():
              processing_line()
      ```
      
* **Dictionary**

 * 2 ways to create a new dictionary
 
     1. weather_dict = {}
     2. weather_dict = dict()
 


      
      
    
      
  

   
                 
        















