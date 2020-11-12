## gesture

__gesture__ library will detect your gesture by using webcam, you can call a function when a gesture (`left`, `right`, `up` or `down`) is detected.

### Functions

* `gesture.start()`: Start webcam and detecting gesture
* `gesture.stop()`: Stop webcam
* `gesture.on(dir, func)`: Set callback function for _dir_, when _dir_ is detected, this function will be called. _dir_ 's value could be `left`, `right`, `up` and `down`. If you didn't use this `on` function to set callback function, by default, if `left` is detected, function `gestureOnLeft` will be called (if defined); if `right` is detected, function `gestureOnRight` will be called (if defined); if `up` is detected, function `gestureOnUp` will be called (if defined); if `down` is detected, function `gestureOnDown` will be called (if defined).


### Example
```python
import gesture

def on_left():
    print "moving left"

def on_right():
    print "moving right"

def gestureOnUp():
    # this is the default callback function when `up` is detected
    # you can use gesture.on('up', other_func) to set this callback
    # function to be other_func
    print "moving up"

def gestureOnDown():
    print "moving down"


# set callback function for left and right gesture
gesture.on("left", on_left)
gesture.on("right", on_right)

# start webcam and detecting
gesture.start()
```
