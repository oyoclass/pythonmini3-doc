## String

You can define a string using two single-quote or two double-quote, or two triple-quote, for example `s = "hello"`, once you have a string, below are listed the string methods you can apply to.

### Functions

* `str.capitalize()`
* `str.center(width[, fillchar])`
* `str.count(sub[, start[, end]])`
* `str.endswith(suffix)`
* `str.expandtabs([tabsize])`
* `str.find(sub[, start[, end]])`
* `str.format(*args, **kwargs)`
* `str.index(sub[, start[, end]])`
* `str.isalnum()`
* `str.isalpha()`
* `str.isdigit()`
* `str.islower()`
* `str.isnumeric()`
* `str.isspace()`
* `str.istitle()`
* `str.isupper()`
* `str.join(iterable)`
* `str.ljust(width[, fillchar])`
* `str.lower()`
* `str.lstrip([chars])`
* `str.partition(seq)`
* `str.replace(old, new[, count])`
* `str.rfind(sub[, start[, end]])`
* `str.rindex(sub[, start[, end]])`
* `str.rjust(width[, fillchar])`
* `str.rpartition(seq)`
* `str.rstrip([chars])`
* `str.split([sep[, maxsplit]])`
* `str.splitlines([keepends])`
* `str.startswith(prefix[, start[, end]])`
* `str.strip([chars])`
* `str.swapcase()`
* `str.title()`
* `str.upper()`
* `str.zfill(width)`

For how to use above functions, check [String Methods on Python official documentation](https://docs.python.org/2/library/stdtypes.html#string-methods).

### Example

```python
a = "hello world"
print a.capitalize()        # Hello world
print a.upper()             # HELLO WORLD
print a.find("world")       # 6
print a.split()             # ['hello', 'world']
print a.isalnum()           # False

b = "hello {0} {1}"
print b.format("Albert", "Einstein")    # hello Albert Einstein
```

### Reference

* [String methods - docs.python.org](https://docs.python.org/2/library/stdtypes.html#string-methods)
