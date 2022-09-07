# my_calcultor
#My first ever GUI App using Tkinter
from tkinter import *
from math import sqrt
from math import pi

root = Tk()
root.title("Basic Calculator")
root.iconbitmap("cal_image.GIF")

inputArea = Entry(root, width=20, borderwidth=12, justify="right", font="bold")
inputArea.grid(row=0, column=0, columnspan=4, padx=10, pady=10)


def button_click(num):
    current = inputArea.get()
    inputArea.delete(0, END)
    inputArea.insert(END, str(current) + str(num))


def button_sqrt():
    current = inputArea.get()
    inputArea.delete(0, END)
    inputArea.insert(0, (sqrt(eval(current))))


def button_pi():
    inputArea.delete(0, END)
    inputArea.insert(0, pi)


def button_clear():
    inputArea.delete(0, END)


def button_del():
    try:
        number = str(inputArea.get())
        inputArea.delete(0, END)
        inputArea.insert(0, number.rstrip(number[-1]))
    except IndexError:
        pass


def button_equal():
    answer = eval(inputArea.get())
    inputArea.delete(0, END)
    inputArea.insert(0, answer)


# create buttons
button_1 = Button(root, text="1", padx=20, pady=10, command=lambda: button_click(1))
button_2 = Button(root, text="2", padx=20, pady=10, command=lambda: button_click(2))
button_3 = Button(root, text="3", padx=20, pady=10, command=lambda: button_click(3))
button_4 = Button(root, text="4", padx=20, pady=10, command=lambda: button_click(4))
button_5 = Button(root, text="5", padx=20, pady=10, command=lambda: button_click(5))
button_6 = Button(root, text="6", padx=20, pady=10, command=lambda: button_click(6))
button_7 = Button(root, text="7", padx=20, pady=10, command=lambda: button_click(7))
button_8 = Button(root, text="8", padx=20, pady=10, command=lambda: button_click(8))
button_9 = Button(root, text="9", padx=20, pady=10, command=lambda: button_click(9))
button_0 = Button(root, text="0", padx=20, pady=10, command=lambda: button_click(0))

button_point = Button(root, text=".", padx=20, pady=7, font="bold", command=lambda: button_click('.'))
button_sub = Button(root, text="-", padx=21.4, pady=10, bg="grey", command=lambda: button_click("-"))
button_add = Button(root, text="+", padx=20, pady=10, bg="grey", command=lambda: button_click('+'))
button_div = Button(root, text="÷", padx=20, pady=10, bg="grey", command=lambda: button_click('/'))
button_mul = Button(root, text="×", padx=20, pady=10, bg="grey", command=lambda: button_click('*'))
button_sqrt = Button(root, text="√", padx=18, pady=10, bg="powder blue", command=button_sqrt)
button_pi = Button(root, text="π", padx=15, pady=8, bg="powder blue", font="bold", command=button_pi)
button_clear = Button(root, text="AC", padx=10, pady=8, bg="powder blue", font="bold", command=button_clear)
button_del = Button(root, text="del", padx=12, pady=8, bg="powder blue", font="bold", command=button_del)
button_equal = Button(root, text="=", padx=18, pady=7, font="bold", fg="blue", command=button_equal)

# add buttons on the screen
button_1.grid(row=4, column=0)
button_2.grid(row=4, column=1)
button_3.grid(row=4, column=2)
button_sub.grid(row=4, column=3)
button_4.grid(row=3, column=0)
button_5.grid(row=3, column=1)
button_6.grid(row=3, column=2)
button_7.grid(row=2, column=0)
button_8.grid(row=2, column=1)
button_9.grid(row=2, column=2)
button_0.grid(row=5, column=0)
button_point.grid(row=5, column=1)
button_equal.grid(row=5, column=2)
button_add.grid(row=5, column=3)
button_div.grid(row=3, column=3)
button_mul.grid(row=2, column=3)
button_pi.grid(row=1, column=1)
button_clear.grid(row=1, column=2)
button_del.grid(row=1, column=3)
button_sqrt.grid(row=1, columnspan=1, column=0)

root.mainloop()
