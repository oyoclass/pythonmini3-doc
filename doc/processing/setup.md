## Setup processing

### A typical running structure

Here is a typical way to use Processing library:

```python
from processing import *

healthPoint = 3

def setup():
    size(500, 400)

def draw():
    background(0, 0, 0)
    # do other drawings and logic

    # here if you want to end the drawing, call exitp()
    if healthPoint == 0:
        exitp()


run()
```

Notice the `run()` function at bottom, it will call `setup()` once, and will iteratively call `draw()` function again and again and again, until you call `exitp()` function.

In `setup()` function, we setup the canvas size for drawing, which is 500px in width and 400px in height. In the `draw()` function, we make the canvas's background as black (RGB color (0, 0, 0) is black).

### Get input from user

If you want to make a game with Processing, one important part will be detecting if player pressed keyboard or clicked mouse, which is:

```python

from processing import *

healthPoint = 3

def setup():
    size(500, 400)

def draw():
    background(0, 0, 0)
    # do other drawings and logic
    # here if you want to end the drawing, call exitp()
    if healthPoint == 0:
        exitp()

def keyPressed():
    if keyboard.keyCode == 37:
        # left arrow key pressed
        # do something ...
    elif keyboard.keyCode == 39:
        # right arrow key
        # do something ...

def mousePressed():
    print "Mouse pressed at", mouse.x, mouse.y


run()
```

### 3D drawing

Processing also support 3D drawing, to use 3D, you need to setup canvas to "3D" model by passing P3D as the 3rd parameter in `size` function:

```python
from processing import *

rotating = 0.01

def setup():
    size(400, 400, P3D)

def draw():
    global rotating
    background(0, 0, 0)
    translate(200, 100, 0)
    rotateY(rotating)
    rotating += 0.01
    if rotating >= PI:
        rotating = 0.01
    fill(255, 0, 0)
    box(40)

run()
```

To check more functions about Processing library, check all functions under `Processing Graphic` on the left.
