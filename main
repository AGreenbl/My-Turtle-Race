import turtle
import random
import time

# x is an unseen turtle which will write for us the scores of the other turtles
x = turtle.Turtle()
x.getscreen().screensize(canvwidth=300, canvheight=300)
x.getscreen().bgpic('race field.png')
x.hideturtle()
x.penup()
x.speed(-1)

# Making a class for a turtle
class Ninja_turtle:

    def __init__(self, name, color, pos):
        self.turtle = turtle.Turtle()
        self.name_tag = name
        self.turtle.setheading(90)
        self.color = self.turtle.color(color)
        self.turtle.shape('turtle')
        self.turtle.penup()
        self.STARTpos = self.turtle.setposition(pos)

    def move_forward(self, dis):
        self.turtle.pendown()
        self.turtle.forward(dis)

    def clear(self):
        self.turtle.clear()

    def remove(self):
        self.turtle.hideturtle()

    def get_name(self):
        return self.name_tag

# checking to see which turtle got the biggest y value at the end of the race
def check_for_winner():
    ranks = {}
    maxY = 0
    leader = ''
    leader2 = ''

    # Creating a dict with a ninja's name and its finish y value
    global ninjas
    for i in ninjas:
        ranks[i.get_name()] = i.turtle.ycor()

    for key, value in ranks.items():

        if value > maxY and leader2 == '':
            maxY = value
            leader = key

        elif value == maxY:
            leader2 = key

        elif value > maxY and leader2 != '':
            maxY = value
            leader = key
            leader2 = ''

    global rs, ls, ds, ms
    for i in ninjas:

        if i.get_name() == leader or leader2:

            if i.get_name() == 'Rafael':
                rs += 1

            if i.get_name() == 'Leonardo':
                ls += 1

            if i.get_name() == 'Donatelo':
                ds += 1

            if i.get_name() == 'Michaelanjelo':
                ms += 1

# Using turtle x for writing the score of the other turtles
def write_score():
    global rs, ls, ds, ms
    x.clear()

    x.color('red')
    x.goto((-307, -300))
    x.write(rs, font=("Italic", 20, "normal"))

    x.color('blue')
    x.goto((-187, -300))
    x.write(ls, font=("Italic", 20, "normal"))

    x.color('purple')
    x.goto((-57, -300))
    x.write(ds, font=("Italic", 20, "normal"))

    x.color('orange')
    x.goto((93, -300))
    x.write(ms, font=("Italic", 20, "normal"))


def main():
    global rs, ls, ds, ms
    rs, ls, ds, ms = 0, 0, 0, 0

    # Writing initial socre
    write_score()

    while True:
        # Making the turtles
        rafael = Ninja_turtle('Rafael', 'red', (-300, -250))
        leonardo = Ninja_turtle('Leonardo', 'blue', (-180, -250))
        donatelo = Ninja_turtle('Donatelo', 'purple', (-50, -250))
        michaelanjelo = Ninja_turtle('Michaelanjelo', 'orange', (100, -250))

        global ninjas
        ninjas = [rafael, leonardo, donatelo, michaelanjelo]

        # Moving the turtles forward in a random length
        for i in range(6):
            rafael.move_forward(random.randint(50, 100))
            leonardo.move_forward(random.randint(50, 100))
            donatelo.move_forward(random.randint(50, 100))
            michaelanjelo.move_forward(random.randint(50, 100))

        check_for_winner()
        write_score()

        time.sleep(2.5)

        for i in ninjas:
            i.remove()

        for i in ninjas:
            i.clear()


main()
