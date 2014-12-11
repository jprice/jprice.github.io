# PASS

## NAME
<a name="NAME"></a>

pass - stores,
retrieves, generates, and synchronizes passwords
securely

## SYNOPSIS
<a name="SYNOPSIS"></a>

**pass** [
_COMMAND_ ] [ _OPTIONS_ ]... [ _ARGS_
]...

## DESCRIPTION
<a name="DESCRIPTION"></a>

**pass** is
a very simple password store that keeps passwords inside
**gpg2**(1) encrypted files inside a simple directory
tree residing at _~/.password-store_. The **pass**
utility provides a series of commands for manipulating the
password store, allowing the user to add, remove, edit,
synchronize, generate, and manipulate passwords.

If no COMMAND
is specified, COMMAND defaults to either **show** or
**ls**, depending on the type of specifier in ARGS.
Otherwise COMMAND must be one of the valid commands listed
below.

Several of the
commands below rely on or provide additional functionality
if the password store directory is also a git repository. If
the password store directory is a git repository, all
password store modification commands will cause a
corresponding git commit. See the _EXTENDED GIT
EXAMPLE_ section for a detailed description using
**init** and **git**(1).

The **init**
command must be run before other commands in order to
initialize the password store with the correct gpg key id.
Passwords are encrypting using the gpg key set with
**init**.

There is a
corresponding bash completion script for use with tab
completing password names in **bash**(1).

## COMMANDS
<a name="COMMANDS"></a>

**init** [
_--path=sub-folder_, _-p sub-folder_ ]
_gpg-id..._

Initialize new password storage
and use _gpg-id_ for encryption. Multiple gpg-ids may
be specified, in order to encrypt each password with
multiple ids. This command must be run first before a
password store can be used. If the specified _gpg-id_
is different from the key used in any existing files, these
files will be reencrypted to use the new id. Note that use
of **gpg-agent**(1) is recommended so that the batch
decryption does not require as much user intervention. If
_--path_ or _-p_ is specified, along with an
argument, a specific gpg-id or set of gpg-ids is assigned
for that specific sub folder of the password store. If only
one _gpg-id_ is given, and it is an empty string, then
the current _.gpg-id_ file for the specified
_sub-folder_ (or root if unspecified) is removed.

**ls** _subfolder_

List names of passwords inside
the tree at _subfolder_ by using the **tree**(1)
program. This command is alternatively named
**list**.

**grep**
_search-string_

Searches inside each decrypted
password file for _search-string_, and displays line
containing matched string along with filename. Uses
**grep**(1) for matching. Make use of the
_GREP_OPTIONS_ environment variable to set particular
options.

**find**
_pass-names_...

List names of passwords inside
the tree that match _pass-names_ by using the
**tree**(1) program. This command is alternatively named
**search**.

**show** [ _--clip_,
_-c_ ] _pass-name_

Decrypt and print a password
named _pass-name_. If _--clip_ or _-c_ is
specified, do not print the password but instead copy the
first line to the clipboard using **xclip**(1) and then
restore the clipboard after 45 (or
  _PASSWORD_STORE_CLIP_TIME_) seconds.

  **insert** [ _--echo_,
  _-e_ | _--multiline_, _-m_ ] [
  _--force_, _-f_ ] _pass-name_

  Insert a new password into the
  password store called _pass-name_. This will read the
  new password from standard in. If _--echo_ or _-e_
  is _not_ specified, disable keyboard echo when the
  password is entered and confirm the password by asking for
  it twice. If _--multiline_ or _-m_ is specified,
  lines will be read until EOF or Ctrl+D is reached.
  Otherwise, only a single line from standard in is read.
  Prompt before overwriting an existing password, unless
  _--force_ or _-f_ is specified. This command is
  alternatively named **add**.

  **edit**
  _pass-name_

  Insert a new password or edit
  an existing password using the default text editor specified
  by the environment variable _EDITOR_ or using
  **vi**(1) as a fallback. This mode makes use of temporary
  files for editing, but care is taken to ensure that
  temporary files are created in _/dev/shm_ in order to
  avoid writing to difficult-to-erase disk sectors. If
  _/dev/shm_ is not accessible, fallback to the ordinary
  _TMPDIR_ location, and print a warning.

  **generate** [
  _--no-symbols_, _-n_ ] [ _--clip_, _-c_
  ] [ _--in-place_, _-i_ | _

  --force_, _-f_ ] _pass-name pass-length_

  Generate a new password using
  **pwgen**(1) of length _pass-length_ and insert into
  _pass-name_. If _--no-symbols_ or _-n_ is
  specified, do not use any non-alphanumeric characters in the
  generated password. If _--clip_ or _-c_ is
  specified, do not print the password but instead copy it to
  the clipboard using **xclip**(1) and then restore the
  clipboard after 45 (or _PASSWORD_STORE_CLIP_TIME_)
  seconds. Prompt before overwriting an existing password,
  unless _--force_ or _-f_ is specified. If
  _--in-place_ or _-i_ is specified, do not
  interactively prompt, and only replace the first line of the
  password file with the new generated password, keeping the
  remainder of the file intact.

  **rm** [ _--recursive_,
  _-r_ ] [ _--force_, _-f_ ]
  _pass-name_

  Remove the password named
  _pass-name_ from the password store. This command is
  alternatively named **remove** or **delete**. If
  _--recursive_ or _-r_ is specified, delete
  pass-name recursively if it is a directory. If
  _--force_ or _-f_ is specified, do not
  interactively prompt before removal.

  **mv** [ _--force_,
  _-f_ ] _old-path new-path_

  Renames the password or
  directory named _old-path_ to _new-path_. This
  command is alternatively named **rename**. If
  _--force_ is specified, silently overwrite
  _new-path_ if it exists. If _new-path_ ends in a
  trailing _/_, it is always treated as a directory.
  Passwords are selectively reencrypted to the corresponding
  keys of their new destination.

  **cp** [ _--force_,
  _-f_ ] _old-path new-path_

  Copies the password or
  directory named _old-path_ to _new-path_. This
  command is alternatively named **copy**. If
  _--force_ is specified, silently overwrite
  _new-path_ if it exists. If _new-path_ ends in a
  trailing _/_, it is always treated as a directory.
  Passwords are selectively reencrypted to the corresponding
  keys of their new destination.

  **git**
  _git-command-args_...

  If the password store is a git
  repository, pass _git-command-args_ as arguments to
  **git**(1) using the password store as the git
  repository. If _git-command-args_ is **init**, in
  addition to initializing the git repository, add the current
  contents of the password store to the repository in an
  initial commit. If the git config key
  _pass.signcommits_ is set to _true_, then all
  commits will be signed using _user.signingkey_ or the
  default git signing key. This config key may be turned on
  using: **‘pass git config --bool --add
  pass.signcommits true‘**

  <table width="100%" border="0" rules="none" frame="void" cellspacing="0" cellpadding="0">
  <tbody><tr valign="top" align="left">
  <td width="11%"></td>
  <td width="6%">

  **help**
  </td>
  <td width="5%"></td>
  <td width="29%">

  Show usage message.
  </td>
  <td width="49%">
  </td></tr>
  </tbody></table>

  **version**

  Show version information.

  ## SIMPLE EXAMPLES
  <a name="SIMPLE EXAMPLES"></a>

  Initialize
  password store

  **zx2c4@laptop ~ $ pass init
  Jason@zx2c4.com**

  mkdir: created directory
  ‘/home/zx2c4/.password-store’

  Password store initialized for Jason@zx2c4.com.

  List existing passwords in
  store

  **zx2c4@laptop ~ $ pass**

  Password Store

  ├── Business

  │ ├── some-silly-business-site.com

  │ └── another-business-site.net

  ├── Email

  │ ├── donenfeld.com

  │ └── zx2c4.com

  └── France

  ├── bank

  ├── freebox

  └── mobilephone

  Alternatively,
  "**pass ls**".

  Find existing passwords in
  store that match .com

  **zx2c4@laptop ~ $ pass find
  .com**

  Search Terms: .com

  ├── Business

  │ ├── some-silly-business-site.com

  └── Email

  ├── donenfeld.com

  └── zx2c4.com

  Alternatively,
  "**pass search .com**".

  Show existing password

  **zx2c4@laptop ~ $ pass
  Email/zx2c4.com**

  sup3rh4x3rizmynam3

  Copy existing password to
  clipboard

  **zx2c4@laptop ~ $ pass -c
  Email/zx2c4.com**

  Copied Email/jason@zx2c4.com to clipboard. Will clear in 45
  seconds.

  Add password to store

  **zx2c4@laptop ~ $ pass insert
  Business/cheese-whiz-factory**

  Enter password for Business/cheese-whiz-factory: omg so much
  cheese what am i gonna do

  Add multiline password to
  store

  **zx2c4@laptop ~ $ pass insert
  -m Business/cheese-whiz-factory**

  Enter contents of Business/cheese-whiz-factory and press
  Ctrl+D when finished:

  Hey this is my

  awesome

  multi

  line

  passworrrrrrrrd.

  ^D

  Generate new password

  **zx2c4@laptop ~ $ pass
  generate Email/jasondonenfeld.com 15**

  The generated password to Email/jasondonenfeld.com is:

  $(-QF&amp;Q=IN2nFBx

    Generate new alphanumeric
    password

    **zx2c4@laptop ~ $ pass
    generate -n Email/jasondonenfeld.com 12**

    The generated password to Email/jasondonenfeld.com is:

    YqFsMkBeO6di

    Generate new password and copy
    it to the clipboard

    **zx2c4@laptop ~ $ pass
    generate -c Email/jasondonenfeld.com 19**

    Copied Email/jasondonenfeld.com to clipboard. Will clear in
    45 seconds.

    Remove password from store

    **zx2c4@laptop ~ $ pass remove
    Business/cheese-whiz-factory**

    rm: remove regular file
    ‘/home/zx2c4/.password-store/Business/cheese-whiz-factory.gpg’?
    y

    removed
    ‘/home/zx2c4/.password-store/Business/cheese-whiz-factory.gpg’

    ## EXTENDED GIT EXAMPLE
    <a name="EXTENDED GIT EXAMPLE"></a>

    Here, we
    initialize new password store, create a git repository, and
    then manipulate and sync passwords. Make note of the
    arguments to the first call of **pass git push**; consult
    **git-push**(1) for more information.

    **zx2c4@laptop
    ~ $ pass init Jason@zx2c4.com**

    mkdir: created directory
    ‘/home/zx2c4/.password-store’

    Password store initialized for Jason@zx2c4.com.

    **zx2c4@laptop
    ~ $ pass git init**

    Initialized empty Git repository in
    /home/zx2c4/.password-store/.git/

    [master (root-commit) 998c8fd] Added current contents of
    password store.

    1 file changed, 1 insertion(+)

    create mode 100644 .gpg-id

    **zx2c4@laptop
    ~ $ pass git remote add origin kexec.com:pass-store**

    **zx2c4@laptop
    ~ $ pass generate Amazon/amazonemail@email.com 21**

    mkdir: created directory
    ‘/home/zx2c4/.password-store/Amazon’

    [master 30fdc1e] Added generated password for
    Amazon/amazonemail@email.com to store.

    1 file changed, 0 insertions(+), 0 deletions(-)

    create mode 100644 Amazon/amazonemail@email.com.gpg

    The generated password to Amazon/amazonemail@email.com is:

    &lt;5m,_BrZY‘antNDxKN&lt;0A

    **zx2c4@laptop
    ~ $ pass git push -u --all**

    Counting objects: 4, done.

    Delta compression using up to 2 threads.

    Compressing objects: 100% (3/3), done.

    Writing objects: 100% (4/4), 921 bytes, done.

    Total 4 (delta 0), reused 0 (delta 0)

    To kexec.com:pass-store

    * [new branch] master -&gt; master

    Branch master set up to track remote branch master from
    origin.

    **zx2c4@laptop
    ~ $ pass insert Amazon/otheraccount@email.com**

    Enter password for Amazon/otheraccount@email.com:
    som3r3a11yb1gp4ssw0rd!!88**

    [master b9b6746] Added given password for
    Amazon/otheraccount@email.com to store.

    1 file changed, 0 insertions(+), 0 deletions(-)

    create mode 100644 Amazon/otheraccount@email.com.gpg

    **zx2c4@laptop
    ~ $ pass rm Amazon/amazonemail@email.com**

    rm: remove regular file
    ‘/home/zx2c4/.password-store/Amazon/amazonemail@email.com.gpg’?
    y

    removed
    ‘/home/zx2c4/.password-store/Amazon/amazonemail@email.com.gpg’

    rm ’Amazon/amazonemail@email.com.gpg’

    [master 288b379] Removed Amazon/amazonemail@email.com from
    store.

    1 file changed, 0 insertions(+), 0 deletions(-)

    delete mode 100644 Amazon/amazonemail@email.com.gpg

    **zx2c4@laptop
    ~ $ pass git push**

    Counting objects: 9, done.

    Delta compression using up to 2 threads.

    Compressing objects: 100% (5/5), done.

    Writing objects: 100% (7/7), 1.25 KiB, done.

    Total 7 (delta 0), reused 0 (delta 0)

    To kexec.com:pass-store

    ## FILES
    <a name="FILES"></a>

    **~/.password-store**

    The default password storage
    directory.

    **~/.password-store/.gpg-id**

    Contains the default gpg key
    identification used for encryption and decryption. Multiple
    gpg keys may be specified in this file, one per line. If
    this file exists in any sub directories, passwords inside
    those sub directories are encrypted using those keys. This
    should be set using the **init** command.

    ## ENVIRONMENT VARIABLES
    <a name="ENVIRONMENT VARIABLES"></a>

    _PASSWORD_STORE_DIR_

    Overrides the default password
    storage directory.

    _PASSWORD_STORE_KEY_

    Overrides the default gpg key
    identification set by **init**. Keys must not contain
    spaces and thus use of the hexidecimal key signature is
    recommended. Multiple keys may be specified separated by
    spaces.

    _PASSWORD_STORE_GIT_

    Overrides the default root of
    the git repository, which is helpful if
    _PASSWORD_STORE_DIR_ is temporarily set to a
    sub-directory of the default password store.

    _PASSWORD_STORE_X_SELECTION_

    Overrides the selection passed
    to **xclip**, by default _clipboard_. See
    **xclip**(1) for more info.

    _PASSWORD_STORE_CLIP_TIME_

    Specifies the number of seconds
    to wait before restoring the clipboard, by default _45_
    seconds.

    _PASSWORD_STORE_UMASK_

    Sets the umask of all files
    modified by pass, by default _077_.

    <table width="100%" border="0" rules="none" frame="void" cellspacing="0" cellpadding="0">
    <tbody><tr valign="top" align="left">
    <td width="11%"></td>
    <td width="9%">

    _EDITOR_
    </td>
    <td width="2%"></td>
    <td width="69%">

    The location of the text editor used by **edit**.
    </td>
    <td width="9%">
    </td></tr>
    </tbody></table>

    ## SEE ALSO
    <a name="SEE ALSO"></a>

    **gpg2**(1),
    **pwgen**(1), **git**(1), **xclip**(1).

    ## AUTHOR
    <a name="AUTHOR"></a>

    **pass** was
    written by [Jason A.
    Donenfeld](mailto:Jason@zx2c4.com). For updates and more information, a project
    page is available on the
    [World Wide
    Web](http://www.passwordstore.org/).

    ## COPYING
    <a name="COPYING"></a>

    This program is
    free software; you can redistribute it and/or modify it
    under the terms of the GNU General Public License as
    published by the Free Software Foundation; either version 2
    of the License, or (at your option) any later version.

    This program is
    distributed in the hope that it will be useful, but WITHOUT
    ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
    GNU General Public License for more details.

    You should have
    received a copy of the GNU General Public License along with
    this program; if not, write to the Free Software Foundation,
    Inc., 51 Franklin Street, Fifth Floor, Boston, MA
    02110-1301, USA.

    </div>
