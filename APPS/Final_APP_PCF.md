```python
from csv import *
from tkinter import * #import everything 
from tkinter import messagebox
```


```python
window=Tk() 
window.title("PCF Calculator APP")
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
    
    
# Set initial size (optional)
window.geometry("1280x720")

# Center the window
center_window(window)
```


```python
def Charging_Source(x):
    global Chg_source
    global Emission_factor_Chg_Source
    Chg_source=int(x)
    if Chg_source == 1:
        Emission_factor_Chg_Source = 500
    elif Chg_source == 2:
        Emission_factor_Chg_Source = 400
    elif Chg_source == 3:
        Emission_factor_Chg_Source = 50
    elif Chg_source == 4:
        Emission_factor_Chg_Source = 300
    else:
        Emission_factor_Chg_Source = 0  # Default value if none of the above
    
    
def Peak_Hours(x):
    global Pk_Hours
    global Emission_factor_PkHours
    Pk_Hours=int(x)
    if Pk_Hours == 1:
        Emission_factor_PkHours = 1.1
    elif Pk_Hours == 2:
        Emission_factor_PkHours = 1
    else:
        Emission_factor_PkHours = 0  # Default value if none of the above
    
def Answer():
    global pcf
    global KWhs_val
    KWhs_val=int(Kwh.get())
    print("Source",Chg_source)
    print("Source Emissions factor",Emission_factor_Chg_Source)
    print("Peak hours",Pk_Hours)
    print("Peak Hours factor",Emission_factor_PkHours)
    print("Kwhs value",KWhs_val)
    
    pcf = Emission_factor_Chg_Source * Emission_factor_PkHours * KWhs_val;
    Output.insert(0,pcf)
    messagebox.showinfo("Information","Calculation Success")
               
            
def Clear():
    Kwh.delete(0,END)
    Output.delete(0,END)
    messagebox.showinfo("Information","Clear Success")
    
```


```python
label1=Label(window,text="Charging Source:",font=("Verdana",12,"bold"),fg="green",padx=10,pady=10)

Souce1=Button(window,text="Gas Station1(less green)",command=lambda:Charging_Source("1"),padx=10,pady=5,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
Souce2=Button(window,text="Gas Station2(more green)",command=lambda:Charging_Source("2"),padx=10,pady=5,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
Souce3=Button(window,text="Home(Solar)",command=lambda:Charging_Source("3"),padx=10,pady=5,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
Souce4=Button(window,text="Office",command=lambda:Charging_Source("4"),padx=10,pady=5,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')

label2=Label(window,text="Time of the day:",font=("Verdana",12,"bold"),fg="green",padx=10,pady=10)

Time1=Button(window,text="Peak Hours",command=lambda:Peak_Hours("1"),padx=10,pady=5,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')
Time2=Button(window,text="Off Peak Hours",command=lambda:Peak_Hours("2"),padx=10,pady=5,borderwidth=3,font=("Verdana",10,"bold"),bg='lightblue')

label3=Label(window,text="How many KWhs:",font=("Verdana",12,"bold"),fg="green",padx=10,pady=10)
Kwh=Entry(window,width=10,font=('Arial', 12), bg='lightgray',borderwidth=5)

Clear=Button(window,text="Clear",command=Clear,padx=10,pady=5,borderwidth=3,font=("Verdana",10,"bold"),bg='yellow')
Calculate=Button(window,text="Calculate", command=Answer,padx=10,pady=5,borderwidth=3,font=("Verdana",10,"bold"),bg='magenta')

label4=Label(window,text="CO2 Emissions (Tons):",font=("Verdana",14,"bold"),fg="blue",padx=10,pady=10)
Output=Entry(window,width=15, font=('Arial', 14), bg='lightgray',borderwidth=7)

exit=Button(window,text=" Exit ",padx=10,pady=5,command=window.quit,borderwidth=3,font=("Verdana",10,"bold"),bg='red')
```


```python
label1.grid(row=0,column=0)

Souce1.grid(row=0,column=1)
Souce2.grid(row=0,column=2)
Souce3.grid(row=0,column=3)
Souce4.grid(row=0,column=4)

label2.grid(row=1,column=0)

Time1.grid(row=1,column=1)
Time2.grid(row=1,column=2)

label3.grid(row=2,column=0)
Kwh.grid(row=2,column=1)

Clear.grid(row=6,column=1)
Calculate.grid(row=6,column=2)

label4.grid(row=7,column=0)
Output.grid(row=7,column=1)

exit.grid(row=9,column=1)
```


```python
window.mainloop()
```


```python

```
