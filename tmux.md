[====COMMAND LINE====]
tmux new -s [name] | Creates new session called [name]
tmux a | Attach to the last running session
tmux a -t [name] | Attach to session [name]
tmux ls | List session
tmux list-keys | Shows default key bindings
tmux kill-session -t [name] | Kill [name] session

[====WINDOW MANAGEMENT====]
prefix c | Create a window
prefix 1 | Move to window 1
prefix x | Kill current window
prefix , | Rename current window
prefix n | Move to next window
prefix p | Move to previous window

[====PANE MANAGEMENT====]
prefix |     | Create vertical split
prefix -     | create horizontal split
prefix j     | move down pane
prefix k     | move up pane
prefix h     | move right pane
prefix l     | move left pane
prefix x     | Kill current pane
prefix o     | Iterate through panes
prefix C-o   | Rotate the panes forward
prefix {     | Swap the current pane with the previous pane.
prefix }     | Swap the current pane with the next pane.
prefix SPACE | Iterate through preset layouts
# Cannot get to work because meta key not working on OS X
#prefix M-o  | Rotate the panes backward
#prefix M-1 to M-5 | Arrange panes in one of the five preset layouts: even-horizontal, even-vertical, main-horizontal,

[====COPY & PASTE====]
prefix [ | Enter copy mode which allows you to scroll aka page up and page down
prefix v | Start visual highlight of text to copy
prefix y | Copy highlighted text to tmux clipboard only
prefix ] | Paste text from tmux clipboard
prefix q | Quit copy mode

[====MISC====]
prefix d | Detach from current session
prefix : | tmux command prompt

     The default command key bindings are:

           C-b         Send the prefix key (C-b) through to the application.
           C-o         Rotate the panes in the current window forwards.
           C-z         Suspend the tmux client.
           !           Break the current pane out of the window.
           "           Split the current pane into two, top and bottom.
           #           List all paste buffers.
           $           Rename the current session.
           %           Split the current pane into two, left and right.
           &           Kill the current window.
           '           Prompt for a window index to select.
           ,           Rename the current window.
           -           Delete the most recently copied buffer of text.
           .           Prompt for an index to move the current window.
           0 to 9      Select windows 0 to 9.
           :           Enter the tmux command prompt.
           ;           Move to the previously active pane.
           =           Choose which buffer to paste interactively from a list.
           ?           List all key bindings.
           D           Choose a client to detach.
           [           Enter copy mode to copy text or view the history.
           ]           Paste the most recently copied buffer of text.
           c           Create a new window.
           d           Detach the current client.
           f           Prompt to search for text in open windows.
           i           Display some information about the current window.
           l           Move to the previously selected window.
           n           Change to the next window.
           o           Select the next pane in the current window.
           p           Change to the previous window.
           q           Briefly display pane indexes.
           r           Force redraw of the attached client.
           s           Select a new session for the attached client interactively.
           L           Switch the attached client back to the last session.
           t           Show the time.
           w           Choose the current window interactively.
           x           Kill the current pane.
           {           Swap the current pane with the previous pane.
           }           Swap the current pane with the next pane.
           ~           Show previous messages from tmux, if any.
           Page Up     Enter copy mode and scroll one page up.
           Up, Down
           Left, Right
                       Change to the pane above, below, to the left, or to the right of the current pane.
           M-1 to M-5  Arrange panes in one of the five preset layouts: even-horizontal, even-vertical, main-horizontal,
                       main-vertical, or tiled.
           M-n         Move to the next window with a bell or activity marker.
           M-o         Rotate the panes in the current window backwards.
           M-p         Move to the previous window with a bell or activity marker.
           C-Up, C-Down
           C-Left, C-Right
                       Resize the current pane in steps of one cell.
           M-Up, M-Down
           M-Left, M-Right
                       Resize the current pane in steps of five cells.
