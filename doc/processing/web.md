## Web

* `link(url[, target=None])` : open a web page in *target* window, if *target* is missing, web page will be opened in current window; if *target* equals `_new`, web page will be opened in a new window/tab.

### Example

```python
from processing import *

def keyPressed():
    # key "o" is pressed
    # open a web page load oyoclass.com
    if keyboard.keyCode == 79:
        link("https://oyoclass.com", "_new")


run()
```

### Reference

* [Processing link](http://processing.org/reference/link_.html)
