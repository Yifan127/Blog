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
```python
import idlelib.tooltip

idlelib.tooltip.ToolTip(self.history_button, 'Print history records')
```

![](/assets/ch2/tkbutton.PNG)









