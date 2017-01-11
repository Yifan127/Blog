### Exit

To quit , I find two similar functions:**exit()** and **sys.exit()**, what's the difference?
 
 **Summary: They all raising SystemExit, exit() is a helper for the interactive shell, sys.exit() is intended for use in programs. Refer to [an answer in stackoverflow](http://stackoverflow.com/questions/6501121/difference-between-exit-and-sys-exit-in-python)**
 
 And now, I have other two functions:
 
 To get weather info and save the query history to a dictionary named weather_history:
 
 ```python
 def print_weather_report(city):
    weather = weather_dict[city]
    if not weather:
        print("!!!Cannot find the weather of city {0}}!!!\n".format(city))
    else:
        print("-" * 20)
        print("{0}: {1}".format(city, weather))
        print("-" * 20)
        weather_history[city] = weather
 ```
 To print history and exit.
 
 ```python
 def print_history_exit(weather_history):
    length = len(weather_history)
    if length != 0:
        print("You have queried {0} cities：".format(length))
        print("-" * 20)
        for key in weather_history:
            print("{0}: {1}".format(key, weather_history[key]))
        print("-" * 20)
    print("Goodbye!")
    exit(0)
```
