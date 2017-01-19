### Label and Entry Widget

#### Create a simple Entry Widget with Label
```python
import tkinter as tk


class App(tk.Frame):

    def __init__(self, master):
        tk.Frame.__init__(self, master)
        self.master = master
        self.pack()
        self.create_widgets()

    def create_widgets(self):
        self.label = tk.Label(self, text='city')
        self.label.pack()
        self.entry = tk.Entry(self)
        self.entry.pack()


if __name__ == '__main__':
    root = tk.Tk()
    app = App(root)
    app.mainloop()
```
#### Parameters
```python
self.font = tk.font.Font(family='Times', size=12, weight=tk.font.BOLD)
self.label = tk.Label(self, text='city', bg='sky blue', width=10, anchor=tk.W, font=self.font)
self.label.pack(side=tk.LEFT)
self.entry = tk.Entry(self, relief=tk.SUNKEN)
self.entry.pack(side=tk.RIGHT)
```
![](/assets/ch2/tkentry.PNG)

|Parameters|Description|Example|
|:---|:---|:---|
|text|text displayed in the label|text='city'|
|bg|the backgroud color|bg='sky blue'|
|width|the width of the label|width=10|
|anchor|control where the text is positioned, default is CENTER|anchor='tk.W'|
|font|the font used for text|font=self.font|
|relief|the appearance of a decorative border about the label,default is FLAT|relief=tk.SUNKEN|

#### Constants 

* anchor

![](/assets/ch2/tkanchor.jpg)

* relief

![](/assets/ch2/tkrelief.PNG)

#### Functions

```python
self.entry.focus_set()
self.entry.bind('<Return>', self.query_weather)
city = self.entry.get()
```





