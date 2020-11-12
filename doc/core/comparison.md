## Comparison

Comparison operations are supported by all objects. They all have the same priority (which is higher than that of the Boolean operations).

### Operations

* `<` : strictly less than
* `<=` : less than or equal
* `>` : strictly greater than
* `>=` : greater than or equal
* `==` : equal
* `!=` : not equal
* `is` : object identity
* `is not` : negated object identity

### Example

```python
print 2 != 3            # True
print 5 >= 4            # True
print 2 is 2            # True
print 300 is 300        # True

num = 350
print num is not 350    # False
```

### Reference

* [Comparisons - docs.python.org](https://docs.python.org/2/library/stdtypes.html#comparisons)
