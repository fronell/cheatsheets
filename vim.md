# References
https://thevaluable.dev/vim-intermediate/

# HOT TIPS THAT ARE ON FIRE!
```
<C-f> on command  | Editor command in command mode with Vim syntax
~                 | Toggle uppercase or lowercase on a letter
gUw               | Change word to Uppercase
guw               | Change word to Lowercase
<C-a>             | Increment number
<C-x>             | Decrement number
gqq               | Enforce textwidth limit on line
<C-n>             | Brings up tab-completion list
<C-v>             | Visual block editing
```

# Buffers
```
:bn       | Go to next buffer
:bp       | Go to previous buffer
:bufdo    | Run command against multiple buffers (google for more detail)
:bd       | Delete a buffer (close a file)
:N,Mbd    | Delete buffer range N-M
:1,$bd    | Delete all buffers
:Bd       | Delete a buffer without closing window using Bbye plugin
:Bdelete  | Close all open buffers but leave windows intact
```

# Copy and Pasting
```
:"0P    | Paste in last yanked text in front of cursor position
<C-r>0  | Paste while in insert mode
"+y     | Yank to system clipboard
"+p     | Put from system clipboard
<C-r>+  | Paste from system clipboard while in insert mode
```

# Diffing Windows
```
:windo diffthis  | Diff open windows
]c               | Goto next change
[c               | Goto previous change
:diffoff         | Turn off diff for current window
:diffoff!        | Turn off diff for all windows
:diffupdate      | Do this if diff doesn't reflect changes in the buffer(s)
do               | Obtain changes from other window (Incompatible w/Visual mode)
dp               | Put changes into other window (Incompatible w/Visual mode)
                 | I've found diffget and diffput work better than do and dp.
                   Will need to document them next time I do a diff
```

# File Format
```
:set ff=unix  | Set format to unix, best method for removing ^M line endings
,m            | Old way of removing ^M line endings for dos files
```

# Folding
```
zi         | open/close all folds
zm         | Increases the foldlevel by one.
zr         | Decreases the foldlevel by one.
zfa}       | Fold block delimited by {}, works with (), [], <> also
za         | toggle current fold open/closed
zc         | close current fold
zM         | close all folds
zv         | expands folds to reveal cursor
zf#j       | Creates a fold from the cursor down # lines.
zf/string  | Creates a fold from the cursor to string .
zj         | Moves the cursor to the next fold.
zk         | Moves the cursor to the previous fold.
zo         | Opens a fold at the cursor.
zO         | Opens all folds at the cursor.
zR         | Decreases the foldlevel to zero -- all folds will be open.
zd         | Deletes the fold at the cursor.
zE         | Deletes all folds.
[z         | Move to start of open fold.
]z         | Move to end of open fold.
```

# grep
## Internal: Slower but it works even if grep isn't installed
```
:vim /<pattern>/ <file/path/*>        | grep pattern in file/path
:vim /<pattern>/ <file/path/**>       | grep pattern in all files recursively
:vim /<pattern>/ <file/path/**/*.rb>  | grep pattern in .rb files recursively
```
## External: Faster and can be used like regular grep
```
:grep [options] <pattern> <file/path/*>  | Uses grep on the system
```

# Help
The Help command requires tags to show documentation for a plugin.  The
command ":Helptags" must be run when plugins are added or existing plugin
documentation has been changed to create the tags.
```
:Helptags      | Create help tags for plugins (command provided by Pathogen)
:h <tag>       | Open help for tag in split, tab completion supported
:vert h <tag>  | Open help for tag in vsplit, tab completion supported
```

# Indentation
```
>>    | Indent line by shiftwidth spaces
<<    | De-indent line by shiftwidth spaces
5>>   | Indent 5 lines
5==   | Re-indent 5 lines
>%    | Increase indent of a braced or bracketed block (place cursor on brace)
=%    | Reindent a braced or bracketed block (cursor on brace)
<%    | Decrease indent of a braced or bracketed block (cursor on brace)
]p    | Paste text, aligning indentation with surroundings
=i{   | Re-indent the 'inner block', i.e. the contents of the block
=a{   | Re-indent 'a block', i.e. block and containing braces
=2a{  | Re-indent '2 blocks', i.e. this block and containing block
>i{   | Increase inner block indent
<i{   | Decrease inner block indent
```

# Motions
```
%	 | Move to corresponding bracket
(	 | Move cursor to the beginning of current sentence
)  | Move cursor to beginning of next sentence
```

# Movement Commands
```
<C-e>  | Scroll down one line at a time
<C-y>  | Scroll up one line at a time
<C-d>  | Scroll down half a page
<C-u>  | Scroll up half a page
<C-f>  | Scroll forward one page
<C-b>  | Scroll back one page
^      | Move to the first non-blank character on the current line
(      | Move to the beginning of current sentence
)      | Move to the end of next sentence
{      | Move to the beginning of current paragraph
}      | Move to the beginning of next paragraph
[[     | Move to the beginning of current section
]]     | Move to the beginning of next section
#G     | Move to line #
zz     | move current line to the middle of the screen
zt     | move current line to the top of the screen
zb     | move current line to the bottom of the screen
```

# Options in Vim
```
:set no<option>  | Unset the option.
:set <option>!   | Toggle the option.
:set <option>?   | Return the option’s value.
```

# Search
```
ggn     | Jump to first search results
GN      | Jump to last search result
CTRL-O  | Go back to where you came from
CTRL-I  | Goes forward
```

# Search and Replace with RegEx
```
:,$s/BEFORE/AFTER/   | Replace from current line to end of file
:,%s:BEFORE:AFTER:   | Colon delimiter (can use any non-regex metacharacter)
:%s/\vBEFORE/AFTER/  | Very magic mode so metacharacters like [] () don't need
                       escaping
:%s/\VBEFORE/AFTER/  | Literal mode, need to escape all metacharacters
g/regex/d|t|m        | Delete|Copy|Move lines that match regex
g/regex/s/old/new/   | Replace old with new on lines that match regex
v/regex/s/old/new/   | Replace old with new on lines that don't match regex
s//NEW               | Replace currently highlighted string using * with NEW
```

# Shell Commands
Vim8 Builtin Terminal: https://gist.github.com/mahemoff/8967b5de067cffc67cec174cb3a9f49d 
```
:r !date         | Reads command into file
:!<command>      | Runs <command>
:!<command> %    | Runs <command> on file in buffer (Save file before running)
:r <filename|!>  | Pastes <filename|command> below cursor position
```

# Splits
```
:vert <cmd>  | Prepend to command to open as vsplit i.e. :vert h motion
:abo <cmd>   | Prepend to command to open split above
:bel <cmd>   | Prepend to command to open split below
:to <cmd>    | Prepend to command to open split at the top
:bo <cmd>    | Prepend to command to open split at the bottom
```

# Tabs
```
gt       | Move to next tab
gT       | Move to previous tab
#gt      | Move directly tab #
:tabo    | Close all tabs but the active one
:tabm #  | Move active tab to position after tab #
```

# Tabular
Reference: http://vimcasts.org/episodes/aligning-text-with-tabular-vim/
```
n,mTab /\A-   | Align on the 1st - in string (useful if there are multiple -)
n,mTab /:\zs  | Align using the 1st character after the :, useful when you want
                to keep the : with the preceding word but align everything after
                i.e. "data:    value" instead of "data    : value"
                \zs is a vim specific token for regular expressions
```

# Tags
```
:ta t      | jump to tag t
:nta       | jump to nth newer tag in list
^],^T      | jump to the tag under cursor, return from tag
:ts t      | list matching tags and select one for jump
:tj t      | jump to tag or select one if multiple matches
:tags      | print tag list
:npo,:n^T  | jump back from, to nth older tag
:tl        | jump to last matching tag
^W},:pt t  | preview tag under cursor, tag t
^W]        | split window and show tag under cursor
^Wz,:pc    | close tag preview window
```

# Visual Selection
```
<from_line>GV<to_line>G  | Visually select range
<from_line>GV<count>j    | Visually select <count> lines down (j) <from_line>
vi}                      | Visually select everything inside {}
```

# Windows
```
:new          | Creates a new window in horizontal split with an empty buffer
:vnew         | Creates a new window in vertical split with an empty buffer
:enew         | Creates a new window with an empty buffer and switches to it
:sp <file>    | Open <file> in a horizontal split
:vsp <file>   | Open <file> in a vertical split
:q            | Close current window
<C-w>s        | Show buffer in horizontally split windows
<C-w>v        | Show buffer in vertically split windows
<C-w>n        | Creates a new window in horizontal split with an empty buffer
<C-w>nv       | Creates a new window in vertical split with an empty buffer
<C-w>q        | Close current window
<C-w>o        | Close all windows but current
<C-w>T        | Move window to a new tab
<C-h,j,k,l>   | Nagivate through windows
<C-w>r        | Rotate windows downwards/rightwards
<C-w>R        | Rotate windows upwards/leftwards
<C-w>H,K,J,L  | Move current window to key position
<C-w>x        | Swap a window with its neighbor
<C-w>+        | Increase window height
<C-w>-        | Decreate window height
<C-w>>        | Increase window width
<C-w><        | Decrease window width
<C-w>=        | Make windows equal in size
<C-w>_        | Maximize window vertically
<C-w>|        | Maximize window horizontally
```

# PLUGINS
## ctrl-p
### ctrl-p commands
```
<F5>   | Purge/refresh the cache for the current directory to get new files,
         remove deleted files and apply new ignore options
<C-f>  | Cycle forward between modes
<C-b>  | Cycle backward between modes
<C-d>  | Switch to filename only search instead of full path
<C-r>  | Switch to Regexp mode
<C-k>  | Navigate up the result list (arrow keys also work)
<C-j>  | Navigate down the result list (arrow keys also work)
<C-t>  | Open the selected entry in a new tab
<C-v>  | Open the selected entry in a new split or ?
<C-x>  | Open the selected entry in a new split or ?
<C-n>  | Select the next string in the prompt's history
<C-p>  | Select the previous string in the prompt's history
<C-y>  | Create a new file and its parent directories
<C-z>  | Mark/unmark multiple files
<C-o>  | Open marked files
..     | Go up directory tree by one level, add more dots for multiple levels
       | End the input string with a colon : followed by a command to execute it
         on the opening file(s):
       | Use :diffthis when opening multiple files to run :diffthis on the first
         4 files.
```
### ctrl-p leader mappings
```
,pb  | buffer mode
,pm  | mru mode
,pt  | tag mode
,pf  | file mode
,pp  | mixed mode (everything)
```
### ctrl-p help
```
:help ctrlp-commands    | Help on commands
:help ctrlp-extensions  | Help on extensions
:help ctrlp-mappings    | Help on mappings
```
## fugitive
Reference: http://vimcasts.org/episodes/fugitive-vim-exploring-the-history-of-a-git-repository/
The screencast uses an older version of Fugitive with a different command syntax
but its still very relevant.
```
:G                  | git status in split that supports syntax operations such
                      as ]] to jump to next section or = to show changes
g?                  | Show available fugitive commands
:G log -- %         | Show entire commit history for file in current window
:G log -p -10 -- %  | Sow changes from last 10 commits in patch format
:G log -Sword -- %  | Search history of changes for file in current window
:Gvdiffsplit        | Opens vsplit diff between staged and working tree versions
:Gvdiffsplit!       | Does the above and maintain focus on current window
:G difftool -y      | Open new tab with diff splits for each file with a change
:Gread              | Git checkout file into buffer (does not modify git repo)
:Gvsplit HEAD~#:%   | Open file in current window from # commits ago in vsplit
```
## pt (The Platinum Searcher)
**IMPORTANT** Note: pt will skip binary files by default.  I found that **files
in the dos format are considered binary** by these tools and the fix is to
convert them to unix format using a tool such as dos2unix (or vim).  dos2unix
can be used to show if a file is in dos format by issuing the following
command:  
`dos2unix -ic *`  
Any text file listed is in dos format and needs to be converted so it can be
searched.   
**IMPORTANT** Note: pt for whatever reason **does not support a wildcard in the
path argument on Windows.**  For example, the following command will work on
Windows:
`pt {pattern} c:\cloud`
However, the following does not work:
`Pt {pattern} c:\cloud\*.txt`
To limit searches to a specific file extension, add the \G regex filename filter
option like so:
`Pt /G \.txt$ {pattern} c:\cloud`
```
:Pt [options] {pattern} [{directories}]   | Opens file if pattern found
:Pt! [options] {pattern} [{directories}]  | Does not open file if pattern found
:Pt! /G \.txt$ {pattern} c:\cloud\        | Workaround for Windows to limit a
                                            search to files ending in .txt
```
### pt Quickfix Window Commands
```
o   | Open (same as enter)
O   | Open and close quickfix window
go  | Preview file (open but maintain focus on ack.vim results)
t   | Open in new tab
T   | Open in new tab silently
h   | Open in horizontal split
H   | Open in horizontal split silently
v   | Open in vertical split
gv  | Open in vertical split silently
q   | Close the quickfix window
```
## Ruby
## Surround
Reference: https://vimeo.com/6093081
```
cs'"          | Change surrounding (cs) ' with "
ds'           | Delete surround (ds) '
ysi<Motion>{  | Surround <motion> with {} including a space i.e. { word }
ysi<Motion>}  | Surround <motion> with {} without a space i.e. {word}
yss)          | Wrap entire line in () with no space
<Visual>S)    | Wrap visual selection in () with no space
```
##  tcomment: Winner of comment plugin over nerdcommenter & vim-commentary
```
gc{motion}        | Comment or uncomment lines that {motion} moves over
gcc               | Comment or uncomment [count] lines
{Visual}gc        | Comment or uncomment the highlighted lines
gcu               | Uncomment the current and adjacent commented lines
:[range]TComment  | Comment or uncomment [range] lines
```

# How-To's
## Auto-indenting a whole file
```
ggVG  | Visually select the whole file
<...  | Flatten the structure.  Repeat as much as necessary with .
=G    | Auto-align the entire file based on the auto-indent rules
```
## Replacing tabs with spaces
```
:set tabstop=2  | Set all tabs to 2 spaces
:set expandtab  | Enable converting tabs to space (may not be needed)
:retab!         | Convert tabs to spaces
```

# Stuff I already know, or at least I think I do
## Various ways insert mode can be entered into
```
a  | Append after cursor
A  | Append after line
x  | Delete character at cursor
r  | Replace character at cursor
R  | Replace character at cursor onward
o  | Opens line below cursor and starts in insert mode
O  | Opens line above cursor and starts in insert mode
I  | Insert text at beginning of the line
```
