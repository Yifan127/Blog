### Button Widget

#### Create a simple Button Widget
```python
import tkinter as tk


class App(tk.Frame):

    def __init__(self, master):
        super().__init__(master)
        self.master = master
        self.pack()
        self.initUI()

    def initUI(self):
        self.history_button = tk.Button(self, text='history', command=self.print_history)
        self.history_button.pack()

    def print_history(self):
        print('history')

if __name__ == '__main__':
    root = tk.Tk()
    app = App(root)
    app.mainloop()
```
#### Add icon to button
```python
self.history_icon = tk.PhotoImage(file='history.png')
self.history_button = tk.Button(self, image=self.history_icon, command=self.print_history, bg='sky blue')
```
#### Add tooltip for button

|Parameters|Description|Example|
|:---|:---|:---|
|text|text displayed in the label|text='city'|
|bg|the backgroud color|bg='sky blue'|
|width|the width of the label|width=10|
|anchor|control where the text is positioned, default is CENTER|anchor='tk.W'|
|font|the font used for text|font=self.font|
|relief|the appearance of a decorative border about the label,default is FLAT|relief=tk.SUNKEN|

#### Constants 

* **anchor**

![](/assets/ch2/tkanchor.jpg)

* **relief**

![](/assets/ch2/tkrelief.PNG)

#### Functions

```python
self.entry.focus_set()
self.entry.bind('<Return>', self.query_weather)

def query_weather(self, event):
    city = self.entry.get()
    city = city.strip()
    self.entry.delete(0, tk.END)
```
|Functions|Description|
|:---|:---|:---|
|focus_set()|set the focus to the entry|
|bind('<Return>', self.query_weather)|press Enter, then self.query_weather is called|
|get()|get the text in entry|
|delete(0, tk.END)|delete the text in entry|







