## string - Common string operations

The string module contains a number of useful constants and functions.

### Constants

* `string.ascii_letters` : The concatenation of the ascii_lowercase and ascii_uppercase constants described below.
* `string.ascii_lowercase` : The lowercase letters *abcdefghijklmnopqrstuvwxyz*. This value is not locale-dependent and will not change.
* `string.ascii_uppercase` : The uppercase letters *ABCDEFGHIJKLMNOPQRSTUVWXYZ*. This value is not locale-dependent and will not change.
* `string.digits` : The string *0123456789*.
* `string.hexdigits` : The string *0123456789abcdefABCDEF*.
* `string.letters` : The concatenation of the strings lowercase and uppercase described below.
* `string.lowercase` : A string containing all the characters that are considered lowercase letters, *abcdefghijklmnopqrstuvwxyz*.
* `string.octdigits` : The string *01234567*.
* `string.punctuation` : String of ASCII characters which are considered punctuation characters.
* `string.printable` : String of characters which are considered printable. This is a combination of digits, letters, punctuation, and whitespace.
* `string.uppercase` : A string containing all the characters that are considered uppercase letters, *ABCDEFGHIJKLMNOPQRSTUVWXYZ*.
* `string.whitespace` : A string containing all characters that are considered whitespace.

### Functions

* `string.capitalize(word)`: Return a copy of word with only its first character capitalized.
* `string.capwords(s[, sep])`: Split the argument into words using str.split(), capitalize each word using str.capitalize(), and join the capitalized words using str.join().  
* `string.join(words[, sep])`: Concatenate a list or tuple of words with intervening occurrences of sep.
* `string.split(s[, sep[, maxsplit]])`: Return a list of the words of the string s. If the optional second argument sep is absent or None, the words are separated by arbitrary strings of whitespace characters (space, tab, newline, return, formfeed). If the second argument sep is present and not None, it specifies a string to be used as the word separator.


### Example

```python
import string


print string.ascii_letters
# abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
print string.ascii_lowercase
# abcdefghijklmnopqrstuvwxyz
print string.punctuation
# !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~

s = "hello world"
print string.capwords(s)
# Hello World
print string.capitalize(s)
# Hello world

words = ["i", "love", "pizza"]
print string.join(words, "*")
# i*love*pizza
```


### Reference

* [string module, docs.python.org](https://docs.python.org/2/library/string.html)
