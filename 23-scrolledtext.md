### Scrolledtext Widget

#### Create a simple Scrolledtext Widget
```python
import tkinter as tk
import tkinter.font
import tkinter.scrolledtext

class App(tk.Frame):

    def __init__(self, master):
        super().__init__(master)
        self.master = master
        self.pack()
        self.initUI()

    def initUI(self):
        self.font = tk.font.Font(family='Times', size=12, weight=tk.font.BOLD)
        self.scrolledtext = tkinter.scrolledtext.ScrolledText(self, font=self.font, width=30, height=5)
        self.scrolledtext.pack()

    def print_history(self):
        print('history')

if __name__ == '__main__':
    root = tk.Tk()
    app = App(root)
    app.mainloop()
```
![](/assets/ch2/tkscrolledtext.PNG)
#### Use Parameter

|Parameters|Description|Example|
|:---|:---|:---|
|state|default is NORMAL. If you don't want the text widget get response from keyboard or mouse, set to DISABLED|state=tk.DISABLED|

#### Functions
```python
def write_scrolledtext(self, message):
    self.scrolledtext.config(state=tk.NORMAL)
    self.scrolledtext.delete(1.0, tk.END)
    self.scrolledtext.insert(tk.INSERT, message)
    self.scrolledtext.config(state=tk.DISABLED)
```
|Function|Description|Example|
|:---|:---|:---|
|delete(startindex [,endindex])|delete characters in the widget|delete(1.0, tk.END)|
|insert(index [,string]...)|insert string to widget|insert(tk.INSERT, 'message')|

#### Index Type

|Index|Description|
|:---|:---|:---|
|line.column|for example, 1.0 means line 1, column 0|
|tk.INSERT|the position of the insertion cursor|
|tk.END|the position after the last character of a text|








