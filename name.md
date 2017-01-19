### \_\_name\_\_

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

![](/assets/ch1/maincheck.PNG)

**Summary: A module's \_\_name\_\_ is set to "\_\_main\_\_" when read from standard input, a script, or from an interactive prompt. **

A reason for doing this is that sometimes you write a module, and it can be executed directly. Alternatively, it can also be imported and used in another module. By doing the main check, you can have that code only execute when you want to run the module as a program and not have it execute when someone just wants to import your module and call your functions themselves.

