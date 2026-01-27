# TMux Commands


### Sessions
```
# To create a new session
tmux

# To create a new session with name
tmux new -s my-newsession

# Already inside a tmux session
:new

# List all session outside a session
tmux ls

# List all sessions from inside a session
ctrl+b s

# To preview window and sessions and press enter to attach
ctrl+b w

# To attach most recent session
tmux attach

# To attach session by name
tmux attach -t my-session
```

### Window
```
# To create a new window
ctrl+b c

# To navigate bewteen windows
ctrl+b 1-9 # To switch windows by window numbers
ctrl+b p # Previous window
ctrl+b n # Nexts window


# To close a window
ctrl+b x
# and press y to confirm
y
```

### Panes
```
# Split vertical
ctrl+b %

# Split horizontal
ctrl+b "

# Move between panes arrow keys
ctrl+b ->
ctrl+b } # to move next pane
ctrl+b { # to move previous pane

ctrl+b o # for next pane
ctrl+b ; # for previous pane

# To close a pane
ctrl+b x
# and press y to confirm
y

# To toggle pane numbers
ctrl+b q

# then press a number which are visible
1

# To zoom in an pan
ctrl+b z

# To zoom out
ctrl+b !
```


### More refrence available at [tmuxcheatsheet.com](https://tmuxcheatsheet.com/)
