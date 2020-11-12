## Set

A set is an unordered collection with no duplicate elements. Basic uses include membership testing and eliminating duplicate entries. Set objects also support mathematical operations like union, intersection, difference, and symmetric difference.

You can use `set()` to get a set, here is a quick example:

```python
basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
fruit = set(basket)
print fruit     # set(['apple', 'orange', 'pear', 'banana'])
```

### Functions

* `set.add(elem)` : Add element elem to the set.
* `set.copy()` : Return a new set with a shallow copy of s.
* `set.difference(other)` : Return a new set with elements in the set that are not in the others.
* `set.difference_update(other)` : Update the set, removing elements found in others.
* `set.discard(elem)` : Remove element elem from the set if it is present.
* `set.intersection(other)` : Return a new set with elements common to the set and all others.
* `set.intersection_update(other)`: Update the set, keeping only elements found in it and all others.
* `set.isdisjoint(other)` : Return True if the set has no elements in common with other. Sets are disjoint if and only if their intersection is the empty set.
* `set.issubset(other)` : Test whether every element in the set is in other.
* `set.issuperset(other)` : Test whether every element in other is in the set.
* `set.pop()` : Remove and return an arbitrary element from the set.
* `set.remove(elem)` : Remove element elem from the set.  
* `set.symmetric_difference(other)` : Return a new set with elements in either the set or other but not both.
* `set.symmetric_difference_update(other)` : Update the set, keeping only elements found in either set, but not in both.
* `set.union(other)` : Return a new set with elements from the set and all others.
* `set.update(other)` : Update the set, adding elements from all others.

*\*Notice:* The official Python support using mathematical operator with sets, for example, if we have two sets a and b, `a - b` is the same as `a.difference(b)`, however, PythonMini doesn't support those operators at this moment.

### Example

```python
a = set()
a.add(1)
a.add(2)
a.add(1)

print a                 # set([1, 2])
print len(a)            # 2

b = set([2,2,3])
print b                 # set([2, 3])

print a.intersection(b) # set([2])
print a.union(b)        # set([1, 2, 3])

c = set([3])
print b.issuperset(c)   # True
```

### Reference

* [Sets - docs.python.org](https://docs.python.org/2/tutorial/datastructures.html#sets)
* [Set - docs.python.org](https://docs.python.org/2/library/stdtypes.html#set)
