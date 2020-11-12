## operator — Standard operators as functions

The operator module exports a set of efficient functions corresponding to the intrinsic operators of Python.

### Functions

* `operator.abs`
* `operator.add`
* `operator.and_`
* `operator.concat`
* `operator.contains`
* `operator.countOf`
* `operator.delitem`
* `operator.div`
* `operator.divmod`
* `operator.eq`
* `operator.floordiv`
* `operator.ge`
* `operator.getitem`
* `operator.gt`
* `operator.index`
* `operator.indexOf`
* `operator.inv`
* `operator.invert`
* `operator.is_`
* `operator.is_not`
* `operator.le`
* `operator.lshift`
* `operator.lt`
* `operator.mod`
* `operator.mul`
* `operator.ne`
* `operator.neg`
* `operator.not_`
* `operator.or_`
* `operator.pos`
* `operator.pow`
* `operator.rshift`
* `operator.setitem`
* `operator.sub`
* `operator.truediv`
* `operator.truth`
* `operator.xor`

For more information on how to use those functions, please check Python's official documentation at [operator module - docs.python.org](https://docs.python.org/2/library/operator.html).

### Example

```python
import operator

print operator.lt(1, 2)
# True

print operator.truth(0)
# False

print operator.truth([])
# False

print operator.truth(2)
# True

print operator.countOf("hello world", "l")
# 3
```

### Reference

* [operator module - docs.python.org](https://docs.python.org/2/library/operator.html)
