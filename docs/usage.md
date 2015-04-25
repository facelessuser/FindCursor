# User Guide {: .doctitle}
Configuration and usage of SubNotify.
{: .doctitle-info}

---

# Getting Started
Create a command and define its search direction and whether you will use the pan feature or the default cursor iteration feature.

Example Keymap:
```javascript
    //////////////////////////////////
    // Find Cursor: Iterative Find
    //////////////////////////////////
    {
        "keys": ["ctrl+."],
        "command": "find_cursor",
        "args": {"reverse": false, "pan": false}
    },
    {
        "keys": ["ctrl+shift+."],
        "command": "find_cursor",
        "args": {"reverse": true, "pan": false}
    }

    //////////////////////////////////
    // Find Cursor: Panning Find
    //////////////////////////////////
    {
        "keys": ["ctrl+."],
        "command": "find_cursor",
        "args": {"reverse": false, "pan": true}
    },
    {
        "keys": ["ctrl+shift+."],
        "command": "find_cursor",
        "args": {"reverse": true, "pan": true}
    }
```
