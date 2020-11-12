## Math

* [PVector](http://processing.org/reference/PVector/)

### Calculation

* [constrain()](http://processing.org/reference/constrain_.html)
* [dist()](http://processing.org/reference/dist_.html)
* [lerp()](http://processing.org/reference/lerp_.html)
* [mag()](http://processing.org/reference/mag_.html)
* [map()](http://processing.org/reference/map_.html)
* [norm()](http://processing.org/reference/norm_.html)
* [sq()](http://processing.org/reference/sq_.html)

### Trigonometry

* [degrees()](http://processing.org/reference/degrees_.html)
* [radians()](http://processing.org/reference/radians_.html)

### Random

* [noise()](http://processing.org/reference/noise_.html)
* [noiseDetail()](http://processing.org/reference/noiseDetail_.html)
* [noiseSeed()](http://processing.org/reference/noiseSeed_.html)
* [random()](http://processing.org/reference/random_.html)
* [randomSeed()](http://processing.org/reference/randomSeed_.html)

### Example

```python
from processing import *

xoff = 0.0
width = 400
height = 300

def setup():
    size(400, 400)

def draw():
    global xoff
    background(204)
    xoff = xoff + .01
    n = noise(xoff) * width
    line(n, 0, n, height)

run()
```

### Reference

* [Processing.org](http://processing.org/reference/)
* [Processing noise function](http://processing.org/reference/noise_.html)
