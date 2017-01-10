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
              line = line.strip()
              data = line.split(',')
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
              line = line.strip()
              data = line.split(',')
      ```
    **Summary3**: Use **open("filename", "encoding=xxx")** when reading unicode data from a file.
    
    I stucked on this issue for couple hours, and read several blogs about characters encoding and decoding in Python2 and Python3, here is the best one I have ever read!
    
      [Python character encoding and decoding](http://ajucs.com/2015/11/10/Python-character-encoding-explained.html) 
  
* **Dictionary**

 * 2 ways to create a new dictionary
 
 ```python
     weather_dict = {}
     weather_dict = dict()
 ```
 
 * 2 ways to add new key:value to dictionary
 
 ```python
     weather_dict[data[0]] = data[1]
     weather_dict.update = ({data[0]: data[1]})
 ```
 
 so now, I have a function as below: it converts a string like '北京，晴' to an item in a dictionary like '北京：晴'
 
 ```python
     filename = "weather_info.txt"
     weather_dict = {}
     def convert_txt_to_dict(filename):
        with open(filename, encoding = "utf-8") as file:
            for line in file.readlines():
                line = line.strip()
                data = line.split(',')
                weather_dict[data[0]] = data[1]
        return weather_dict
 ```
 
 * 3 ways to check if the dictory is empty
 
 There is a requirement in the task: print all the query history before exit. To implement it, I save the query results to a dictionary named 'weather_history', then I need to check whether it is empty, if yes, quit directory, else, print history then quit.
 
 ```python
    weather_history = {}
    
    if len(weather_history) == 0:
        print("Method1: This is an empty dictionary")
    
    if not weather_history:
        print("Method2: This is an empty dictionary")
    
    if not bool(weather_history):
        print("Method3: This is an empty dictionary")
        
 ```
 To understand method2 and method3 better, read [Python3 docs Truth Value Testing](https://docs.python.org/3/library/stdtypes.html) 
 
 **Summary4**: **Any object can be tested for truth value, for use in an if or while condition.** 
 
     The following values are considened false: 
     * None
     * False
     * zero of any numeric type: 0,0.0
     * any empty sequence, '',(),[]
     * any empty mapping, {}
     * instance of user-defined classes, if the class defines a \_\_bool\_\_() or \_\_len()\_\_ method, when that returns the integer zero or bool value False.
    
     All other values are considered true.
 
 
 * To quit , I find two similar functions:exit() and sys.exit(), what's the difference?
 
 Refer to [an answer in stackoverflow](http://stackoverflow.com/questions/6501121/difference-between-exit-and-sys-exit-in-python)
 
 **Summary5**: 
     * They all raising SystemExit
     * exit() is a helper for the interactive shell
     * sys.exit() is intended for use in programs.
 
 
    
      
  

   
                 
        















