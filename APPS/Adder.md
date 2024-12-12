```python
from tkinter import * #import everything 
window=Tk() 
#window.geometry("1280*720")
```


```python
def sum():
    a=int(entry1.get())
    b=int(entry2.get())
    c=a+b
    result.insert(0,c)  #insert(index,value)
    
def delete():
    entry1.delete(0,END) 
    entry2.delete(0,END) 
    result.delete(0,END) 
    
def center_window(window):
    window.update_idletasks()
    width = window.winfo_width()
    height = window.winfo_height()
    screen_width = window.winfo_screenwidth()
    screen_height = window.winfo_screenheight()
    
    x = (screen_width - width) // 2
    y = (screen_height - height) // 2
    
    window.geometry(f'{width}x{height}+{x}+{y}')
```


```python
window.geometry("300x200")

# Center the window
center_window(window)
```


```python
mylabel1=Label(window,text="Enter the first number:",font=("Verdana",10,"bold"),fg="green",padx=10,pady=10)
mylabel2=Label(window,text="Enter the second number:",font=("Verdana",10,"bold"),fg="green",padx=10,pady=10)
entry1=Entry(window,width=10, font=('Arial', 12), bg='lightgray',borderwidth=5)
entry2=Entry(window,width=10, font=('Arial', 12), bg='lightgray',borderwidth=5)
result=Entry(window,width=10, font=('Arial', 12), bg='lightgreen',borderwidth=5)
add=Button(window,text="Add",padx=10,pady=5,command=sum,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
clear=Button(window,text="Clear",padx=10,pady=5,command=delete,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
```


```python
mylabel1.grid(row=0,column=0)
mylabel2.grid(row=1,column=0)
entry1.grid(row=0,column=1)
entry2.grid(row=1,column=1)
add.grid(row=2,column=0)
result.grid(row=3,column=0)
clear.grid(row=2,column=1)
```


```python
window.mainloop()
```


```python

```
