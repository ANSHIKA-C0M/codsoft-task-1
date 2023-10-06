# codsoft
from tkinter import *


def click(event):
  global datavalue
  text = event.widget.cget("text")
  print(text)
  if text == "=":
    if datavalue.get().isdigit():
      value = int(datavalue.get())
    else:
      value = eval(screen.get())

    datavalue.set(value)
    screen.update()
  elif text == "c":
    datavalue.set("")
    screen.update()
  else:
    datavalue.set(datavalue.get() + text)
    screen.update()

root = Tk()
root.geometry("500x550")
root.title("calculator by Anshika")

datavalue = StringVar()
datavalue.set("")
screen = Entry(root, textvar=datavalue, font="arial 40 ")
screen.pack(fill=X, ipadx=10, pady=12, padx=12)
   
#frame 1
f = Frame(root, bg="grey")
b = Button(f, text="1", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="2", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="3", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="c", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)
f.pack()

#frame 2
f = Frame(root, bg="grey")
b = Button(f, text="4", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="5", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="6", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="*", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)
f.pack()
#frame 3
f = Frame(root, bg="grey")
b = Button(f, text="7", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="8", padx=34, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="9", padx=35, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="-", padx=37, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)
f.pack()

#frame 4
f = Frame(root, bg="grey")
b = Button(f, text="=", padx=33, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="0", padx=33, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text="+", padx=32, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)

b = Button(f, text=" /", padx=30, pady=20, font="arial 30 bold ")
b.pack(side=LEFT)
b.bind("<Button>", click)
f.pack()


root.mainloop()

