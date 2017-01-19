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

|Parameters|Description|Example|
|:---|:---|:---|
|bg|||
|anchor|||
|fond|||

#### Functions







