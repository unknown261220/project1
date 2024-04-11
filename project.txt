
from tkinter import *

def click(event):
    global scvalue
    text = event.widget.cget("text")
    if text == "=":
        if scvalue.get().isdigit():
            value = int(scvalue.get())
        else:
            try:
                value = eval(screen.get())

            except Exception as e:
                print(e)
                value = "Error"


        scvalue.set(value)
        screen.update()

    elif text == "C":
        scvalue.set("")
        screen.update()

    else:
        scvalue.set(scvalue.get() + text)
        screen.update()

root = Tk()
root.geometry("644x700")
root.title("Calculator By CodeWithHarry")
# root.wm_iconbitmap("1.ico")

scvalue = StringVar()
scvalue.set("")
screen = Entry(root, textvar=scvalue, font="lucida 40 bold")
screen.pack(fill=X, ipadx=8, pady=10, padx=10)

f = Frame(root, bg="grey")
b = Button(f, text="9", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="8", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="7", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

f.pack()


f = Frame(root, bg="grey")
b = Button(f, text="6", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="5", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="4", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

f.pack()


f = Frame(root, bg="grey")
b = Button(f, text="3", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="2", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="1", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

f.pack()


f = Frame(root, bg="grey")
b = Button(f, text="0", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="-", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="*", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

f.pack()


f = Frame(root, bg="grey")
b = Button(f, text="/", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="%", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="=", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

f.pack()

f = Frame(root, bg="grey")
b = Button(f, text="C", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text=".", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

b = Button(f, text="00", font="lucida 35 bold")
b.pack(side=LEFT)
b.bind("<Button-1>", click)

f.pack()

scrollbar = Scrollbar(root)
scrollbar.pack(side=RIGHT, fill=Y)
text1 = Text(root, yscrollcommand=scrollbar.set, font="helvetica 10 bold")
text1.pack(fill=BOTH) 
scrollbar.config(command=text1.yview)

root.mainloop()
