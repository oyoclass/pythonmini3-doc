## Functions

### Built-in functions

* `abs`
* `all`
* `any`
* `bin`
* `bool`
* `chr`
* `dict`
* `dir`
* `divmod`
* `enumerate`
* `filter`
* `float`
* `hex`
* `int`
* `isinstance`
* `issubclass`
* `len`
* `list`
* `long`
* `map`
* `max`
* `min`
* `oct`
* `ord`
* `pow`
* `print`
* `range`
* `raw_input`
* `reduce`
* `repr`
* `reversed`
* `round`
* `set`
* `slice`
* `sorted`
* `str`
* `sum`
* `tuple`
* `xrange`
* `zip`

For how to use above functions, check [built-in functions on Python official documentation](https://docs.python.org/2/library/functions.html).

#### Example

```python
print bin(3)        # 0b11
print hex(255)      # 0xff
print abs(-5)       # 5
print pow(3, 2)     # 9
print round(3.5)    # 4.0
print round(3.2)    # 3.0
print oct(8)        # 010
print ord('A')      # 65
print chr(97)       # a

a = [1,4,5,2,3]
print sorted(a)     # [1, 2, 3, 4, 5]
```

### User-defined functions

You can define your own function by using `def`.

Example:

```python
def my_add(a, b):
    c = a + b
    return c

print my_add(1, 2)  # 3
```


### Reference

* [Built-in function - docs.python.org](https://docs.python.org/2/library/functions.html)
