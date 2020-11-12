## Firebase

The firebase library can be used to add real-time database functionality in your Python applications. This library depends on creating a Firebase app at [Google Firebase](https://console.firebase.google.com/). The Firebase database allows you to store, retrieve, and update data.

### Firebase Functions
* `firebase.loadFirebase(api_key, auth_domain, database_url)` : Creates a firebase database connection to your existing Firebase app. It returns the _Firebase_ object that you will use for all the database functionality (the class is explained below). Pass the API key and the app name twice as strings. You will continue to use this `db` object to work with the database.
```python
db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')
```

### Firebase Class

#### Save Data

* `db.set(url, data)`: Write or replace data to a URL path, such as `users/star_count`. For example, `db.set('users/star_count', 10)`.
* `db.push(url, data)`: Writes data to URL path at a new unique child. For example, `db.push('users/', {'username': 'Bob'})`.
* `db.remove(url)`: Removes data at the given URL path. For example, `db.remove('users/')`.
* `db.update(url, data)`: Writes or replaces data to the URL path. For example, `db.update('users/star_count', 15)`.

#### Retrieve Data

* `db.child_added(url, fn, once=False)`: Retrieve lists of items and listen for additions to a list of items to be passed to the callback function. By default, child_added continues to listen for new events, but can retrieve once by passing `True` to the third parameter once.  For example, `db.child_added('users/', printUsers, True)`.
* `db.child_removed(url, fn, once=False)`: Listen for items being removed from a list to be passed to the callback function. By default, child_removed continues to listen for new events, but can retrieve once by passing `True` to the third parameter once. For example, `db.child_removed('users/', printRemovedUsers, True)`.
* `db.child_updated(url, fn, once=False)`: Listen for changes to the items in a list to be passed to the callback function. By default, child_updated continues to listen for new events, but can retrieve once by passing `True` to the third parameter once. For example, `db.child_updated('users/', printUpdatedUsers, True)`.
* `db.value(url, fn, once=False)`: Read and listen for changes to the entire contents of a URL path to be passed to the callback function. By default, value continues to listen for new events, but can retrieve once by passing `True` to the third parameter once. When once is set to `True` `db.value` can be used with `db.set` to set and read data at a URL path. For example, `db.value('users/', printValues, True)`.

### Setup

Head to [Firebase setup](./setup.md).

### Structured Data

Head to [Structured Data](./structured_data.md).


### Examples

### Saving/Updating/Removing Data Example

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
"""
Firebase import:
Declare and initialize database variable(db) with the loadFirebase() method.

firebase.loadFirebase(apiKey, auth_domain, database_url)
@param apiKey: string
@param auth_domain: string
@param database_url: string
"""
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

"""
db.set(url, data)
@param url: String
@param data: Python data types and data structures
"""
# data can be numbers
db.set('users/star_count', 10)
# data can be strings
db.set('users/to_be_deleted', '10')
# data can be floats
db.set('users/pi', 3.15)
# data can be Python dictionaries
db.set('users/spaceship', {
    "userid": "uid001",
    "health": 95,
    "damage": 8,
    "coordinates": [25, 99]
})
# data can be Python lists
db.set('users/my_array', [0, 1, 2, 3, 4, 5])

"""
db.push(url, data)
@param url: String
@param data: Python data types and data structures
"""
# data can be integers/floats/strings
db.push('math/', 3.14)
# data can be Python dictionaries
db.push('users/', {'username': 'Mary'})
db.push('users/', {'username': 'Joe'})
db.push('users/', {
                    'username': 'Bob',
                    'email': 'example@email.com',
                    'age': 22
                    })

"""
db.remove(url)
@param url: String
"""
# remove the data at the URL path 'users/to_be_deleted'
db.remove('users/to_be_deleted')

"""
db.update(url, data)
@param url: String
@param data: Python data types and data structures
"""
# the data at the URL path 'users/star_count' is now the number 3.14
db.update('users/pi', 3.14)

```

### Retrieving Data

To retrieve data through Firebase you must use a callback function.
Callback functions will all receive two parameters.
A URL string which is being listened on and a data dictionary.

```python

def printAddedUser(url, data):
    # URL path being listened on
    print url
    # relative location of the data from the passed URL path
    print data['key']
    # data located at the URL path and key
    print data['value']

```

The data dictionary will have two attributes the 'key' for locating the
data on the URL path and the 'value' of that data.

```python
ret = {
    # relative location of the data from the passed URL path
    "key": "-KOtqG2aj5ln1bJ2qkav",
    "value": {
        "username": "Bob",
        "health": 85,
        "coordinates": [45, 110]
    }
}
```

## Retrieving Data Examples

### On Event Callbacks
The following retrieval examples have the once parameter equal to `False`.
As new events occur on the given URL path the callback function will run.

#### Child Added

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

# This callback function will print the username from the return data dictionary.
def printAddedUser(url, data):
    # When using db.push a unique key will be generated at the passed URL
    # for the data.
    key = data['key']
    # This key will be used to update the data at that URL path and key.
    # This change will emit a child_updated event see Child Updated.
    updateUser(key)
    print data['value']['username'], " has joined."

# the child_added method will retrieve every child at the URL path 'users/'
db.child_added('users/', printAddedUser)

new_user = {
    'username': 'Bob',
    'profession': 'builder'
}

modify_user = {
    'username': 'Bob',
    'profession': 'plumber'
}

# The value at the path 'users/' + key will be modify_user, not new_user.
def updateUser(key):
    db.update('users/' + key, modify_user)

"""
The push method will add a new user to the database.
This will trigger a child_added event at 'users/' and fire the printAddedUser method.
"""
db.push('users/', new_user)

```

#### Child Removed

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

# This callback function will print the username from the return data dictionary.
def printRemovedUser(url, data):
    print data['value']['username'], " has left."

# The child_removed method will fire when a child at the URL path 'users/'
# is removed.
db.child_removed('users/', printRemovedUser)

"""
The remove method will remove the object at 'users/bob002' from the database.
This will trigger a child_removed event at 'users/' and fire the printRemovedUser method.
To see the effect you will need to have a value at the path 'users/bob002'.
"""
db.remove('users/bob002')

```

#### Child Updated

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

# This callback function will print the username from the return data dictionary.
def printUpdatedUser(url, data):
    print data['value']['username'], " has updated."

# The child_updated method will fire when a child at the URL path 'users/'
# is updated.
db.child_updated('users/', printUpdatedUser)

updated_user = {
    'username': 'Bob',
    'profession': 'plumber'
}

"""
The update method will update the object at 'users/bob002' from the database.
This will trigger a child_updated event at 'users/' and fire the printUpdatedUser method.
To see the effect you will need to have a value at the path 'users/bob002'.
"""
db.update('users/bob002', updated_user)

```

#### Value

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

"""
This callback function will be passed the all the contents on the path.
To print the username from the return data dictionary we must iterate
over the returned data["value"].
"""
def printAllUsers(url, data):
    # entire path's contents are sent
    for user in data["value"]:
        print data["value"][user]["username"] + " has joined."

# The printAllUsers method will fire when any change at the URL path 'users/'
# is modified(added, removed, updated).
db.value('users/', printAllUsers)

new_user = {
    'username': 'Bob',
    'profession': 'builder'
}

updated_user = {
    'username': 'Bob',
    'profession': 'plumber'
}

"""
The following methods will all trigger the firing of the value method and the
return of the entire path's value.
Note: That the values must exists at users/bob002 for update and remove methods to work.
"""

db.set('users/bob002', new_user)

db.update('users/bob002', updated_user)

db.remove('users/bob002')

```

### Once Event Callbacks
The following retrieval examples have the once parameter equal to `True`.
The callback function at the given URL path will run once.

#### Child Added

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

# This callback function will print the username from the return data dictionary.
def printAddedUser(url, data):
    print data['value']['username'], " has joined."

# The child_added method will retrieve one child at the URL path 'users/'.
db.child_added('users/', printAddedUser, True)

new_user = {
    'username': 'Bob',
    'profession': 'builder'
}


"""
The push method will add a new user to the database, but this will not trigger
the child_added event at 'users/' and fire the printAddedUser method!
It has already retrieved a user and will not listen for this push method's child_added
event.
"""
db.push('users/', new_user)

```

#### Child Removed

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

# This callback function will print the username from the return data dictionary.
def printRemovedUser(url, data):
    print data['value']['username'], " has left."

# The child_removed method will fire when a child at the URL path 'users/'
# is removed and not fire again.
db.child_removed('users/', printRemovedUser, True)

"""
The remove method will remove the object at 'users/bob002' from the database.
This will trigger a child_removed event at 'users/' and fire the printRemovedUser method.
To see the effect you will need to have a value at the path 'users/bob002'.
"""
db.remove('users/bob002')
# this update will not trigger the child_removed function
db.remove('users/mary004')

```

#### Child Updated

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

# This callback function will print the username from the return data dictionary.
def printUpdatedUser(url, data):
    print data['value']['username'], " has updated."

# The child_updated method will fire when a child at the URL path 'users/'
# is updated and then will not fire again.
db.child_updated('users/', printUpdatedUser, True)

bob_updated_user = {
    'username': 'Bob',
    'profession': 'plumber'
}

mary_updated_user = {
    'username': 'Mary',
    'profession': 'doctor'
}

"""
The update method will update the object at 'users/bob002' from the database.
This will trigger a child_updated event at 'users/' and fire the printUpdatedUser method.
To see the effect you will need to have a value at the path 'users/bob002'.
"""
db.update('users/bob002', bob_updated_user)
# this update will not trigger the child_updated function
db.update('users/mary004', mary_updated_user)

```

#### Value

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

```python
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')

"""
Try this callback function will be passed the all the contents on the path.
To print the username from the return data dictionary we must iterate
over the returned data["value"].
"""
def printAllUsers(url, data):
    # entire path's contents are sent
    for user in data["value"]:
        print data["value"][user]["username"] + " has joined."

# The printAllUsers method will fire only once at the URL path 'users/'.
db.value('users/', printAllUsers, True)

new_user = {
    'username': 'Bob',
    'profession': 'builder'
}

"""
The push method will add a new user to the database, but this will not trigger
the value event at 'users/' and fire the printAllUsers method!
It has already retrieved the path contents and will not listen for this push method's
value event.
"""
db.push('users/', new_user)

```

## Common Use Cases

### Set and Retrieve

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).

Run this example more than once to fully understand the code!

```python

from time import sleep
from random import randint
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16l0w',
                           'fir-docs-demo', 'fir-docs-demo')

# initial lives count we want updated
lives = 0

"""
Try this callback function will be passed the all the contents on the path.
There will need to be a integer value at the URL path 'lives/' for this example to work.
"""
def getLives(url, data):
    global lives
    lives = data["value"]

"""
With the once parameter set to `True` the getInitialLives method will
fire only once at the URL path 'lives/'.
We can use this .value() method with .set() method to get and set values.
"""
def retrieveFromDB():
    db.value('lives/', getLives, True)

"""
The set method will set the new value for lives in the database, but this will not trigger the value event at 'lives/' again until we want to get the value again.
"""
def sendToDB(val):
    db.set('lives/', val)

# value of lives is 0
print("Global lives value: " + str(lives))
# will assign the value of lives variable asynchronously
retrieveFromDB()
# wait for lives to be assigned
sleep(5)
# lives should be the value from database
print("Original database value: " + str(lives))
# set value of lives to random integer on database
random_int = randint(0,10)
print("Random integer is: " + str(random_int))
sendToDB(random_int)
# new value has only been sent to database not the global variable
# value should be the same as random_int
print("Still original database value: " + str(lives))
# will assign the value of lives variable asynchronously
retrieveFromDB()
# wait for lives to be assigned
sleep(5)
# lives should be updated and should print the random number
print("Database value should return random_int value: " + str(lives))

```

### Unique Push Key Child Added, Child Updated, Child Removed

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).
For help on the Processing library head to [Processing setup](/processing/setup).

```python

from processing import *
import firebase

db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16l0w',
                           'fir-docs-demo', 'fir-docs-demo')

# Prints out the list of current objects at database URL 'users/'.
# Continues to print every added object at database URL 'users/'.
def handleAddedUser(url, data):
    user_id = data["key"]
    username = data["value"]["username"]
    print "child_added callback:"
    print "key", user_id
    print "username", username

# Prints out the updates object and key on the URL 'users/'.    
def handleUpdatedUser(url, data):
    user_id = data["key"]
    username = data["value"]["username"]
    print "child_updated:"
    print "key", user_id
    print "username", username

# Prints out the removed object and key on the URL 'users/'.
def handleRemovedUser(url, data):
    user_id = data["key"]
    username = data["value"]["username"]
    print "child_removed:"
    print "key", user_id
    print "username", username

# attach child_added listener on users/ path
db.child_added('users/', handleAddedUser)
# attach child_updated listener on users/ path
db.child_updated('users/', handleUpdatedUser)
# attach child_removed listener on users/ path
db.child_removed('users/', handleRemovedUser)

# setup processing
def setup():
    size(120, 30)
    background(0, 0, 0)

# draw run command button
def draw():
    background(0,0,0)
    textSize(14)
    text("Run Command", 10, 20)

# On clicking run command button pass command as a string.
# JavaScript dialog box will show.
# Take the key from previous user objects to use update and remove.
def mouseClicked():
    cmd = raw_input("Enter Command([a]dd, [r]emove, [u]pdate):")
    if cmd is "a":
        addUser()
    elif cmd is "r":
        removeUser()
    elif cmd is "u":
        updateUser()

# Prompts for inputing new user's username into javascript dialog box.
# Pushes new object to 'users/' URL path and will trigger child_added
# event.
def addUser():
    username = raw_input("New username:")
    db.push('users/',
            {
             'username': username
             })

# Prompts for inputing new user's key into javascript dialog box.
# Removed object at 'users/' + key URL path and will trigger
# child_removed event.
def removeUser():
    user_id = raw_input("Enter key for user to delete:")
    db.remove('users/' + user_id)

# Prompts for inputing new user's key and username into javascript
# dialog box.
# Updates object at 'users/' + key URL path and will trigger
# child_updated event.
def updateUser():
    user_id = raw_input("Enter key for user to update:")
    username = raw_input("New username:")
    db.update('users/' + user_id,
            {
             'username': username
             })

# run processing
run()

```

## Chat Example

Note: This is not a working example until you add your own API key, database URL and authentication URL.
For help on setup head to [Firebase setup](./setup.md).
For help on the Processing library head to [Processing setup](/processing/setup).

```python

# import firebase and processing library
import firebase
from processing import *

# declare and initialize firebase db object
db = firebase.loadFirebase('AIzaSyATrCtlpxYanFOSt_6xPmj2z2phAL16lAI',
                           'fir-docs-demo', 'fir-docs-demo')
# global name
name = ""

def printOnAdd(url, data):
    """
    Callback function that prints the user's name followed by the message.
    """
    print data["value"]["name"], "says:"
    print "\t", data["value"]["text"]

# attach child_added listener on /messages path
db.child_added('/messages', printOnAdd)

# setup processing
def setup():
    size(120, 30)
    background(0, 0, 0)

# draw send message button
def draw():
    textSize(14)
    text("Send Message", 10, 20)

# on clicking message button enter message into
# javascript dialog box
def mouseClicked():
    global name
    msg = raw_input("Message:")
    db.push('/messages',
            {
             'name': name,
             'text': msg
             })

# prompts for inputing name into javascript dialog box
def initializeChat():
    global name
    name = raw_input("Name:")

# call initializeChat method and run processing
initializeChat()
run()


```

### Credits

* [Google Firebase](https://firebase.google.com/docs/web/setup)
