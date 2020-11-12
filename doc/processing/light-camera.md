## Light & Camera

### Lights

* [ambientLight()](http://processing.org/reference/ambientLight_.html)
* [directionalLight()](http://processing.org/reference/directionalLight_.html)
* [lightFalloff()](http://processing.org/reference/lightFalloff_.html)
* [lightSpecular()](http://processing.org/reference/lightSpecular_.html)
* [lights()](http://processing.org/reference/lights_.html)
* [noLights()](http://processing.org/reference/noLights_.html)
* [normal()](http://processing.org/reference/normal_.html)
* [pointLight()](http://processing.org/reference/pointLight_.html)
* [spotLight()](http://processing.org/reference/spotLight_.html) : Note - on this linked page, this function's syntax is `spotLight(v1, v2, v3, nx, ny, nz, angle, concentration)`, which SHOULD BE `spotLight(v1, v2, v3, x, y, z, nx, ny, nz, angle, concentration)`

### Camera

* [beginCamera()](http://processing.org/reference/beginCamera_.html)
* [camera()](http://processing.org/reference/camera_.html)
* [endCamera()](http://processing.org/reference/endCamera_.html)
* [frustum()](http://processing.org/reference/frustum_.html)
* [ortho()](http://processing.org/reference/ortho_.html)
* [perspective()](http://processing.org/reference/perspective_.html)
* [printCamera()](http://processing.org/reference/printCamera_.html)
* [printProjection()](http://processing.org/reference/printProjection_.html)

### Coordinates

* [modelX()](http://processing.org/reference/modelX_.html)
* [modelY()](http://processing.org/reference/modelY_.html)
* [modelZ()](http://processing.org/reference/modelZ_.html)
* [screenX()](http://processing.org/reference/screenX_.html)
* [screenY()](http://processing.org/reference/screenY_.html)
* [screenZ()](http://processing.org/reference/screenZ_.html)

### Material Properties

* [ambient()](http://processing.org/reference/ambient_.html)
* [emissive()](http://processing.org/reference/emissive_.html)
* [shininess()](http://processing.org/reference/shininess_.html)
* [specular()](http://processing.org/reference/specular_.html)

### Example

```python
from processing import *

def setup():
    size(560, 400, P3D)
    #printCamera()
    #printProjection()

def draw():
    noFill()
    beginCamera()
    camera()
    rotateX(-PI/6)
    endCamera()

    translate(50, 50, 0)
    rotateY(PI/3)
    box(45)


run()
```

### Reference

* [Processing.org](http://processing.org/reference/)
