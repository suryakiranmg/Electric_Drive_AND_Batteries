```python
from csv import *
from tkinter import * #import everything 
from tkinter import messagebox
```


```python
window=Tk() 
window.title("My Data Entry APP")
```




    ''




```python
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
# Set initial size (optional)
window.geometry("300x200")

# Center the window
center_window(window)
```


```python
main_lst=[]
```


```python
'''[["Suki",20,1234],["kiran",45,4567],["john",56,56789]]'''

def Add():
    lst=[name.get(),age.get(),contact.get()]
    print(lst)
    main_lst.append(lst)
    messagebox.showinfo("Information","Add Success")
    
    
def Save():
    with open("suki.csv","w") as file:
        Writer=writer(file)
        Writer.writerow(["Name","Age","Contact"])
        Writer.writerows(main_lst)
        messagebox.showinfo("Information","Save Success")
      

```


```python
def Clear():
    name.delete(0,END)
    age.delete(0,END)
    contact.delete(0,END)
```

### 3 Lables, 4 buttons, 3 entry fields 



```python
label1=Label(window,text="Name:",font=("Verdana",10,"bold"),fg="green",padx=10,pady=10)
label2=Label(window,text="Age:",font=("Verdana",10,"bold"),fg="green",padx=10,pady=10)
label3=Label(window,text="Contact:",font=("Verdana",10,"bold"),fg="green",padx=10,pady=10)

name=Entry(window,width=10, font=('Arial', 12), bg='lightgray',borderwidth=5)
age=Entry(window,width=10, font=('Arial', 12), bg='lightgray',borderwidth=5)
contact=Entry(window,width=10, font=('Arial', 12), bg='lightgray',borderwidth=5)

save=Button(window,text="Save",padx=10,pady=5,command=Save,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
add=Button(window,text=" Add ",padx=10,pady=5,command=Add,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
clear=Button(window,text="Clear",padx=10,pady=5,command=Clear,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
exit=Button(window,text=" Exit ",padx=10,pady=5,command=window.quit,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
```


```python
label1.grid(row=0,column=0)
label2.grid(row=1,column=0)
label3.grid(row=2,column=0)

name.grid(row=0,column=1)
age.grid(row=1,column=1)
contact.grid(row=2,column=1)

save.grid(row=4,column=0,columnspan=2)
add.grid(row=3,column=0,columnspan=2)
clear.grid(row=5,column=0,columnspan=2)
exit.grid(row=6,column=0,columnspan=2)
```


```python
window.mainloop()
```


```python

```


```python
print(main_lst)
```


```python
messagebox.showerror("OOps","An error occured")
```
