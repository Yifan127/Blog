### dictionary

#### 2 ways to create a new dictionary
 
 ```python
     weather_dict = {}
     weather_dict = dict()
 ```
 
#### 2 ways to add new key:value to dictionary
 
 ```python
     weather_dict[data[0]] = data[1]
     weather_dict.update = ({data[0]: data[1]})
 ```
 
 So, I have a function as below: it converts a string like '北京，晴' to an item in a dictionary like '北京：晴'
 
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
 
#### Check if a dictionary has a key
 
 At first, I try this:
 
         weather_dict.has_key(city)
 But get below exception:
 
         AttributeError: 'dict' object has no attribute 'has_key'    
 The reason is **dict.has_key()** is removed in Python3, and use **in** operator instead. Like this:
     
 **Summary: Use "if key in dict:" to check whether the key is exist in a dictionary in Python3.**
 
 So the script looks like this:
 ```python
 weather_dict = convert_txt_to_dict(filename)
 while True:
        print("Welcome to query weather report\n\t* Please input city name\n\t* To quit, input quit or exit")
        choice = input("> ")
        choice = choice.strip()   

        if choice in weather_dict:
            print_weather_report(choice)
        elif choice.lower() == "quit" or choice.lower() == "exit":
            print_history_exit(weather_history)
        elif choice.lower() == "help" or choice.lower() == "h":
            print_help()
        else:
            print("!!!Cannot find city [{0}]!!!\n".format(choice))
 ```

#### 3 ways to check if the dictionary is empty
 
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
 
 **Summary: Any object can be tested for truth value, for use in an if or while condition.** 

 The following values are considened false: 
 * None
 * False
 * zero of any numeric type: 0,0.0
 * any empty sequence, '',(),[]
 * any empty mapping, {}
 * instance of user-defined classes, if the class defines a \_\_bool\_\_() or \_\_len()\_\_ method, when that returns the integer zero or bool value False.
 
All other values are considered true.
 
 
