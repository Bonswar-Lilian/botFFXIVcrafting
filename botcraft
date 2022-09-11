import pynput.keyboard as kb
import random
import time
import threading
from tkinter import *
from tkinter import messagebox
import pynput.mouse as ms
import pynput.keyboard as kb
mouse = ms.Controller()
keyboard = kb.Controller()
import time
import random
keyboard = kb.Controller()
running = False

event = time.time()
def start():
    global running
    running = True

def clique():
    time.sleep(random.uniform(0.01, 0.06))
    mouse.press(ms.Button.left)
    time.sleep(random.uniform(0.01, 0.06))
    mouse.release(ms.Button.left)
    time.sleep(random.uniform(0.01, 0.06))


def bougersouris(x, y):
    mouse.position = (x + random.randint(-3, 3), y + random.randint(-3, 3))
    pause()

def pause():
    time.sleep(random.uniform(0.5, 0.7))


def stop():
    global running
    running = False


def random_press(y):  # Fonction qui permet de rester appuyer sur une touche pendant 0.5sec
    timer = 0
    while timer < random.uniform(0.5, 0.8):
        time.sleep(0.1)
        timer += 0.1
        keyboard.press(y)
    keyboard.release(y)

def le_cheat():
    print("+1 pot")
    bougersouris(1261, 739)
    clique()
    time.sleep(random.uniform(3.2, 3.5))
    keyboard.press('r')
    pause()
    keyboard.release('r')

y = 0


def truc():
    global event
    event = time.time()
    le_cheat()
    test()


def event_minute_later(event, a):
    return event + a < time.time()

def test():
    global y
    y = random.randint(57, 60)

def showMsg():
    global y
    if running:
        if event_minute_later(event, y):
            truc()
    root.after(10, showMsg)


def start():
    time.sleep(3)
    le_cheat()
    global running
    global w2
    w2.destroy()
    w2 = Label(root, text="En pleine session de cheating de craft")
    w2.grid()
    running = True
    test()


def stop():
    global running
    global w2
    running = False
    w2.destroy()
    w2 = Label(root, text="tu cheat pas , GG")
    w2.grid()


root = Tk()
root.title("BOT FF POUR BRASSER UN MAX DE GILS")
root.geometry("400x100")
w = Label(root, text="Clique la pour lancer le bot craft")
app = Frame(root)
app.grid()

w2 = Label(root, text="tu cheat pas , GG")
w2.grid()

start = Button(app, text="Début du cheat", command=start)
stop = Button(app, text="Fin du cheat", command=stop)

start.grid()
stop.grid()

root.after(1000, showMsg)  # After 1 second, call scanning
root.mainloop()
