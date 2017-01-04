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

![](/assets/setup_0.png)

* **Q: I have some Python2 scripts, how I can convert them to Python3?**

  ```
  A: Use 2to3.py in ./Toos/scripts folder.
  For example: $ py C:\Users\Yifan\AppData\Local\Programs\Python\Python36-32\Tools\scripts ex1.py
  ```

* **Q: What's different between version 2 and version 3?**

  ```
  A: So far, I have found 2 differences:

  print\(\) is a function in Python3.
  In Python2: print "Hello World!"
  In Python3: print \("Hello World!"\)

  raw\_input\(\) was renamed to input\(\).
  ```

References:

1. https://wiki.python.org/moin/Python2orPython3
2. https://docs.python.org/3/whatsnew/3.0.html\#porting-to-python-3-0
3. Python 3.6.0 documentation



