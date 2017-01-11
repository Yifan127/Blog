### Ch1 Project practice : Weather Report

#### Function description
    
    1. Input city, output weather info
    2. Input 'h' or 'help', print usage guide
    3. Input 'exit' or 'quit' to quit the script
    4. Print all the query records before quit

#### Break down to small tasks

    1. Read a txt file named 'weather_info.txt'.
    2. Get the data from the file, then save the data in dictionary.
    3. Chinese character decoding and encoding.
    4. How to write help for script?
    5. How to quit a script?
    6. What does "\_\_name\_\_" mean?


#### To implement the function, I need to understand:
* **read file**
* **dictionary**
* **character decoding and encoding**
    * ASCII
    * GBK
    * Unicode, UTF-8
    * String and bytes in Python3 vs. unicode and 8-bit Python2
* **loop**
* **argparse**
* **exit**
* **\_\_name\_\_**


#### Recording all the thinking when I solve the problem.


* **\_\_name\_\_**

    What does if \_\_name\_\_ == "\_\_main\_\_": do?
    
    Here's a best answer in stackoverflow: [\_\_name\_\_ explanation](http://stackoverflow.com/questions/419163/what-does-if-name-main-do)
    
    **A practice about the main check**:
    
    maincheck1.py:
    ```python
    def function1():
        print("This is a __name__ practice.")

    if __name__ == "__main__":
        print("This script is being run by itself.")
    else:
        print("I am being imported into other modules.")

    ```
    maincheck2.py:
    ```python
    import maincheck1

    maincheck1.function1()
    ```
    output:
    
    ![](/assets/ch1practice/maincheck.PNG)
    
    **Summary7: A module's \_\_name\_\_ is set to "\_\_main\_\_" when read from standard input, a script, or from an interactive prompt. **
    
    A reason for doing this is that sometimes you write a module, and it can be executed directly. Alternatively, it can also be imported and used in another module. By doing the main check, you can have that code only execute when you want to run the module as a program and not have it execute when someone just wants to import your module and call your functions themselves.

* **Writing help for script**

    The first thing comes to my mind about help is like this:

    Executing the script with -h, then a usage is printed to Windows PowerShell.
    
        py weather_report.py -h
        
    So, to implement this requirement, I have two sub tasks:
    
    1. Add a description for the script
    
    **Solution: import argparse**
        ```python
        import argparse

        # help
        parser = argparse.ArgumentParser(
            description = '''
            line1
            \t* line2
            ''')
        args=parser.parse_args()
            ```
        And test it,
        
        ![](/assets/ch1practice/help.PNG)
        Then new question: how to display the argparse help in multiple lines? 
        
        **Solution: RawTextHelpFormatter**
        ```python
        import argparse
        # help
        parser = argparse.ArgumentParser(
        description = '''
        这是一个查询城市天气的程序。
        \t* 请输入城市或者地区的中文名称。
        \t\t例子1：上海
        \t\t例子2：浦东新区
        \t* 退出请输入quit或者exit后按回车键，不区分大小写。
        \t* 退出前会打印所有查询过的城市天气信息。
        ''', formatter_class = argparse.RawTextHelpFormatter)
        args = parser.parse_args()
        ```
        **Summary8: 
        Import argparse to add help for script. By default, ArgumentParser objects line-wrap the description and epilog texts in command-line help messages.Use the RawTextHelpFormatter class instead to indicate that you already wrapped the lines.**
       
    2. How to execute command line "py weather_report.py -h" in python script, and get the output?
    
    **Solution: import subprocess** 
    ```python
    import subprocess
    
    output = subprocess.check_output("py .\weather_report.py -h")
    ```
    And test it, garbled text is displayed.
    ![](/assets/ch1practice/encode.PNG)
    
    **Solution**: Decoding in 'gbk'
    
    **Summary9: [subprocess.check_out()](https://docs.python.org/3/library/subprocess.html) run command with arguments and return its output. If the return code is non-zero, it raises a CalledProcessError. The CalledProcessError object will have the return code in returncode attribute and any output in the output attribute. By default, this function will return the data as encoded bytes.**
    
    So here is the last function: print_help()
    ```python
    # print help
    def print_help():
        try:
            output = subprocess.check_output("py .\weather_report.py -h")
            output = output.decode("gbk")
            print("output:{0}".format(output))
        except subprocess.CalledProcessError as e:
            output = e.output
            code = e.returncode
            print(code, output)
    ```
    
    


    
 
 
    
      
  

   
                 
        















