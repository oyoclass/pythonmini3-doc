## re — Regular expression operations

This module provides regular expression matching operations.

### Constants

* `re.I` or `re.IGNORECASE` : Perform case-insensitive matching
* `re.M` or `re.MULTILINE` : When specified, the pattern character '^' matches at the beginning of the string and at the beginning of each line (immediately following each newline); and the pattern character '$' matches at the end of the string and at the end of each line (immediately preceding each newline).

### Functions

* `re.findall`
* `re.match`
* `re.search`
* `re.split`

### Class

* `re.MatchObject` : match object support methods `group` and `groups`

For more information on how to use above attributes and methods, check Python's official documentation at [re module - docs.python.org](https://docs.python.org/2/library/re.html)

### Example

```python
import re

m = re.match(r"(\w+) (\w+)", "Isaac Newton, physicist")

print m.group(0)
# Isaac Newton

print m.group(1)
# Isaac

print m.group(2)
# Newton
```

### Reference

* [re module - docs.python.org](https://docs.python.org/2/library/re.html)
