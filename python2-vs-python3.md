Lession 1: Python2 vs. Python3

* **Q: Can I install both Python2 and Python3?**

  ```
  A: Yes! I installed both Python3.6 and Python2.7 in my Windows 10.
  ```

* **Q: Then how does the system locate and execute of different Python versions?**

  ```
  A: Use Python Launcher for Windows! 
    For command line: type py to launch Python3, and py -2.7 to launch Python2.7, I can also use py -2 to 
    launch the latest version2.x I have installed.

    Specify version in scripts: 
    #! python: means version2
    #! python3: means version3
    Also, I can specify a more explicit version:
    #! python2.7
  ```

![](/assets/python2 vs. python3/setup_0.png)

* **Q: I have some Python2 scripts, how I can convert them to Python3?**

  ```
  A: Use 2to3.py in ./Toos/scripts folder.
  For example: 
  $ py C:\Python\Python36-32\Tools\scripts\2to3.py ex1.py
  A diff against the original source file will be printed.

  $ py C:\Python\Python36-32\Tools\scripts\2to3.py -w ex1.py
  Write the modification to a new file, and a backup of the original file is made.

  $ py C:\Python\Python36-32\Tools\scripts\2to3.py -w -n ex1.py
  Write the modification to a new file, without backup of the original file.
  ```

* **Q: What's different between version 2 and version 3?**

  | Python2 | Python3 |
  | :--- | :--- |
  | print "Hello world!"                                                                   print "Hello world!",           | print\("Hello world!"\)                                                                 print \("Hello world!", end\(" "\)\) |
  | raw\_input\(\) | input\(\) |

###### References:

1. [https://wiki.python.org/moin/Python2orPython3](https://wiki.python.org/moin/Python2orPython3)
2. [https://docs.python.org/3/whatsnew](https://docs.python.org/3/whatsnew/)
3. Python 3.6.0 documentation



