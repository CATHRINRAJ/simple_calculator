from tkinter import *

expression = ""


# Function to update expression
def press(num):

	global expression

	
	expression = expression + str(num)
	equation.set(expression)


# Function to evaluate the final expression
def equalpress():
	
	try:

		global expression

		
		total = str(eval(expression))

		equation.set(total)

		
		expression = ""

	
	except:

		equation.set(" error ")
		expression = ""


# Function to clear the contents

def clear():
	global expression
	expression = ""
	equation.set("")


# Driver code
if __name__ == "__main__":
	
	cal = Tk()

	
	cal.configure(background="grey")

	
	cal.title("basic Calculator")

	
	cal.geometry("270x250")

	
	equation = StringVar()

	
	expression_field = Entry(cal, textvariable=equation)

	
	expression_field.grid(columnspan=4, ipadx=70)
    
    
	
	but1 = Button(cal, text=' 1 ', fg='black', bg='pink',
					command=lambda: press(1), height=3, width=10)
	but1.grid(row=2, column=0)

	but2 = Button(cal, text=' 2 ', fg='black', bg='pink',
					command=lambda: press(2), height=3, width=10)
	but2.grid(row=2, column=1)

	but3 = Button(cal, text=' 3 ', fg='black', bg='pink',
					command=lambda: press(3), height=3, width=10)
	but3.grid(row=2, column=2)

	but4 = Button(cal, text=' 4 ', fg='black', bg='pink',
					command=lambda: press(4), height=3, width=10)
	but4.grid(row=3, column=0)

	but5 = Button(cal, text=' 5 ', fg='black', bg='pink',
					command=lambda: press(5), height=3, width=10)
	but5.grid(row=3, column=1)

	but6 = Button(cal, text=' 6 ', fg='black', bg='pink',
					command=lambda: press(6), height=3, width=10)
	but6.grid(row=3, column=2)

	but7 = Button(cal, text=' 7 ', fg='black', bg='pink',
					command=lambda: press(7), height=3, width=10)
	but7.grid(row=4, column=0)

	but8= Button(cal, text=' 8 ', fg='black', bg='pink',
					command=lambda: press(8), height=3, width=10)
	but8.grid(row=4, column=1)

	but9 = Button(cal, text=' 9 ', fg='black', bg='pink',
					command=lambda: press(9), height=3, width=10)
	but9.grid(row=4, column=2)

	but0 = Button(cal, text=' 0 ', fg='black', bg='pink',
					command=lambda: press(0), height=3, width=10)
	but0.grid(row=5, column=1)

	plus = Button(cal, text=' + ', fg='black', bg='pink',
				command=lambda: press("+"), height=3, width=10)
	plus.grid(row=2, column=3)

	minus = Button(cal, text=' - ', fg='black', bg='pink',
				command=lambda: press("-"), height=3, width=10)
	minus.grid(row=3, column=3)

	multiply = Button(cal, text=' * ', fg='black', bg='pink',
					command=lambda: press("*"), height=3, width=10)
	multiply.grid(row=4, column=3)

	divide = Button(cal, text=' / ', fg='black', bg='pink',
					command=lambda: press("/"), height=3, width=10)
	divide.grid(row=5, column=3)

	equal = Button(cal, text=' = ', fg='black', bg='pink',
				command=equalpress, height=3, width=10)
	equal.grid(row=5, column=2)
    
 
    Decimal= Button(cal, text='.', fg='black', bg='pink',
                    command=lambda: press('.'), height=3, width=10)
    Decimal.grid(row=5, column=0)
    clear = Button(cal, text='Clear', fg='black', bg='pink', command=clear, height=3, width=30)
    clear.grid(row=6, column=1,columnspan =3,pady=1)
    
   
	
# start the GUI
cal.mainloop()
