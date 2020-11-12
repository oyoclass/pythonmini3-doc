##  collections — High-performance container datatypes

This module implements the following specialized container datatypes:

### Objects

* `namedtuple`: factory function for creating tuple subclasses with named fields
* `Counter`: dict subclass for counting hashable objects
* `OrderedDict`: dict subclass that remembers the order entries were added
* `defaultdict`: dict subclass that calls a factory function to supply missing values

For more information and how to use those objects, check [Python Collections Module documentation](https://docs.python.org/2/library/collections.html).

### Example

```python
import collections

c = collections.Counter('gallahad')
print c["a"]
# 3
print c.most_common(1)
# [('a', 3)]

Point = collections.namedtuple('Point', ['x', 'y'])
p = Point(1,2)
print p.x
# 1
print p.y
# 2
```
