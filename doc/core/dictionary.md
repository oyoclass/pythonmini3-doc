## Dictionary

Dictionaries are sometimes found in other languages as “associative memories” or “associative arrays”. Unlike sequences, which are indexed by a range of numbers, dictionaries are indexed by keys, which can be any immutable type.

It is best to think of a dictionary as an unordered set of key: value pairs, with the requirement that the keys are unique (within one dictionary). A pair of braces creates an empty dictionary: {}. Placing a comma-separated list of key:value pairs within the braces adds initial key:value pairs to the dictionary.

### Functions

* `dict.clear()` : Remove all items from the dictionary.
* `dict.get(key[, default])` : Return the value for key if key is in the dictionary, else default. If default is not given, it defaults to None, so that this method never raises a KeyError.
* `dict.has_key(key)` : Test for the presence of key in the dictionary.
* `dict.items()` : Return a copy of the dictionary’s list of (key, value) pairs.
* `dict.keys()` : Return a copy of the dictionary’s list of keys.
* `dict.pop(key[, default])` : If key is in the dictionary, remove it and return its value, else return default. If default is not given and key is not in the dictionary, a KeyError is raised.
* `dict.setdefault(key[, default])` : If key is in the dictionary, return its value. If not, insert key with a value of default and return default. default defaults to None.
* `dict.update([other])` : Update the dictionary with the key/value pairs from other, overwriting existing keys. Return None.
* `dict.values()` : Return a copy of the dictionary’s list of values.

### Example

```python
a = {"name": "Bo", "age": 20}
print a.has_key("name")             # True
print a.keys()                      # ['name', 'age']
print a.values()                    # ['Bo', 20]
a.setdefault("gender", "m")         
print a                             # {'name': 'Bo', 'age': 20, 'gender': 'm'}
a.update({"city": "Stony Brook"})   
print a                 # {'name': 'Bo', 'age': 20, 'gender': 'm', 'city': 'Stony Brook'}
```

### Reference

* [Data structure: dictionary - docs.python.org](https://docs.python.org/2/tutorial/datastructures.html#dictionaries)
* [Mapping Type - Dict](https://docs.python.org/2/library/stdtypes.html#mapping-types-dict)
