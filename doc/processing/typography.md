## Typography

* [PFont](http://processing.org/reference/PFont/)

### Loading & Displaying

* [createFont()](http://processing.org/reference/createFont_.html)
* [text()](http://processing.org/reference/text_.html)
* [textFont()](http://processing.org/reference/textFont_.html)

### Attributes

* [textAlign()](http://processing.org/reference/textAlign_.html)
* [textLeading()](http://processing.org/reference/textLeading_.html)
* [textMode()](http://processing.org/reference/textMode_.html)
* [textSize()](http://processing.org/reference/textSize_.html)
* [textWidth()](http://processing.org/reference/textWidth_.html)

### Metrics

* [textAscent()](http://processing.org/reference/textAscent_.html)
* [textDescent()](http://processing.org/reference/textDescent_.html)


### Example

```python
from processing import *

myFont = None

def setup():
    global myFont
    size(400, 400)
    background(0)
    myFont = createFont("Georgia", 32);

def draw():
    fill(255, 255, 255)
    textFont(myFont)
    textAlign(LEFT)
    text("Hello World", 100, 200)

    fill(255, 0, 0)
    textSize(30)
    text("Start Game", 100, 300)


run()
```


### Reference

* [Processing.org](http://processing.org/reference/)
