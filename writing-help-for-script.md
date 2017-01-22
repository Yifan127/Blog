### Writing Help For A Script

The first thing comes to my mind about help is like this:

Executing the script with -h, then a usage is printed to Windows PowerShell.

    py weather_report.py -h
    
So, to implement this requirement, I have two sub tasks:

#### 1. Add a description for the script

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

![](/assets/ch1/help.PNG)

Then the new question is how to display the argparse help in multiple lines? 
    
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
**Summary: 
Import argparse to add help for script. By default, ArgumentParser objects line-wrap the description and epilog texts in command-line help messages.Use the RawTextHelpFormatter class instead to indicate that you already wrapped the lines.**
   
#### 2. How to execute a command line 

How to execute "py weather_report.py -h" in python script, and get the output?


**Solution: import subprocess** 
```python
import subprocess

output = subprocess.check_output("py .\weather_report.py -h")
```
And test it, garbled text is displayed.
![](/assets/ch1/encode.PNG)

**Solution**: Decoding in 'gbk'

**Summary: [subprocess.check_out()](https://docs.python.org/3/library/subprocess.html) run command with arguments and return its output. If the return code is non-zero, it raises a CalledProcessError. The CalledProcessError object will have the return code in returncode attribute and any output in the output attribute. By default, this function will return the data as encoded bytes.**

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
