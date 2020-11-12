## turtle — Turtle graphics

Turtle graphic implements a subset functions of the [Python Turtle Module](https://docs.python.org/2/library/turtle.html).

### Setup

```python
from turtle import Turtle

# Generate Turtle object, name it like your pet
nick = Turtle()
```

Now you have your own turtle (in this example I called it *nick*, but you can change it), there are several functions you can use to control your turtle.

### Move and draw

* ```turtle.forward(distance)``` or ```turtle.fd(distance)``` : Move the turtle forward by *distance*, in the direction the turtle is headed.
* ```turtle.backward(distance)``` or ```turtle.back(distance)``` or ```turtle.bk(distance)``` : Move the turtle backward by *distance*, opposite to the direction the turtle is headed. This function doesn't change turtle's heading.
* ```turtle.right(angle)``` or ```turtle.rt(angle)``` : Turn turtle right by *angle* units.
* ```turtle.left(angle)``` or ```turtle.lt(angle)``` : Turn turtle left by *angle* units.
* ```turtle.goto(x, y)``` : Move turtle to an absolute position. If the pen is down, draw line.
* ```turtle.setposition(x, y)``` or ```turtle.setpos(x, y)``` : Move turtle to an absolute position without drawing the line. (*Notice:* this one is different with Python's official turtle module documentation, in which *setposition* is the same as *goto*).
* ```turtle.setworldcoordinates(llx, lly, urx, ury)``` : Set up user-defined coordinate system and switch to mode “world” if necessary.
* ```turtle.setx(x)``` : Set the turtle’s first coordinate to x, leave second coordinate unchanged.
* ```turtle.sety(y)``` : Set the turtle’s second coordinate to y, leave first coordinate unchanged.
* ```turtle.setheading(dir)``` or ```turtle.seth(dir)``` : Set the orientation of the turtle to *dir*. 0 is east, 90 is north, 180 is west, 270 is south, etc.
* ```turtle.home()``` : Move turtle to the origin – coordinates (0,0) – and set its heading to its start-orientation.
* ```turtle.circle(radius, extent=None)``` : Draw a circle with given radius. The center is radius units left of the turtle; extent – an angle – determines which part of the circle is drawn. If extent is not given, draw the entire circle.
* ```turtle.dot(size, color=None)``` : Draw a circular dot with diameter size, using color. If size is not given, the maximum of pensize+4 and 2*pensize is used.
* ```turtle.stamp()``` : Stamp a copy of the turtle shape onto the canvas at the current turtle position.
* ```turtle.speed(number=None)``` : Set the turtle’s speed to an integer value in the range 0..10. If no argument is given, return current speed. If speed number is set to 0 or less than 0 or greater than 10, speed will be set to 0, which is fastest and no animation takes place. 1 is slowest, 3 is slow, 6 is normal, 10 is fast. By default, its speed is 6.


### Appearance

* ```turtle.shape(name)``` : Set turtle shape to shape with given name or, if name is not given, return name of current shape. Shape's name could be one of followings: "arrow", "turtle", "circle", "square", "triangle", "classic".

### Tell Turtle's State
* ```turtle.position()``` or ```turtle.pos()``` : Return the turtle’s current location (x, y)
* ```turtle.towards(x, y)``` : Return the angle between the line from turtle position to position specified by (x, y), the vector or the other turtle.
* ```turtle.xcor()``` : Return the turtle’s x coordinate.
* ```turtle.ycor()``` : Return the turtle’s y coordinate.
* ```turtle.heading()``` : Return the turtle’s current heading.
* ```turtle.distance(x, y)``` : Return the distance from the turtle to (x, y)

### Pen control
* ```turtle.pendown()``` or ```turtle.pd()``` or ```turtle.down()``` : Pull the pen down – drawing when moving.
* ```turtle.penup()``` or ```turtle.pu()``` or ```turtle.up()``` : Pull the pen up – no drawing when moving.
* ```turtle.pensize(number)``` or ```turtle.width(number)``` : Set the line thickness to width or return it.
* ```turtle.isdown()``` : Return True if pen is down, False if it’s up.

### Color control
* ```turtle.pencolor(*args)``` : Return or set the pencolor. *pencolor()* returns current pen color, *pencolor(colorstring)*, e.g. *pencolor("red")*, *pencolor("#FF9900")* or *pencolor(r, g, b)* will set pencolor to a RGB color.
* ```turtle.fillcolor(*args)``` : Return or set the fillcolor. *fillcolor()* returns current fill color. *fillcolor(colorstring)* or *fillcolor(r, g, b)* set fillcolor to a RGB color.
* ```turtle.color(*args)``` : Return or set pencolor and fillcolor. *color()* returns the current pencolor and the current fillcolor, *color(colorstring)* or *color(r, g, b)* set pencolor and fillcolor the a RGB color.

### Filling
* ```turtle.fill(flag)``` : Call *fill(True)* before drawing the shape you want to fill, and *fill(False)* when done.
* ```turtle.begin_fill()``` : Call just before drawing a shape to be filled. Equivalent to *fill(True)*.
* ```turtle.end_fill()``` : Fill the shape drawn after the last call to begin_fill(). Equivalent to *fill(False)*.

### Visibility
* ```turtle.showturtle()``` or ```turtle.st()``` : Make the turtle visible.
* ```turtle.hideturtle()``` or ```turtle.ht()``` : Make the turtle invisible.
* ```turtle.isvisible()``` : Return True if the Turtle is shown, False if it’s hidden.

### Animation control
* ```turtle.delay(delay=None)``` : Set or return the drawing delay in milliseconds.
* ```turtle.tracer(n=None, delay=None)``` : Turn turtle animation on/off and set delay for update drawings. If n is given, only each n-th regular screen update is really performed.

### Reset
* ```turtle.reset()``` : Delete the turtle’s drawings from the screen, re-center the turtle and set variables to the default values.
* ```turtle.clear()``` : Delete the turtle’s drawings from the screen. Do not move turtle. State and position of the turtle as well as drawings of other turtles are not affected.

### Examples

* Draw line and circle

```python
from turtle import Turtle
nick = Turtle()

# move forward 100 steps
nick.forward(100)

# draw a circle with radius 40
nick.circle(40)

# change pencolor
nick.pencolor("red")

# draw a semi-circle
nick.circle(40, 180)
```

* Draw square

```python
from turtle import Turtle
nick = Turtle()

nick.forward(100)
nick.right(90)
nick.forward(100)
nick.right(90)
nick.forward(100)
nick.right(90)
nick.forward(100)
nick.right(90)
```

* Draw square with loop

```python
from turtle import Turtle
nick = Turtle()

for counter in range(4):
    nick.forward(100)
    nick.right(90)
```

* Fill square with color

```python
from turtle import Turtle
nick = Turtle()

# draw a square fill with red color
nick.color("red")

nick.begin_fill()

for counter in range(4):
    nick.forward(100)
    nick.right(90)

nick.end_fill()
```


### Reference

* [turtle library - docs.python.org](https://docs.python.org/2/library/turtle.html)
