# General
:h - Bring up help

# Misc
:set ff=unix - Set format to unix, best method for removing ^M line endings
,m           - Old way of removing ^M line endings for dos files
:pwd         - Show current working directory
:sp <file>   - Open <file> in a horizontal split
:vsp <file>  - Open <file> in a vertical split
:Helptags    - Generate help tags for plugins (provided by Pathogen)

# Copy and Pasting
:"0P         - Paste in last yanked text in front of cursor position
<C-r>0       - Paste while in insert mode
"+y          - Yank to system clipboard
"+p          - Put from system clipboard
<C-r>+       - Paste from system clipboard while in insert mode

# Visual Selection
<from_line>GV<to_line>G - Visually select range
<from_line>GV<count>j   - Visually select <count> lines down (j) <from_line>

# Visually select Ruby text objects
## Provided by vim-textobj-rubyblock
vir - Select inner-portion of ruby block
var - Select entire ruby block
## Provided by vim-ruby
vim - Select contents within current ruby method
vam - Select contents around current ruby method
viM - Select content within current ruby class
vaM - Select content around current ruby class

# Visually select inside delimiter
vi} - Visually select everything inside {}

# Search and Replace
:,$s/BEFORE/AFTER/  - Replace from current line to end of file
:,%s:BEFORE:AFTER:  - Colon delimiter (can use any non-regex metacharacter)
:%s/\vBEFORE/AFTER/ - Very magic mode so metacharacters like [] () don't need escaping
:%s/\VBEFORE/AFTER/ - Literal mode, need to escape all metacharacter

# Tabular
n,mTab /\A= - Align on the 1st = in the string (useful if there are multiple =)

# Motions
%	- Move to corresponding bracket
(	- Move cursor to the beginning of current sentence
) - Move cursor to beginning of next sentence

# Searching
ggn	   - Jump to first search results
GN     - Jump to last search result
CTRL-O - Go back to where you came from
CTRL-I - Goes forward

# Indentation
>>   - Indent line by shiftwidth spaces
<<   - De-indent line by shiftwidth spaces
5>>  - Indent 5 lines
5==  - Re-indent 5 lines

>%   - Increase indent of a braced or bracketed block (place cursor on brace first)
=%   - Reindent a braced or bracketed block (cursor on brace)
<%   - Decrease indent of a braced or bracketed block (cursor on brace)
]p   - Paste text, aligning indentation with surroundings

=i{  - Re-indent the 'inner block', i.e. the contents of the block
=a{  - Re-indent 'a block', i.e. block and containing braces
=2a{ - Re-indent '2 blocks', i.e. this block and containing block

>i{  - Increase inner block indent
<i{  - Decrease inner block indent

# Tabs
gt         - Move to next tab in normal mode
gT         - Move to previous tab in normal mode
#gt        - Move directly tab #
:tabonly   - Close all tabs but the active one
:tabmove # - Move active tab to position after tab #

# Movement Commands
C-e         - Scroll down one line at a time
C-y         - Scroll up one line at a time
ctrl-d      - Scroll down half a page
ctrl-u      - Scroll up half a page
ctrl-f      - Scroll forward one page
ctrl-b      - Scroll back one page
(           - Move to the beginning of current sentence
)           - Move to the end of next sentence
{           - Move to the beginning of current paragraph
}           - Move to the beginning of next paragraph
[[          - Move to the beginning of current section
]]          - Move to the beginning of next section
<line num>G - Move to <line num>
zz          - move current line to the middle of the screen
zt          - move current line to the top of the screen
zb          - move current line to the bottom of the screen

# Diffing Windows
:windo diffthis - Diff open windows
]c              - Goto next change
[c              - Goto previous change
:diffoff        - Turn off diff for current window
:diffoff!       - Turn off diff for all windows
:diffupdate     - Do this if diff doesn't reflect changes in the buffer(s)
:do             - Same as diffget but does not work with argument, range or visual mode
:dp             - Same as diffput but does not work with argument, range or visual mode
## I've found diffget and diffput work better than do and dp
:[range]diffg [bufspec]   - Modify the current buffer to undo difference with another buffer
                            If no range is given, the diff at the cursor position or just
                            above it is affected
:[range]diffput [bufspec] - Modify another buffer to undo difference with the current buffer
                            If no range is given, the diff at the cursor position or just
                            above it is affected

# Shell Commands
:r !date		    - Reads command into file
:!<command>		  - Executes <command>
:!<command> %	  - Executes <command> on file in opened buffer (must save changes to file)
:r <filename|!> - Pastes <filename|command> below cursor position

# Tags
:ta t     - jump to tag t
:nta      - jump to nth newer tag in list
^],^T     - jump to the tag under cursor, return from tag
:ts t     - list matching tags and select one for jump
:tj t     - jump to tag or select one if multiple matches
:tags     - print tag list
:npo,:n^T - jump back from, to nth older tag
:tl       - jump to last matching tag
^W},:pt t - preview tag under cursor, tag t
^W]       - split window and show tag under cursor
^Wz,:pc   - close tag preview window

# PLUGINS
## Ack
:Ack [options] {pattern} [{directories}]
### In quickfix window
o  - to open (same as enter)
O  - to open and close quickfix window
go - to preview file (open but maintain focus on ack.vim results)
t  - to open in new tab
T  - to open in new tab silently
h  - to open in horizontal split
H  - to open in horizontal split silently
v  - to open in vertical split
gv - to open in vertical split silently
q  - to close the quickfix window

## fugitive
Gblame      - Opens a vertical split window with the blame info on the left
Gdiff       - Compare working copy of file with the last commit
Gsdiff      - Compare working copy of file with the last commit in split
Gvdiff      - Compare working copy of file with the last commit in vsplit
Gstatus     - Bring up status window showing stage and unstaged changes
              Press - to toggle moving files between staged and unstaged
Glog [-<n>] - Bring up git log in seperate buffer with revisions in quickfix list
              n represents the amount of previous revisions to load

## nerdcommenter: No space inserted after comment character
,ci         - Comment a line on/off (inverse commenting)
<count>,ci  - Comment count lines on/off
<visual>,ci - Comment lines in visual mode on/off

## vim-commentary: Inserts space after comment character
gc{motion}         - Comment or uncomment lines that {motion} moves over
gcc                - Comment or uncomment [count] lines
{Visual}gc         - Comment or uncomment the highlighted lines
gcu                - Uncomment the current and adjacent commented lines
:[range]Commentary - Comment or uncomment [range] lines

##  tcomment: Winner of comment plugin over nerdcommenter & vim-commentary
gc{motion}       - Comment or uncomment lines that {motion} moves over
gcc              - Comment or uncomment [count] lines
{Visual}gc       - Comment or uncomment the highlighted lines
gcu              - Uncomment the current and adjacent commented lines
:[range]TComment - Comment or uncomment [range] lines

## vim-surround
cs'"  - Use surround plugin to replace surrounding ' with "s
ds'   - Delete ' delimiters
csw)  - Use motion w to wrap word in () with no spaces
ysiw{ - Wrap selected word in {} with space i.e. { word }
ysiw} - Wrap selected word in {} with no space i.e. {word}
yss)  - Wrap entire line in () with no space i.e (entire line of words)

## ctrl-p
### custom mappings
,pb - buffer mode
,pm - mru mode
,pt - tag mode
,pf - file mode
,pp - mixed mode (everything)

### commands
Press <F5> to purge/refresh the cache for the current directory to get new files, remove deleted files and apply new ignore options.
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
Use :diffthis when opening multiple files to run :diffthis on the first 4 files.

### help
:help ctrlp-commands   - Help on commands
:help ctrlp-extensions - Help on extensions

## VimFiler
{lhs}			    {rhs}
--------		  -----------------------------
<Tab>         (default)
			        (vimfiler_switch_to_another_vimfiler)
<Tab>         (enabled "no-quit" and "split" options)
			        (vimfiler_switch_to_other_window)
j             (vimfiler_loop_cursor_down)
k             (vimfiler_loop_cursor_up)
gg            (vimfiler_cursor_top)
<C-l>         (vimfiler_redraw_screen)
<Space>       (vimfiler_toggle_mark_current_line)
<S-LeftMouse> (vimfiler_toggle_mark_current_line)
<S-Space>     (vimfiler_toggle_mark_current_line_up)
*             (vimfiler_toggle_mark_all_lines)
#             (vimfiler_mark_similar_lines)
U             (vimfiler_clear_mark_all_lines)
c             (vimfiler_copy_file)
m             (vimfiler_move_file)
d             (vimfiler_delete_file)
Cc            (vimfiler_clipboard_copy_file)
Cm            (vimfiler_clipboard_move_file)
Cp            (vimfiler_clipboard_paste)
r             (vimfiler_rename_file)
K             (vimfiler_make_directory)
N             (vimfiler_new_file)
<Enter>       (vimfiler_cd_or_edit)
o             (vimfiler_expand_or_edit)
l             (vimfiler_smart_l)
x             (vimfiler_execute_system_associated)
X             (vimfiler_execute_vimfiler_associated)
h             (vimfiler_smart_h)
L             (vimfiler_switch_to_drive)
~             (vimfiler_switch_to_home_directory)
\             (vimfiler_switch_to_root_directory)
&             (vimfiler_switch_to_project_directory)
<C-j>         (vimfiler_switch_to_history_directory)
<BS>          (vimfiler_switch_to_parent_directory)
.             (vimfiler_toggle_visible_ignore_files)
H             (vimfiler_popup_shell)
e             (vimfiler_edit_file)
E             (vimfiler_split_edit_file)
B             (vimfiler_edit_binary_file)
ge            (vimfiler_execute_external_filer)
<RightMouse>  (vimfiler_execute_external_filer)
!             (vimfiler_execute_shell_command)
q             (vimfiler_hide)
Q             (vimfiler_exit)
-             (vimfiler_close)
g?            (vimfiler_help)
v             (vimfiler_preview_file)
O             (vimfiler_sync_with_current_vimfiler)
go            (vimfiler_open_file_in_another_vimfiler)
<C-g>         (vimfiler_print_filename)
g<C-g>        (vimfiler_toggle_maximize_window)
yy            (vimfiler_yank_full_path)
M             (vimfiler_set_current_mask)
gr            (vimfiler_grep)
gf            (vimfiler_find)
S             (vimfiler_select_sort_type)
<C-v>         (vimfiler_switch_vim_buffer_mode)
gc            (vimfiler_cd_vim_current_dir)
gs            (vimfiler_toggle_safe_mode)
gS            (vimfiler_toggle_simple_mode)
a             (vimfiler_choose_action)
Y             (vimfiler_pushd)
P             (vimfiler_popd)
t             (vimfiler_expand_tree)
T             (vimfiler_expand_tree_recursive)
I             (vimfiler_cd_input_directory)
<2-LeftMouse> (vimfiler_double_click)
gj            (vimfiler_jump_last_child)
gk            (vimfiler_jump_first_child)

# How-To's
## Diffing a file from a previous commit in git
>Open the file you want to diff
>:Gitv! to bring up the commit browser for the file
>Press D on the commit to diff against
### Commands to open commit but stay in buffer window
>o - Open in new split
>O - Open in new tab
>s - Open in new vsplit

## Auto-indenting a whole file
>ggVG to visually select the whole file
><... to flatten the structure.  Repeat as much as necessary with .
>gg to jump to the top of the file
>=G to auto-align the entire file based on the auto-indent rules

## Replacing tabs with spaces
>set tabstop=2 to set all tabs to 2 spaces
>set expandtab to enable converting tabs to space (may not be needed)
>retab! to convert tabs to spaces

# Stuff I already know, or at least I think I do
## Insert Commands
a - Append after cursor
A - Append after line
x - Delete character at cursor
r - Replace character at cursor
R - Replace character at cursor onward
o - Opens line below cursor and starts in insert mode
O - Opens line above cursor and starts in insert mode
I - Insert text at beginning of the line

# Buffers
:bn              - go to next buffer
:bp              - go to previous buffer
:bd              - delete a buffer (close a file)
:Bd              - delete a buffer without closing window using Bbye plugin
:N,Mbd           - Delete buffer range N-M
:bw              - Wipe out buffer, recommended to use buffer delete instead
:bufdo :Bdelete  - Close all open buffers but leave windows intact

# grep
## Internal: Slower but it works even if grep isn't installed
:vim /<pattern>/ <file/path/*>       - grep for pattern in file/path
:vim /<pattern>/ <file/path/**>      - grep for pattern in all files recursively
:vim /<pattern>/ <file/path/**/*.rb> - grep for pattern in .rb files recursively
## External: Faster and can be used like regular grep
:grep [options] <pattern> <file/path/*> - grep for <pattern> with [options]

# Folding
zi        - open/close all folds
zm        - Increases the foldlevel by one.
zr        - Decreases the foldlevel by one.
zfa}      - Fold block delimited by {}, works with (), [], <> also
za        - toggle current fold open/closed
zc        - close current fold
zM        - close all folds
zv        - expands folds to reveal cursor
zf#j      - Creates a fold from the cursor down  #  lines.
zf/string - Creates a fold from the cursor to string .
zj        - Moves the cursor to the next fold.
zk        - Moves the cursor to the previous fold.
zo        - Opens a fold at the cursor.
zO        - Opens all folds at the cursor.
zR        - Decreases the foldlevel to zero -- all folds will be open.
zd        - Deletes the fold at the cursor.
zE        - Deletes all folds.
[z        - Move to start of open fold.
]z        - Move to end of open fold.

# Windows
C-w s       - Show buffer in horizontally split windows
C-w v       - Show buffer in vertically split windows
C-w n       - Creates a new window in horizontal split with an empty buffer
:new        - Creates a new window in horizontal split with an empty buffer
C-w nv      - Creates a new window in vertical split with an empty buffer
:vnew       - Creates a new window in vertical split with an empty buffer
:enew       - Creates a new window with an empty buffer and switches to it
C-w q       - Close current window
:q          - Close current window
C-w o       - Close all windows but current
C-w T       - Move a window to a new tab
C-h,j,k,l   - Nagivate through windows
C-w r       - Rotate windows downwards/rightwards
C-w R       - Rotate windows upwards/leftwards
C-w H,K,J,L - Move current window to key position
C-w x       - Swap a window with its neighbor
C-w +       - Increase window height
C-w -       - Decreate window height
C-w >       - Increase window width
C-w <       - Decrease window width
C-w =       - Make windows equal in size
C-w _       - Maximize window vertically
C-w |       - Maximize window horizontally

# Omnicompletion
CTRL-X CTRL-O - Autocomplete
CTRL-N        - Next
CTRL-P        - Previous
CTRL-Y        - Accept
