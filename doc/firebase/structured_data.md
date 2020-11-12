## Structured Data in Firebase

Firebase Realtime Database data is stored as JSON objects and takes the form of
a tree. When you add data to the JSON tree, it becomes a node in the existing
JSON structure with an associated key. You can provide your own keys, such as
user IDs or semantic names, or they can be provided for you using `push()`.

Note: Keys cannot contain ., $, #, [, ], /, or ASCII control characters 0-31 or 127.

### Example User Tree Structure

```JSON
{
    "users": {
        "-KP-55vu7MyiqFkpOWeP": {
            "username": "Bob"
        },
        "-KP-59G8ezqWdBdNMOZG": {
            "username": "John"
        },
        "-KP-5AdrJLSEVN1cZ27F": {
            "username": "Mary"
        },
        "bob002": {
            "name": "Bob",
            "friends": {
                "mary004": true
            }
        },
        "mary004": {
            "name": "Mary",
            "friends": {
                "bob002": true,
                "john010": true
            }
        },
        "john010": {
            "name": "John",
            "friends": {
                "mary004": true
            }
        }
    }
}
```

### Firebase Console Data

Find in your [Firebase Console](https://console.firebase.google.com/).

<img src="../images/firebase_structured_data.png" width="400px" />
