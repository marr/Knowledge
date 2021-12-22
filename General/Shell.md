# Shell

## Learn more

- https://pubs.opengroup.org/onlinepubs/9699919799/

## View documentation

```shell
man some-thing
```

## Start a shell process

```
sh/bash/zsh
```

## Use paths

```
some-path(s)
```

- `~` absolute for the user’s directory.
- `/` absolute for the root directory.
- `.` relative for the current directory.
- `..` relative for the directory above the current directory.
- `*` wildcard for directory contents.
- `-` shorthand for the last directory.

For example:

```shell
rm -rf ~/Downloads/*
```

## Pipe output from one command as input to another

```shell
some-command | another-command
```

## Redirect output from one command to a file

```shell
some-command > some-file
```

## Append to a file

```shell
some-command >> some-file
```

## Use file contents in a command

```shell
some-file < some-command
```

## Run commands if the previous succeeds

```shell
some-command && another-command
```

- If the previous command has an exit code of `0`.

## Run commands if the previous fails

```shell
some-command || another-command
```

- If the previous command has an exit code other than `0`.

## Run commands in sequence whether they succeed or fail

```shell
some-command; another-command
```

## Define variables

```shell
some_local_variable=some_value
```

## Evaluate variables

```shell
$some_variable
```

For example:

```shell
echo $some_variable
```

## Share variables globally

```shell
export SOME_GLOBAL_VARIABLE=some_value
```

- Uppercase by convention to avoid clashing with local variables.

## View all global variables

```shell
export
```

- `PATH` includes what programs are available globally.

## Use global variables

```shell
$SOME_GLOBAL_VARIABLE
```

For example:

```shell
echo $PATH
```

## Exit the current process with a successful exit code

```shell
exit
```

## Exit the current process with a failed exit code

```shell
exit 1
```

## Check the last exit code

```shell
echo $?
```

## Run an executable

```
some-path<enter>
```

## Use search patterns (regular expressions)

```
# Match the starting position
^

# Match the ending position
$

# Match any single character
.

# Match the preceding element 0 or more times
*

* Can escape special characters with \ to use literal characters.
```

For example:

```
# Find instances of echo commands that use double quotes
^echo ".*"$
```

## Print the working directory

```shell
pwd
```

## Display running processes

```
ps [-e]
```

- `-e` for all including non-owned.

## Stop a process

```
kill [-15/-9] some-pid
```

- `-15` sends a SIGTERM signal to try to gracefully kill a process.
- `-9` sends a SIGKILL signal to force a process to quit with potential data loss or corruption.

## Stop the current process

```
<ctrl c>
```

- Sends a SIGINT signal to interrupt the current process.

## List directory contents

```
ls [-al] [some-directory]
```

- `-a` for all including hidden.
- `-l` for permissions (`r` is read, `w` is write, `x` is execute).

## Change directory

```shell
cd some-path
```

## Make directory

```shell
mkdir some-directory
```

## Create file

```shell
touch some-file
```

## Remove file / directory

```
rm [-rf] some-path
```

- `-r` is recursive for directories.
- `-f` is for forcing without prompting for confirmation.

## Move / rename file / directory

```shell
mv some-path another-path
```

## Copy file / directory

```
cp [-R] some-path another-path
```

- `-R` is recursive for directories.

## Use text

```shell
echo "Some text"
```

For example:

```shell
echo "Some text to append to file" >> some-file
```

## Find a search pattern

```
grep [-iRlv] some-search-pattern [some-path]
```

- `-i` to ignore casing.
- `-R` for recursive.
- `-l` for file names.
- `-v` for non matching.

## Substitute a search pattern

```
sed [-i] [""] 's/some-search-pattern/some-replacement/g' [some-path]
```

- `-i` to overwrite file(s) in place.
- `""` needed as a suffix in some versions.

## Sort lines

```
sort [-r] [some-file]
```

- `-r` for reverse.

## Filter adjacent repeated lines

```
uniq [some-file]
```

For example:

```shell
sort some-file | uniq
```

## Count lines

```
wc -l [some-file]
```

## Transform lines

```
awk [-F "some-delimiter"] '{action}' [some-file]
```

- `-F` to use a delimiter other than spaces.
- `print` for printing.
- `$#` for parts of line by delimiter.
- `$0` for entire line.

For example:

```shell
awk -F "," '{print $1, $3}' log.csv
```

## Find files / directories

```
find some-path [-type d] -name some-search-pattern
```

- `-type d` for directories.

For example:

```shell
find . -name '*.txt'
```

## Pass output of a command as arguments to another command

```shell
some-command | xargs another-command
```

For example:

```shell
find . -name '*.txt' | xargs grep -l copyright
```

## See where an executable is installed

```shell
command -v some-executable
```

## Compare the contents of two files / directories

```
diff [-r] some-path another-path
```

- `-r` for recursive.

## Use file contents

```
cat [some-file]
```

## Use the beginning of content

```
head [-n#] [some-file]
```

- `-n` for number of lines.

For example:

```shell
ls | head -n1
```

## Use the end of content

```
tail [-n#f] [some-file]
```

- `-n` for number of lines.
- `-f` for follow real-time.

For example:

```shell
tail -f some-log-file
```

## Page through content

```
more [some-file]
```

## Print system information

```
uname [-a]
```

- `-a` for all.

## Show who is logged in

```shell
who
```

## Track running time

```shell
time some-command
```

## Use current date

```shell
date
```

## Use command output

```
$(some-command)
```

## Do something for each item in a list

```shell
for some-item in some-list; do
  # ...
done
```

For example:

```shell
for dir in */; do echo "$dir"; done
```

## Get the last file / directory name in a path

```shell
basename some-path
```

For example:

```shell
for item_path in ~/some-path/items/*; do
  item=$(basename $item_path)
  echo "$item"
done
```

## Check the size of file / directory

```
du [-s] some-path
```

- `-s` for a sum.

## Change ownership of a file / directory

```shell
chown some-user some-path
```

## Change permissions of a file / directory

```
chmod owner/group/world-permissions some-path
```

- `owner` is myself.
- `group` is my group.
- `world` is everyone else.
- `r` is read.
- `w` is write.
- `x` is execute.
- `+` adds to existing permissions.
- `1` is 1 (execute).
- `2` is 2 (write).
- `3` is 2+1 (write/execute).
- `4` is 4 (read).
- `5` is 4+1 (read/execute).
- `6` is 4+2 (read/write).
- `7` is 4+2+1 (read/write/execute).

For example:

```shell
chmod +x some-script
chmod 755 somefile.txt
```

## Store commands in an executable file (script)

```shell
#!/bin/sh

# ...
```

For example:

```shell
#!/bin/sh

if ! command -v git > /dev/null; then
  echo "Error: git is required"
  exit 1
fi

if [ -z "$1" ]; then
  echo "Error: version argument is required"
  exit 1
fi

version=$1
git checkout some-main-branch
git pull
git tag v"$version"
git push --tags
```

## Edit text

```shell
vi[m]
```

For example:

```shell
cd some-project
vim .
```

### Compose commands

```
# Search pattern
/some-search-pattern
n

# Change
c

# Delete
d

# Yank
y

# Put
p

# Inside
i

# Around
a

# Parenthesis
(

# Braces
{

# Brackets
[

# Double quotes
"

# Single quotes
‘

# Backticks
`

# Tag
<

# Word
w

# Start of line
^

# End of line
$

# File top
gg

# File bottom
G

# Line number
#G

# Format
=

# Clipboard register
"+

For example:

# Search for ‘some ‘thing
/some thing

# Delete up to ‘some ‘thing
d/some thing

# Delete word
dw

# Change to end of line
c$

# Change inside braces
ci{

# Yank around brackets
ya[

# Clipboard register put
"+p

# Format to end of file
=G
```

### Return to normal mode

```
<ctrl [>
```

### Explore files / directories

```
:vs/e/E some-path
```

For example:

```
:vs .
:vs src/
:vs src/**/*some-file<tab>
:e src/**/*some-file<tab>
:E
```

### Go to window

```
<ctrl w h/j/k/l>
```

### Write

```
:w
```

### Quit

```
:q
```

### Run a shell command

```
:! some-command
```

### Undo

```
u
```

### Redo

```
<ctrl r>
```

### Repeat

```
.
```

### Record a macro

```
q{register}
{commands}
q
```

### Run a macro

```
@{register}
```

### Populate quickfix with a search pattern

```
:vim /[\c]some-search-pattern/[g] some-files
```

- `\c` for case insensitive.
- `g` for all matches in a file.

For example:

```
:vim /\ctodo/g `git ls-files`
:vim /TODO/g src/**/*.txt
```

### Run commands on quickfix

```
:c[f]do some-command
```

- `f` for only once per file.

For example:

```
:cfdo normal @q | :w
```

### Show quickfix

```
:cw
```

### Navigate quickfix

```
:cn/p
```

### Run commands on ranges

```
:some-range some-command
```

For example:

```
:15,25 normal @q
```

### Run commands on open windows

```
:windo some-command
```

### Substitute a search pattern

```
:some-range s/some-search-pattern/some-replacement/g
```

For example:

```
:%s/some thing/another thing/gc
```

### Complete word

```
<ctrl n>
<ctrl n/p>
```

### Complete line

```
<ctrl x><ctrl l>
<ctrl n/p>
```

### Page up/down

```
<ctrl f/b>
```

### Go to path under cursor

```
gf
```

### Go in/out

```
<ctrl i/o>
```

### Toggle syntax highlighting

```
:syntax on/off
```

### Compare the contents of windows

```
# Activate on current window
:diffthis

# Deactivate on current window
:diffoff
```

For example:

```
:windo diffthis
:windo diffoff
```

### Re-run commands

```
:some-search
<up/down>
<enter>
```
