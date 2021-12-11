# Vim

## Learn more

- https://www.vim.org/docs.php.

## Start a vim process

```shell
cd some-project
vim .
```

## Compose commands

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

## Return to normal mode

```
<ctrl [>
```

## Explore files / directories

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

## Go to window

```
<ctrl w h/j/k/l>
```

## Write

```
:w
```

## Quit

```
:q
```

## Run a shell command

```
:! some-command
```

## Undo

```
u
```

## Redo

```
<ctrl r>
```

## Repeat

```
.
```

## Record a macro

```
q{register}
{commands}
q
```

## Run a macro

```
@{register}
```

## Populate quickfix with a search pattern

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

## Run commands on quickfix

```
:c[f]do some-command
```

- `f` for only once per file.

For example:

```
:cfdo normal @q | :w
```

## Show quickfix

```
:cw
```

## Navigate quickfix

```
:cn/p
```

## Run commands on ranges

```
:some-range some-command
```

For example:

```
:15,25 normal @q
```

## Run commands on open windows

```
:windo some-command
```

## Substitute a search pattern

```
:some-range s/some-search-pattern/some-replacement/g
```

For example:

```
:%s/some thing/another thing/gc
```

## Complete word

```
<ctrl n>
<ctrl n/p>
```

## Complete line

```
<ctrl x><ctrl l>
<ctrl n/p>
```

## Page up/down

```
<ctrl f/b>
```

## Go to path under cursor

```
gf
```

## Go in/out

```
<ctrl i/o>
```

## Toggle syntax highlighting

```
:syntax on/off
```

## Compare the contents of windows

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

## Re-run commands

```
:some-search
<up/down>
<enter>
```
