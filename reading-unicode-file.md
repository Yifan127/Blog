### Reading File

#### 3 ways to read a file:

1. **read()**: Read the entire file, return string or bytes
2. **readline()**: Read a single line of a file
3. **readlines()**: Read all the lines of a file in a list 

```python
# read()
# open a file in read mode
file = open("weather_info.txt")
str_read = file.read()
print(str_read)
# close the file
file.close()

```
output:

![](/assets/ch1practice/read.PNG)   

```python
# readline
# open a file in read mode
file = open("weather_info.txt")
str_readline = file.readline()
print(str_readline)
# close the file
file.close()

```
output:
    
![](/assets/ch1practice/readline.PNG)


```python
# readlines
# open a file in read mode
file = open("weather_info.txt")
list_readlines = file.readlines()
print(list_readlines)
# close the file
file.close()

```
output:

![](/assets/ch1practice/readlines.PNG)

 **Summary : Use readlines() to get a list, each line in the file is an element in the list. Although readline() is not very efficiency, but it is useful when the file is extremely large, like 2GB, because if using read(), it will read the entire file and occupy more then 2GB RAM.**
     
#### Good practice to use with 

  ```python
  with open("weather_info.txt") as file:
      list = file.readlines()
  print(file.closed)
  ```  
  
 output
 
    True
    
**Summary: Use with to deadling with file object, the advantage is:  file is properly closed, even if an exception is raised.**

After reading the file to a list, loop over the list to get each line

  ```python
  with open("weather_info.txt") as file:
      for line in file.readlines():
          line = line.strip()
          data = line.split(',')
  ```
