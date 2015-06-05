# User Guide {: .doctitle}
Configuration and usage of FindCursor.

---

## Getting Started
Find cursor provides only one command, and it works best when bound to a shortcut.  Simply setup a [keymap](#defining-keymaps) and you are ready to go.  Though if you prefer, you can add commands in the command palette, or menus.

## Command
find_cursor
: 

    When the command is first invoked, all cursors will turn to block cursors and blink making them highly visible.  Subsequent invocations (if performed before timeout) will cycle through the cursors focusing them in the view.  The focus modes are iterative (the default) and pan mode.  Pan mode will pan the view to the next available region that has cursors not already visible in the view.

    | Parameters | Type | Description |
    |------------|------|-------------|
    | reverse | bool | Controls the direction of cursor focusing when either iterating or panning through cursors. |
    | pan | bool | Controls whether the command will run in pan mode or iterative mode. |


## Defining Keymaps
Setting up commands is basically the same for either pan or iterative commands.  The command can be bound in a forward or reverse direction and in iterative or pan mode.  It is usually useful to bind both forward and reverse variants for easier cursor navigation.

```js
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
```

```js
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

## Settings

There is currently only one setting that can be used in FindCursor.

### find_mode_timeout
`find_mode_timeout` controls how long after each command invocation that navigating through cursors will be allowed.  After the time out is reached, the cursors return to normal mode and the next invocation will only make them highly visible again.

```js
    // How long before find mode times out
    // and cursors return to normal
    "find_mode_timeout": 3000
```
