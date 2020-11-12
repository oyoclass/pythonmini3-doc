## Shape

### 2D Primitives

* [arc()](http://processing.org/reference/arc_.html)
* [ellipse()](http://processing.org/reference/ellipse_.html)
* [line()](http://processing.org/reference/line_.html)
* [point()](http://processing.org/reference/point_.html)
* [quad()](http://processing.org/reference/quad_.html)
* [rect()](http://processing.org/reference/rect_.html)
* [triangle()](http://processing.org/reference/triangle_.html)

### Curves

* [bezier()](http://processing.org/reference/bezier_.html)
* [bezierDetail()](http://processing.org/reference/bezierDetail_.html)
* [bezierPoint()](http://processing.org/reference/bezierPoint_.html)
* [bezierTangent()](http://processing.org/reference/bezierTangent_.html)
* [curve()](http://processing.org/reference/curve_.html)
* [curveDetail()](http://processing.org/reference/curveDetail_.html)
* [curvePoint()](http://processing.org/reference/curvePoint_.html)
* [curveTangent()](http://processing.org/reference/curveTangent_.html)
* [curveTightness()](http://processing.org/reference/curveTightness_.html)

### 3D Primitives

* [box()](http://processing.org/reference/box_.html)
* [sphere()](http://processing.org/reference/sphere_.html)
* [sphereDetail()](http://processing.org/reference/sphereDetail_.html)

### Attributes

* [ellipseMode()](http://processing.org/reference/ellipseMode_.html)
* [noSmooth()](http://processing.org/reference/noSmooth_.html)
* [rectMode()](http://processing.org/reference/rectMode_.html)
* [smooth()](http://processing.org/reference/smooth_.html)
* [strokeCap()](http://processing.org/reference/strokeCap_.html)
* [strokeJoin()](http://processing.org/reference/strokeJoin_.html)
* [strokeWeight()](http://processing.org/reference/strokeWeight_.html)

### Vertex

* [beginShape()](http://processing.org/reference/beginShape_.html)
* [bezierVertex()](http://processing.org/reference/bezierVertex_.html)
* [curveVertex()](http://processing.org/reference/curveVertex_.html)
* [endShape()](http://processing.org/reference/endShape_.html)
* [texture()](http://processing.org/reference/texture_.html)
* [textureMode()](http://processing.org/reference/textureMode_.html)
* [vertex()](http://processing.org/reference/vertex_.html)

### Loading & Displaying

* [loadShape()](http://processing.org/reference/loadShape_.html)
* [shape()](http://processing.org/reference/shape_.html)
* [shapeMode()](http://processing.org/reference/shapeMode_.html)

### Example

```python
from processing import *

def setup():
    size(400, 400)
    background(0, 0, 0)

def draw():
    fill(0, 0, 255)
    ellipse(56, 46, 55, 55)
    fill(255, 0, 0)
    triangle(130, 175, 158, 120, 186, 175)

run()
```


### Reference

* [Processing.org](http://processing.org/reference/)
