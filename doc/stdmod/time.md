## time — Time access
<!-- doc for this module is completed -->

This module provides time-related functions.

### Attribute

* `time.altzone` : The offset of the local DST timezone, in seconds west of UTC.
* `time.daylight` : Nonzero if a DST timezone is defined.
* `time.timezone` : The offset of the local (non-DST) timezone, in seconds west of UTC (negative in most of Western Europe, positive in the US, zero in the UK).
* `time.tzname` : A tuple of two strings: the first is the name of the local non-DST timezone, the second is the name of the local DST timezone.

### Functions

* `time.asctime([t])` : Convert a tuple or struct_time representing a time as returned by gmtime() or localtime() to a 24-character string of the following form: 'Sun Jun 20 23:21:05 1993'. If t is not provided, the current time as returned by localtime() is used.
* `time.clock()` : Return the current processor time as a floating point number expressed in seconds.
* `time.ctime([secs])` : Convert a time expressed in seconds since the epoch to a string representing local time. If secs is not provided or None, the current time as returned by time() is used.
* `time.gmtime([secs])` : Convert a time expressed in seconds since the epoch to a struct_time in UTC in which the dst flag is always zero. If secs is not provided or None, the current time as returned by time() is used.
* `time.localtime([secs])` : Like gmtime() but converts to local time. If secs is not provided or None, the current time as returned by time() is used.
* `time.mktime(t)` : This is the inverse function of localtime(). Its argument is the struct_time or full 9-tuple.
* `time.sleep(secs)` : Suspend execution of the current thread for the given number of seconds.
* `time.time()`: Return the time in seconds since the epoch as a floating point number.

### Class

* `time.struct_time`: The type of the time value sequence returned by gmtime(), localtime().

For more information, check [time module on Python official documentation](https://docs.python.org/2/library/time.html).
### Example

```python
import time

print time.timezone
print time.altzone
print time.ctime()
print time.clock()
print time.localtime()
print time.gmtime()
print time.tzname

# print out time every 1 second
for i in range(10):
    print time.asctime()
    time.sleep(1)
```

### Reference

* [time module - docs.python.org](https://docs.python.org/2/library/time.html)
