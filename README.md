# python-project
from tkinter import *
from tkinter import messagebox

tk=Tk()
tk.title("Tic Tac Toe")

buttons=StringVar() # used to manage widgets, buttons and labels

button1 = Button(tk,text=" ",font=('Times 20 bold'),
                 bg='cyan',fg='black',height=5,width=10,
                 command=lambda:buttonClick(button1))

button1.grid(row=1,column=0,sticky = S+N+E+W)

button2 = Button(tk,text=' ',font=('Times 20 bold'),bg='cyan',fg='black',height=5,width=10,command=lambda:buttonClick(button2))
button2.grid(row=1,column=1,sticky = S+N+E+W)

button3 = Button(tk,text=' ',font=('Times 20 bold'),bg='cyan',fg='black',height=5,width=10,command=lambda:buttonClick(button3))
button3.grid(row=1,column=2,sticky = S+N+E+W)

button4 = Button(tk,text=' ',font=('Times 20 bold'),bg='cyan',fg='black',height=5,width=10,command=lambda:buttonClick(button4))
button4.grid(row=2,column=0,sticky = S+N+E+W)

button5 = Button(tk,text=' ',font=('Times 20 bold'),bg='cyan',fg='black',height=5,width=10,command=lambda:buttonClick(button5))
button5.grid(row=2,column=1,sticky = S+N+E+W)

button6 = Button(tk,text=' ',font=('Times 20 bold'),bg='cyan',fg='black',height=5,width=10,command=lambda:buttonClick(button6))
button6.grid(row=2,column=2,sticky = S+N+E+W)

button7 = Button(tk,text=' ',font=('Times 20 bold'),bg='cyan',fg='black',height=5,width=10,command=lambda:buttonClick(button7))
button7.grid(row=3,column=0,sticky = S+N+E+W)

button8 = Button(tk,text=' ',font=('Times 20 bold'),bg='cyan',fg='black',height=5,width=10,command=lambda:buttonClick(button8))
button8.grid(row=3,column=1,sticky = S+N+E+W)

button9 = Button(tk,text=' ',font=('Times 20 bold'),bg='cyan',fg='black',height=5,width=10,command=lambda:buttonClick(button9))
button9.grid(row=3,column=2,sticky = S+N+E+W)

moveCounter = 0 
bclick = True

def winner(buttons):
    
    if (button1['text'] == button2['text'] == button3['text'] == 'O'or
    button4['text'] == button5['text'] == button6['text'] == 'O'or
    button7['text'] == button8['text'] == button9['text'] == 'O'or
      
    button1['text'] == button4['text'] == button7['text'] == 'O'or
    button2['text'] == button5['text'] == button8['text'] == 'O'or
    button3['text'] == button6['text'] == button9['text'] == 'O'or
      
    button1['text'] == button5['text'] == button9['text'] == 'O'or
    button3['text'] == button5['text'] == button7['text'] == 'O'):
        messagebox.showinfo("Winner", "Player O Wins!")
        tk.destroy()
        
    elif (button1['text'] == button2['text'] == button3['text'] == 'X'or 
    button4['text'] == button5['text'] == button6['text'] == 'X'or 
    button7['text'] == button8['text'] == button9['text'] == 'X'or
         
    button1['text'] == button4['text'] == button7['text'] == 'X'or
    button2['text'] == button5['text'] == button8['text'] == 'X'or
    button3['text'] == button6['text'] == button9['text'] == 'X'or

    button1['text'] == button5['text'] == button9['text'] == 'X'or
    button3['text'] == button5['text'] == button7['text'] == 'X'):
        messagebox.showinfo("Winner", "Player X Wins!")
        tk.destroy()      

def buttonClick(buttons):
     global bclick
     global moveCounter
     
     if buttons["text"] == " " and bclick == True:
         buttons["text"] = "X"
         bclick = False
         moveCounter +=1
         
     elif buttons["text"] == " " and bclick == False:
          buttons["text"] = "O"
          bclick = True
          moveCounter +=1
          
     winner(buttons)
     
     if moveCounter == 9:
        messagebox.showinfo("Stalemate", "The game is tied.")
        tk.destroy()
            
tk.mainloop()
