## What's Python?

Quote from [Python official website](https://www.python.org/):

> Python is an easy to learn, powerful programming language. It has efficient high-level data structures and a simple but effective approach to object-oriented programming. Python’s elegant syntax and dynamic typing, together with its interpreted nature, make it an ideal language for scripting and rapid application development in many areas on most platforms.


## About PythonMini

PythonMini is an online python interpreter to help you write python in browser, without installing it to your computer. It implements a subset of Python 2, plus extra libraries:

* [processing](/processing/setup) : Graphical library
* [webaudio](/webaudio/webaudio) : Audio library
* [gesture](/gesture/gesture) : Gesture detecting library
* [impress](/impress/impress): Slides/Presentation library
* [firebase](/firebase/setup): Firebase library, can be used as database


## Quick Start

Copy following example code to PythonMini editor then click "Run":

* Say hello

```python
print "hello"
```

* Doing math

```python
print 123 * 456     # calculate 123 times 456
print 180 / 12      # calculate 180 divided by 12
```

* Ask a question

```python
answer = raw_input("What's your name?")
print "hello", answer
```

* Draw a circle

```python
from turtle import Turtle
t = Turtle()
t.circle(40)    # a circle with radius 40
```

* Make a drawing-board

```python
from processing import *

def setup():
    size(500, 400)
    background(255, 255, 255)

def draw():
    if mouse.pressed:
        line(mouse.x, mouse.y, mouse.px, mouse.py)


run()
```

* Draw a 3D rotating box

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

There are a lot more you can do with PythonMini, for more information and examples, check the documentation on the left.

## Beyond PythonMini

PythonMini is meant as an introduction to the Python programming language. Everything you see in this documentation represents the full capability of the PythonMini editor. It is designed to allow you to run python in the browser, making storage and sharing of your work easier. Much more is possible with python than can be done with Python Mini alone. Examples include accessing local data, interacting with the operating system, or installing and using third-party libraries.

To access the full capabilities of Python, download and install python onto your machine. Also included below are the links to the official python website and its documentation.

 * [Python.org](https://www.python.org)
 * [Download Python](https://www.python.org/downloads/)
 * [Python Official Documentation](https://www.python.org/doc/)


## Feedback

If you find any error about this PythonMini documentation, please help us improve it, mail us at <a href="mailto:feedback@oyoclass.com">feedback@oyoclass.com</a>


## Credits

* [Skulpt](http://skulpt.org/)
* [Python Official Documentation](https://docs.python.org/2/)
* [Processingjs](http://processingjs.org/reference/) & [Processing.py](http://py.processing.org/reference/)
* [Gesture.js](https://github.com/bofeng/gest.js)
* [Impress.js](https://github.com/impress/impress.js/)
* [Firebase](https://firebase.google.com)
