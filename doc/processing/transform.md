## Transform

* [applyMatrix()](http://processing.org/reference/applyMatrix_.html)
* [popMatrix()](http://processing.org/reference/popMatrix_.html)
* [pushMatrix()](http://processing.org/reference/pushMatrix_.html)
* [resetMatrix()](http://processing.org/reference/resetMatrix_.html)
* [rotate()](http://processing.org/reference/rotate_.html)
* [rotateX()](http://processing.org/reference/rotateX_.html)
* [rotateY()](http://processing.org/reference/rotateY_.html)
* [rotateZ()](http://processing.org/reference/rotateZ_.html)
* [scale()](http://processing.org/reference/scale_.html)
* [translate()](http://processing.org/reference/translate_.html)

### Example

```python
from processing import *
import math

rotate = PI/6
def setup():
    size(400, 400, P3D)

def draw():
    global rotate
    background(180)
    noFill()
    translate(150, 150, 0)
    rotate += 0.01
    if rotate >= TWO_PI:
        rotate = 0
    rotateY(rotate)
    stroke(153)
    box(35)
    # Set rotation angles
    ct = math.cos(PI/9.0)
    st = math.sin(PI/9.0)          
    # Matrix for rotation around the Y axis
    applyMatrix( ct,  0.0,  st,  0.0,
                 0.0, 1.0, 0.0,  0.0,
                 -st, 0.0,  ct,  0.0,
                 0.0, 0.0, 0.0,  1.0)
    stroke(255)
    box(50)

run()
```

### Reference

* [Processing.org](http://processing.org/reference/)
* [Processing applyMatrix](http://processing.org/reference/applyMatrix_.html)
