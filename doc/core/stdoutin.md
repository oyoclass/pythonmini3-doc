## Standard output and input

### Standard output

The most common way to output something is using `print` function:

```python
print 2 * 3
print "hello"
arr = [1, 2, 3, 4]
print arr
```

Output:

```
6
hello
[1, 2, 3, 4]
```

or you can use `sys.stdout.write`:

```python
from sys import stdout
arr = [1, 2, 3, 4]
stdout.write("hello ")
stdout.write(arr)
```

Output:

```
hello 1,2,3,4
```

### Standard input

To get user input, you can use `raw_input` function:

```python
name = raw_input("What's your name?")
print "hello", name
```

What you get from `raw_input` will always be string, even it looks like a number, for example:

```python
num = raw_input("Give me a number")
print num               # 12
print num * 2           # 1212

# now convert it to number
num = int(num)
print num * 2           # 24
```

You can also read user's input by using `sys.stdin.read` or `sys.stdin.readline`:

```python
from sys import stdin

name = stdin.readline()
print name

# Only read 3 characters
name = stdin.readline(3)
print name
```
