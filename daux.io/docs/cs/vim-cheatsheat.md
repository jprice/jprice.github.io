========== Basics =============

:e filename 	Open filename for edition
:w 	            Save file
:q 	            Exit Vim
:q! 	        Quit without saving
:x 	            Write file (if changes has been made) and exit
:sav filename 	Saves file as filename
. 	            Repeats the last change made in normal mode
5. 	            Repeats 5 times the last change made in normal mode


Cut & paste:
1. Position the cursor where you want to begin cutting.
2. Press v (or upper case V if you want to cut whole lines).
3. Move the cursor to the end of what you want to cut.
4. Press d.
5. Move to where you would like to paste.
6. Press P to paste before the cursor, or p to paste after. 


========== Navigation ==========

1/2 ½	BOL (Begin-of-line)
0	    BOL (Begin-of-line)
$	    EOL (End-of-line)

H	    Goto HEADER (Top of the screen)
M	    Goto MIDDLE of BUFFER
L	    Goto last (bottom).

gg	    (BOF) Beginning of File
G	    (EOF) End of the file. 
10G	    Goto line 10
:10	    Goto line 10

gd	    Goto Definition of Variable

Ctrl+D	Page-by-page scrolling

CTRL+O	Last location (cursor)
CTRL-I	Next location (cursor)

*	    Next word
#	    Previous word

%	    on brackets {} () [] will find the matching one.


========== Change ==========

I               INSERT (at beginning)
A               INSERT (at end)

ci}             Change inside brackets
vi}             Select inside brackets

dgg             Delete to top
dG              Delete to bottom 	

d^              Delete to start of line
D               Delete to end of line (or d$)
dt;             Delete until ;

d}              Delete next p-graph 	
d{              Delete previous p-graph

j               Join line to Above
J               Join line to below

cc              Replace Line
S               Replace Line

s               Replace Letter (Delete then Insert Mode)
cw              Replace word
c$              Replace to EOL

deep            Swap two words in front of cursor (Cursor on empty space)
ddp             Swap two lines

g-              Undo Change
u               Undo Change
g+              Redo Change
CTRL+R          Redo Change

R               Overwrite/Replace mode (shift+r in normal mode)

y               Copy marked text
Y               Copy/Yank whole line
y$              Copy/Yank whole line
2yy             Copy 2 lines
yw              Copy word

ALT+j           Move current line UP
ALT+k           Move current line DOWN

ggVG            Select All
gg=G            Automatically indent code beautifully on whole file
=               Fix indentation on selected area

x               Delete current character
d<numb>w        Delete (opt. numb) next word after cursor

<numb>CTRL+A    Increment number by <numb>
CTRL+A	        Increment a number
CTRL+X          Decrement a number


========== Macro ==========

q	        Record Macro
q<key>	    Record macro and place it on <key>
@<key>      Run macro at <key>
3@q	        Run macro 3 times


========== Navigation/Files ==========

:cwd	                Show current working directory
:lcwd	                Show current (Tab/Window) directory
:ls	                    Show current buffers
:cd	                    Change directory
:lcd	                Change current (Tab/Window) directory

CTRL + w + w            Move to next window
CTRL + w + l            Move to window on the right of current
CTRL + w + h            Move to window on the left of current

CTRL + w; SHIFT + L     Rearrange window, to far right (move window right)
CTRL + w; SHIFT + H     Rearrange window, to far left (move window left)
CTRL + W + R            Rotate window


========== Visual commands ========== 
>	Indent Right
<	Indent Left
d	Delete marked text
~	Switch case
V	Select whole line
v   Select range of text with arrow keys

Multiline edit:
CTRL + Q
Mark the lines you want to edit
Hit Shift + I
Do your modifications
Hit ESC


========== Search / Replace ==========

/			        Search
<SPACE>			    Search
?       		    Backwards Search
n			        Next Search ¯
N			        Previous Search
SHIFT+*             Search for word under cursor

:bufdo /searchstr/	Search in all open files

:%s/old/new/g		replace all old with new throughout file
:%s/foo/bar/gi		The same as above, but ignore the case of the pattern you want to substitute. This replaces foo, FOO, Foo, and so on.
:%s/old/new/gc		replace all old with new throughout file with confirmations
:%s/foo/bar/c		For each line on the file, replace the first occurrence of foo with bar and confirm every substitution.

:rs/foo/bar/a		Substitute foo with bar. r determines the range and a determines the arguments.

:g/^#/d			    Delete all lines that begins with #
:g/^$/d			    Delete all lines that are empty

:ab mail mail@provider.org 	Define mail as abbreviation of mail@provider.org


========== Folding ========== 

za		Toggle folding
zA		Toggle folding recursively
zc		Close one or count folds under the cursor
zC		Close all folds under cursor
zD		Delete folds recursively
zE		Delete ALL Folds
zf		motion - Create a fold
zF		Create a fold for count lines
zi		Toggle foldenable

zM		Close all folds, set foldlevel=0, set foldenable
zR		Open all folds and set foldlevel to highest fold level.
zn		Fold "none": reset foldenable and open all folds
zN		Fold "normal": set foldenable and restore all folds
zo		Open one or count folds
z0		Open all folds under the cursor


========== Plugins / Extensions ========== 

,f		     Most Recent Files (MRU)
,o		     BufExplorer
CTRL+b+e     CTRLF
CTRL-j		 Trigger snippet
CTRL+TAB	 See all available snippets


========== Marks ========== 

m+[A-Z]		marks the current line with an alias of the key pressed.
'[A-Z]		goes to this mark.
http://vim.wikia.com/wiki/Using_marks


========== Tricks ========== 

:set tabline=[_%{getcwd()}_] 
Set tabline to current directory

Relative Directory
:set tabline=%{expand('%:p:h')}
Absolute Path
:set tabline=%{expand('%:p')}
File name
:set tabline=%{expand('%:t')}

/\t                Show all tabs:
/\s\+$             Show trailing whitespace:
/\(\S\+\)\@<=\s\+$ Show trailing whitespace only after some text (ignores empty lines):
/ \+\ze\t          Show spaces before a tab

========== Tabs ==========
tabe[dit] filename    opens filename in a new tab
CTRL+W+T              Move current split window into its own tab
tabc[lose]            Close the current tab page and all its windows
tabo[nly]             Close all tabs apart from the current one

tabmove 	          Move current tab to the end
tabmove 0 	          Move current tab to the beginning
tabmove 1 	          Move current tab to become the 2nd tab

,tn		              New TAB [ ]
,tc		              TAB Close [x]
,t		              Next TAB ¯
,w		              SAVE/WRITE
:tab sball	          Opens a new tab for each open buffer

,ba	                  Close ALL Buffers
,bd	                  Close BUFFER

gt	                  Next Tab
gT	                  Previous Tab
{i}gt                 go to tab in position i


========== Misc ========== 
.	                Repeat Command
0p	                Paste BOL
$p	                Paste EOL

CTRL+w+H            Window left
CTRL+w+L            Window Right
CTRL+w+K            Window Up
CTRL+w+J            Window Down

CTRL+WW	            Switch between Windows

CTRL+WQ	            Quit window
CTRL+WV	            Split Windows Vertical
CTRL-W_             Minimize window
CTRL-W|             Maximize window
CTRL-W+             Grow window
CTRL-W-             Shrink window

:bn	                Next Buffer
:bp	                Previous Buffer
:b #	            Goto # Buffer. (eg. ':b 1' goto buffer 1)
:b filename

,pp	                Toggle Paste Mode
,cd	                Switch CWD to Dir of Open Buffer

:r	                Read from file into buffer
gf	                open file under cursor (or import statement)
<c-w>f	            open in a new window (Ctrl-w f)
<c-w>gf	            open in a new tab (Ctrl-w gf) 

,ss	                Toggle spellcheck equivalent to set spell
,m	                Remove Windows ^M encoding.
,e	                Reload vimrc
so $MYVIMRC         Reload vimrc

CTAGS
# Generate tags (for goto definition, goto file, taglist) for PHP and template files (*.tpl)
ctags -R --languages=php --langmap=PHP:+.tpl .
ctags -R --languages=php --langmap=PHP:+.tpl --tag-relative=yes --PHP-kinds=+cf  .

Syntax hightlighting
setf LANG (replace LANG, ex. setf C)

digraphs            Display all non-ascii characters, with keybindings

Prettify JSON (split one line, to N)
%!python -m json.tool


======== Comments =========
[count]<leader>cc |NERDComComment|
Comment out the current line or text selected in visual mode.

[count]<leader>cu |NERDComUncommentLine|
Uncomments the selected line(s).

[count]<leader>cn |NERDComNestedComment|
Same as <leader>cc but forces nesting.

[count]<leader>c |NERDComToggleComment|
Toggles the comment state of the selected line(s). If the topmost selected line is commented, all selected lines are uncommented and vice versa.

[count]<leader>cm |NERDComMinimalComment|
Comments the given lines using only one set of multipart delimiters.

[count]<leader>ci |NERDComInvertComment|
Toggles the comment state of the selected line(s) individually.

[count]<leader>cs |NERDComSexyComment|
Comments out the selected lines ``sexily''

[count]<leader>cy |NERDComYankComment|
Same as <leader>cc except that the commented line(s) are yanked first.

<leader>c$ |NERDComEOLComment|
Comments the current line from the cursor to the end of line.

<leader>cA |NERDComAppendComment|
Adds comment delimiters to the end of line and goes into insert mode between them.

|NERDComInsertComment|
Adds comment delimiters at the current cursor position and inserts between. Disabled by default.

<leader>ca |NERDComAltDelim|
Switches to the alternative set of delimiters.

[count]<leader>cl
[count]<leader>cb |NERDComAlignedComment|
Same as |NERDComComment| except that the delimiters are aligned down the left side (<leader>cl) or both sides (<leader>cb).


---

# This is from another I found. Contains some of the same info.

Cursor movement

h - move left
j - move down
k - move up
l - move right
ctrl-b - page up
ctrl-f - page down
% - jump to matching brace
w - jump by start of words (punctuation considered words)
W - jump by words (spaces separate words)
e - jump to end of words (punctuation considered words)
E - jump to end of words (no punctuation)
b - jump backward by words (punctuation considered words)
B - jump backward by words (no punctuation)
ge - jump backward to end of words (punctuation considered words)
gE - jump backward to end of words (no punctuation)
0 - (zero) start of line
^ - first non-blank character of line
$ - end of line
gg - Go to first line
[N]G - Go To line N. No N: last line
Note: Prefix a cursor movement command with a number to repeat it. For example, 4j moves down 4 lines.

Insert Mode - Inserting/Appending text

i - start insert mode at cursor
I - insert at the beginning of the line
a - append after the cursor
A - append at the end of the line
o - open (append) blank line below current line (no need to press return)
O - open blank line above current line
ea - append at end of word
Esc - exit insert mode

Editing

r - replace a single character (does not use insert mode)
J - join line below to the current one
cc - change (replace) an entire line
cw - change (replace) to the end of word
c$ - change (replace) to the end of line
s - delete character at cursor and subsitute text
S - delete line at cursor and substitute text (same as cc)
xp - transpose two letters (delete and paste, technically)
u - undo
ctrl-r - redo
. - repeat last command
~ - switch case
g~iw - switch case of current word
gUiw - make current word uppercase
guiw - make current word lowercase
>> - indent line one column to right
<< - indet line one column to left
== - auto-indent current line
ddp - swap current line with next
ddkP - swap current line with previous

Cut and Paste

dd - delete (cut) a line
dw - delete the current word
x - delete current character
X - delete previous character
D - delete from cursor to end of line
yy - yank (copy) a line
2yy - yank 2 lines
yw - yank word
y$ - yank to end of line
p - put (paste) the clipboard after cursor/current line
P - put (paste) before cursor/current line
:set paste - avoid unexpected effects in pasting

Visual Mode - Marking text

v - start visual mode, mark lines, then do command (such as y-yank)
V - start Linewise visual mode
o - move to other end of marked area
U - upper case of marked area
ctrl+v - start visual block mode
O - move to Other corner of block
aw - mark a word
ab - a () block (with braces)
aB - a {} block (with brackets)
ib - inner () block
iB - inner {} block
Esc - exit visual mode

Visual Mode - Commands

> - shift right
< - shift left
c - change (replace) marked text
y - yank (copy) marked text
d - delete (cut) marked text
~ - switch case

Visual Mode - Cut and paste

1. Place the cursor at the start of your text.
2. ma (marks the location as point 'a')
3. Place the cursor at the end of your text.
4. d'a (cuts back to location 'a')

Exiting

:w - write (save) the file, but don't exit
:wq - write (save) and quit
:x - same as :wq
:q - quit (fails if anything has changed)
:q! - quit and throw away changes

Search/Replace

/pattern - search for pattern
?pattern - search backward for pattern
n - repeat search in same direction
N - repeat search in opposite direction
:%s/old/new/g - replace all old with new throughout file
:%s/old/new/gc - replace all old with new throughout file with confirmations

Working with multiple files

:e filename - Edit a file in a new buffer
:n **/*.pl - Open all perl files under the current directory, recursively
:tabe filename - Edit a file in a new tab (Vim7, gVim)
:bnext (or :bn) - go to next buffer
:bprev (or :bp) - go to previous buffer
:bd - delete a buffer (close a file)
:sp filename - Open a file in a new buffer and split window
ctrl-w s - Split windows
ctrl-w w - switch between windows
ctrl-w q - Quit a window
ctrl-w v - Split windows vertically

Tabs (Vim7)

gt - Next tab
gT - Previous tab
:tabr - First tab
:tabl - Last tab
:tabm [N] - Move current tab after tab N. No N: last. N=0: first.
$vim -p file1 file2 fileN  - Open multiple files in different tabs (vim7) 

Command Line Options

$vim -c "vim command" file - execute an editor command on startup

Commands

:setlocal fileformat=dos|unix
:setlocal fileencoding=utf-8

More help

:help - main help portal (with links to more help pages)
:viusage - show a huge cheat sheet listing every command