## Image

* [PImage](http://processing.org/reference/PImage/)
* [createImage()](http://processing.org/reference/createImage_.html)

### Loading & Displaying

* [image()](http://processing.org/reference/image_.html)
* [imageMode()](http://processing.org/reference/imageMode_.html)
* [loadImage()](http://processing.org/reference/loadImage_.html)
* [requestImage()](http://processing.org/reference/requestImage_.html)

### Pixels

* [blend()](http://processing.org/reference/blend_.html)
* [copy()](http://processing.org/reference/copy_.html)
* [filter()](http://processing.org/reference/filter_.html)
* [getPixel()](http://processing.org/reference/get_.html)
* [setPixel()](http://processing.org/reference/set_.html)

### Example

```python
from processing import *

pikachu = None
ball = None

def setup():
    global pikachu, ball
    size(400, 400)
    colorMode(RGB, 100)
    # you may want to change the image url below
    pikachu = loadImage("http://www.avatars101.com/avatars/Pokemon/301BE8845F43838DE7A6B6DFEB2B963E/Pikachu.gif")
    ball = requestImage("http://vignette4.wikia.nocookie.net/pokemon/images/4/46/Timer_Ball.png")

def draw():
    background(0, 200, 200)
    image(pikachu, 100, 100)

    if ball.width != 0 and ball.width != -1:
        image(ball, 200, 50, 65, 65)    

run()
```

### Reference

* [Processing.org](http://processing.org/reference/)
