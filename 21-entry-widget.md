### Entry Widget

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
self.label = tk.Label(self, text='city', bg='sky blue', anchor='tk.W', font=self.font )
```
![](/assets/ch2/tkentry.png)

|Parameters|Description|Example|
|:---|:---|:---|
|text|text displayed in the label|text='city'|
|bg|the backgroud color|bg='sky blue'|
|anchor|control where the text is positioned|anchor='tk.W'|
|font|the font used for text|font=self.font|

#### Constants for Anchor

![](/assets/ch2/tkanchor.jpg)
#### Functions







