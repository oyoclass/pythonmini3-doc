## json

JSON (JavaScript Object Notation), specified by RFC 7159 (which obsoletes RFC 4627) and by ECMA-404, is a lightweight data interchange format inspired by JavaScript object literal syntax.

### Functions

* ```json.dumps(object)```: Serialize obj to a JSON formatted string
* ```json.loads(string)```: Deserialize a string to a Python object

### Example

```python
import json

student = {
    "name": "Nick",
    "grade": 5
}

# s is a string
s = json.dumps(student)
print s

# o is an object
o = json.loads(s)
print o["name"]
```
