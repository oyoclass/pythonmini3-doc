# Input

You can detect if user pressed keyboard or mouse.

## Keyboard

### Property

* `keyboard.key` : the actual key, if you pressed `e`, this will be `e`
* `keyboard.keyCode` : the key's code, if you pressed `e`, this will be `69`
* `keyboard.keyPressed` : `True` if any key is pressed and `False` if no keys are pressed

### Constants

* `BACKSPACE` : backspace key code
* `TAB` : tab key code
* `ENTER` : enter key code
* `RETURN` : return key code
* `ESC` : esc key code
* `DELETE` : delete key code
* `SHIFT` : shift key code
* `CONTROL` : control key code
* `ALT` : alt key code
* `CAPSLK` : caps lock key code
* `PGUP` : page up key code
* `PGDN` : page down key code
* `END` : end key code
* `HOME` : home key code
* `LEFT` : left arrow key code
* `UP` : up arrow key code
* `RIGHT` : right arrow key code
* `DOWN` : down arrow key code
* `F1`, `F2` ... `F12` : F1 ~ F12 key code
* `NUMLK` : number lock key code
* `INSERT` : insert key code

### Events

* `keyPressed()` : If any key is pressed, this function will be called
* `keyReleased()` : If any key is released, this function will be called
* `keyTyped()` : If any key is typed, this function will be called

### Example

Move a rectangle when left or right arrow key is pressed.

```python
from processing import *

rectX = 0

def setup():
    size(500, 400)

def draw():
    background(0, 0, 0)
    rect(rectX, 100, 50, 10)

def keyPressed():
    global rectX
    if keyboard.keyCode == LEFT:
        rectX -= 5
    elif keyboard.keyCode == RIGHT:
        rectX += 5

run()
```

## Mouse

### Property

* `mouse.x` : current horizontal coordinate of the mouse
* `mouse.y` : current vertical coordinate of the mouse
* `mouse.px` : the previous horizontal coordinate of the mouse
* `mouse.py` : the previous vertical coordinate of the mouse
* `mouse.pressed` : if mouse is pressed
* `mouse.button` : which mouse button is pressed, left mouse button is 37, right mouse button is 39

### Functions

* `mouseClicked()` : will be called when click clicked
* `mouseDragged()` : will be called when drag mouse
* `mousePressed()` : will be called when press mouse
* `mouseMoved()` : will be called when move mouse
* `mouseReleased()` : will be called when release mouse
* `mouseOut()` : will be called when mouse pointer leaves canvas
* `mouseOver()` :  will be called when the mouse pointer moves over canvas

### Example

```python
from processing import *

def setup():
    size(500, 400)

def draw():
    background(0)

def mousePressed():
    print "pressed at:", mouse.x, mouse.y
    # left button is 37, right button is 39
    print "mouse button:", mouse.button

def mouseMoved():
    info = "Mouse moved at (%s, %s)" % (mouse.x, mouse.y)
    text(info, mouse.x, mouse.y)

def mouseReleased():
    text("Mouse released", 10, 10)


run()
```

### Reference

* [Processing.org](http://processing.org/reference)
