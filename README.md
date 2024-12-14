# Tmux Notes

## ***To Start***
```bash
tmux
```

## ***List all the sessions***
```bash
tmux list-sessions
tmux ls
```

## ***Detach the current session***
<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>d</kbd>


## ***Attach to an existing session***
```bash
tmux attach -t [session-id]
tmux a -t [session-id]
```

## ***Pane management***
- a pane is a terminal section within a window

### Horizontal Split

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>"</kbd>

### Vertical Split

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>%</kbd>

### Move to a different pane

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>arrow key</kbd>

### Resize a pane
```bash
:resize-pane -L 20 # Resizes the current pane Left by 20 cells
:resize-pane -R 20 # Resizes the current pane Right by 20 cells
:resize-pane -D 20 # Resizes the current pane Down by 20 cells
:resize-pane -U 20 # Resizes the current pane Upward by 20 cells

or 
:set mouse on # do resize with a mouse
:set mouse off
```


## ***Window management***
- a session can have multiple windows
- a window can have mutiple panes

### To create a Window
```bash
# within Tmux, type:
tmux new-window
```
or 

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>c</kbd>

### To switch between windows

### Previous Window ###

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>p</kbd>  

### Next Window ###

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>n</kbd>  

### Kill a Window ###

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>&</kbd>  

### Rename a Window ###

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>,</kbd>  


## ***Session Management***

### Rename a session ###
```bash
tmux rename-session [new-name]
```
or

<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>$</kbd>

### Switch to another session
<kbd>Ctrl</kbd> + <kbd>b</kbd>  <kbd>s</kbd>


## Awesome preset configurations
```bash
# Prefix + r to load conf file
bind r source ~/.tmux.conf \; display "~/.tmux.conf loaded!"

# Prefix + k to toggle mouse mode on/off
bind-key k set-option -g mouse \; display-message 'Mouse #{?mouse,on,off}'

# Use Alt-arrow keys to switch panes
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

# Prefix + h / v to set window split
bind-key h split-window -h
bind-key v split-window -v

# Shift arrow to switch windows
bind -n S-Left previous-window
bind -n S-Right next-window

# Status Bar
set -g status-bg black
set -g status-fg colour35
```
