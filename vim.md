# VIM
## General
:h | Bring up help

## Motions
%	| Move to corresponding bracket
(	| Move cursor to the beginning of current sentence
) | Move cursor to beginning of next sentence

## Searching
ggn	   | Jump to first search results
GN     | Jump to last search result
CTRL-O | Go back to where you came from
CTRL-I | Goes forward

## Insert Commands
a | Append after cursor
A | Append after line
x | Delete character at cursor
r | Replace character at cursor
R | Replace character at cursor onward
o | Opens line below cursor and starts in insert mode
O | Opens line above cursor and starts in insert mode
I | Insert text at beginning of the line

## Buffers
:bn    | go to next buffer
:bp    | go to previous buffer
:bd    | delete a buffer (close a file)
:N,Mbd | Delete buffer range N-M

## Folding
zi | open/close all folds
za  | toggle current fold open/closed
zc  | close current fold
zM  | close all folds
zv  | expands folds to reveal cursor
zf#j			| Creates a fold from the cursor down  #  lines.
zf/string		| Creates a fold from the cursor to string .
zj			| Moves the cursor to the next fold.
zk			| Moves the cursor to the previous fold.
zo			| Opens a fold at the cursor.
zO			| Opens all folds at the cursor.
zm			| Increases the foldlevel by one.
zr			| Decreases the foldlevel by one.
zR			| Decreases the foldlevel to zero -- all folds will be open.
zd			| Deletes the fold at the cursor.
zE			| Deletes all folds.
[z			| Move to start of open fold.
]z			| Move to end of open fold.

## Windows
C-w s       | Show buffer in horizontally split windows
C-w v       | Show buffer in vertically split windows
C-w n       | Creates a new window in horizontal split with an empty buffer
C-w nv      | Creates a new window in vertical split with an empty buffer
:enew       | Creates a new window with an empty buffer and switches to it
C-w q       | Close current window
:q          | Close current window
C-w o       | Close all windows but current
C-h,j,k,l   | Nagivate through windows
C-w r       | Rotate windows downwards/rightwards
C-w R       | Rotate windows upwards/leftwards
C-w H,K,J,L | Move current window to key position
C-w =       | Make windows equal in size
C-w +       | Increase window height
C-w -       | Decreate window height
C-w >       | Increase window width
C-w <       | Decrease window width

## Movement Commands
ctrl-d      | Scroll down half a page
ctrl-u      | Scroll up half a page
ctrl-f      | Scroll forward one page
ctrl-b      | Scroll back one page
(           | Move to the beginning of current sentence
)           | Move to the end of next sentence
{           | Move to the beginning of current paragraph
}           | Move to the beginning of next paragraph
[[          | Move to the beginning of current section
]]          | Move to the beginning of next section
<line num>G | Move to <line num>

## Diffing Windows
:windo diffthis | Diff open windows
:diffoff!       | Turn off diff

## Shell Commands
:r !date		    | Reads command into file
:!<command>		  | Executes <command>
:r <filename|!> | Pastes <filename|command> below cursor position

## Tags
:ta t     | jump to tag t
:nta      | jump to nth newer tag in list
^],^T     | jump to the tag under cursor, return from tag
:ts t     | list matching tags and select one for jump
:tj t     | jump to tag or select one if multiple matches
:tags     | print tag list
:npo,:n^T | jump back from, to nth older tag
:tl       | jump to last matching tag
^W},:pt t | preview tag under cursor, tag t
^W]       | split window and show tag under cursor
^Wz,:pc   | close tag preview window

# PLUGINS
## ctrl-p
Run :CtrlP or :CtrlP [starting-directory] to invoke CtrlP in find file mode.
Run :CtrlPBuffer or :CtrlPMRU to invoke CtrlP in find buffer or find MRU file mode.
Run :CtrlPMixed to search in Files, Buffers and MRU files at the same time.
Check :help ctrlp-commands and :help ctrlp-extensions for other commands.

Once CtrlP is open:

Press <F5> to purge the cache for the current directory to get new files, remove deleted files and apply new ignore options.
Press <c-f> and <c-b> to cycle between modes.
Press <c-d> to switch to filename only search instead of full path.
Press <c-r> to switch to regexp mode.
Use <c-j>, <c-k> or the arrow keys to navigate the result list.
Use <c-t> or <c-v>, <c-x> to open the selected entry in a new tab or in a new split.
Use <c-n>, <c-p> to select the next/previous string in the prompt's history.
Use <c-y> to create a new file and its parent directories.
Use <c-z> to mark/unmark multiple files and <c-o> to open them.
Run :help ctrlp-mappings or submit ? in CtrlP for more mapping help.

Submit two or more dots .. to go up the directory tree by one or multiple levels.
End the input string with a colon : followed by a command to execute it on the opening file(s):
Use :25 to jump to line 25.
Use :diffthis when opening multiple files to run :diffthis on the first 4 files.

## vim-ruby
CTRL-X CTRL-O | Autocomplete
CTRL-N | Next
CTRL-P | Previous
CTRL-Y | Accept
