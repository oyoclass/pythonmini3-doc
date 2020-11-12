## List

List is used to group together values, can be written as a list of comma-separated values (items) between square brackets. Lists might contain items of different types, but usually the items all have the same type.

List's index starts from 0, and you can visit last element using index -1:

```python
a = [1, 5, 2, 3]
print a[0]          # 1
print a[1]          # 5
print a[-1]         # 3
print a[1:3]        # Get elements from index 1 to index 3 (exclusive), i.e. [5, 2]
```

Change element at a index:

```python
a = [1, 5, 2, 3]
a[1] = 7
print a             # [1, 7, 2, 3]
```

To check if one element in a list, you can use `in`:

```python
a = [1, 5, 2, 3]
print 5 in a       # True
```

Use function `len` to get length (how many elements) of a list:

```python
a = [1, 5, 2, 3]
print len(a)       # 4
```

### Functions

* `list.append(x)`
* `list.count(x)`
* `list.extend(L)`
* `list.index(x)`
* `list.insert(i, x)`
* `list.pop([i])`
* `list.remove(x)`
* `list.reverse()`
* `list.sort(cmp=None, key=None, reverse=False)`

For how to use those functions, check [lists method on Python official documentation](https://docs.python.org/2/tutorial/datastructures.html#more-on-lists)  

### Example

```python
a = [1, 5, 2, 3]
a.append(6)
print a             # [1, 5, 2, 3, 6]
print a.count(5)    # 1
a.remove(2)
print a             # [1, 5, 3, 6]
a.reverse()
print a             # [6, 3, 5, 1]
a.sort()
print a             # [1, 3, 5, 6]
```

## Tuple

Tuple is similar with list, the main difference is list is mutable and tuple is immutable. Once you defined a tuple with parentheses `()`, you can not change its element.

```python
b = (1, 5, 2, 3)
b.append(6)     # this will give an error, since b is a tuple and immutable
```

## Conversion between tuple and list

Though a tuple can not be changed, you can convert it to list, make some changes, then convert it back to tuple. You can do this with `tuple` and `list` function.

```python
b = (1, 5, 2, 3)
b = list(b)         # Convert tuple to list
b.append(6)         # Change list - append one more element
b = tuple(b)        # Convert list to tuple
print b             # (1, 5, 2, 3, 6)
```

### Reference

* [Introduction of List - docs.python.org](https://docs.python.org/2/tutorial/introduction.html#lists)
* [More on Lists - docs.python.org](https://docs.python.org/2/tutorial/datastructures.html#more-on-lists)
