Creating a session:

````
tmux new-session -s work
````

Attach to a session:

````
tmux attach -t work
````

Detach from a session: `C-b d`

Display a list of keyboard shortcuts:

````
C-b ?
````

Creating a new pane by splitting an existing one:

````
C-b "          split vertically (top/bottom)
C-b %          split horizontally (left/right)
````

Switching between panes:

````
C-b left       go to the next pane on the left
C-b right      (or one of these other directions)
C-b up
C-b down
C-b o          go to the next pane (cycle through all of them)
C-b ;          go to the last (previously used) pane
````

Resizing panes:

````
C-b M-up, C-b M-down, C-b M-left, C-b M-right
               resize by 5 rows/columns
C-b C-up, C-b C-down, C-b C-left, C-b C-right
               resize by 1 row/column

C-b x          kill the current pane
C-b q          display pane numbers for a short while
````

# SESSIONS, WINDOWS, PANES

Session is a set of windows, plus a notion of which window is current.

Window is a single screen covered with panes. 

Pane is a rectangular part of a window that runs a specific command, e.g. a
shell.


# GETTING HELP

Display a list of keyboard shortcuts:

````
C-b ?
````

Any command mentioned in this list can be executed as `tmux something` or `C-b
:something` (or added to `~/.tmux.conf`).


# MANAGING SESSIONS

Creating a session:

````
tmux new-session -s work
````

Create a new session that shares all windows with an existing session, but has
its own separate notion of which window is current:

````
tmux new-session -s work2 -t work
````

Attach to a session:

````
tmux attach -t work
````

Detach from a session: `C-b d`.

Switch between sessions:

````
C-b (          previous session
C-b )          next session
C-b L          ‘last’ (previously used) session
C-b s          choose a session from a list
````

Other:

````
C-b $          rename the current session
C-b
````

# MANAGING WINDOWS

Create a window:

````
C-b c          create a new window
````

Switch between windows:

````
C-b 1 ...      switch to window 1, ..., 9, 0
C-b 9
C-b 0
C-b p          previous window
C-b n          next window
C-b l          ‘last’ (previously used) window
C-b w          choose window from a list
````

Switch between windows with a twist:

````
C-b M-n        next window with a bell, activity or
               content alert
C-b M-p        previous such window
````

Other:

````
C-b ,          rename the current window
C-b &          kill the current window
````

# MANAGING SPLIT PANES

Creating a new pane by splitting an existing one:

````
C-b "          split vertically (top/bottom)
C-b %          split horizontally (left/right)
````

Switching between panes:

````
C-b left       go to the next pane on the left
C-b right      (or one of these other directions)
C-b up
C-b down
C-b o          go to the next pane (cycle through all of them)
C-b ;          go to the ‘last’ (previously used) pane
````

Moving panes around:

````
C-b {          move the current pane to the previous position
C-b }          move the current pane to the next position
C-b C-o        rotate window ‘up’ (i.e. move all panes)
C-b M-o        rotate window ‘down’
C-b !          move the current pane into a new separate
               window (‘break pane’)
C-b :move-pane -t :3.2
               split window 3's pane 2 and move the current pane there
````

Resizing panes:

````
C-b M-up, C-b M-down, C-b M-left, C-b M-right
               resize by 5 rows/columns
C-b C-up, C-b C-down, C-b C-left, C-b C-right
               resize by 1 row/column
````

Applying predefined layouts:

````
C-b M-1        switch to even-horizontal layout
C-b M-2        switch to even-vertical layout
C-b M-3        switch to main-horizontal layout
C-b M-4        switch to main-vertical layout
C-b M-5        switch to tiled layout
C-b space      switch to the next layout
````

Other:

````
C-b x          kill the current pane
C-b q          display pane numbers for a short while
````

# OTHER CONFIG FILE SETTINGS

Force a reload of the config file on C-b r:

````
unbind r
bind r source-file ~/.tmux.conf
````

Some other settings that I use:

````
setw -g xterm-keys on
````
