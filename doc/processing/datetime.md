## Date & Time

* [day()](http://processing.org/reference/day_.html)
* [hour()](http://processing.org/reference/hour_.html)
* [millis()](http://processing.org/reference/millis_.html)
* [minute()](http://processing.org/reference/minute_.html)
* [month()](http://processing.org/reference/month_.html)
* [second()](http://processing.org/reference/second_.html)
* [year()](http://processing.org/reference/year_.html)


### Example

```python
from processing import *

def setup():
    size(500, 400)

def draw():
    background(0)
    s = "Current time: %02d:%02d:%02d" % (hour(), minute(), second())
    textSize(35)
    fill(0, 255, 0)
    text(s, 80, 200)


run()
```

### Reference

* [Processing.org](http://processing.org/reference/)
