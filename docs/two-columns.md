[Table of Contents](../README.md)
# View text file in two columns
When reading text, it can be useful to make a wide window, then 
split it vertically so two consecutive pages of text can be seen 
in the left and right windows.

Wit a large monitor, you might enter `:set columns=160` to make 
the screen 160 columns wide. This tip can then be used to split 
the screen to show two windows, with the `'scrollbind'` option set 
so that scrolling one window also scrolls the other window.

## Mapping
Enter the following command:
```
:noremap <silent> <Leader>vs :<C-u>let @z=&so<CR>:set so=0 noscb<CR>:bo vs<CR>Ljzt:setl scb<CR>:let &so=@z<CR>
```
With the default leader, you can now press `\vs` to vertically 
split the screen into two windows with `'scrollbind'` set. To 
display only a single window, press Ctrl-W then `o`.

The mapping performs these operations:
```
:<C-u>             " clear command line (if in visual mode)
let @z=&so         " save scrolloff in register z
:set so=0 no scb   " set scrolloff to 0 and clear scrollbind
:bo vs             " split window vertically, new window on right
Ljzt               " jump to bottom of window + 1, scroll to top
:setl scb          " setlocal scrollbind in right window
<C-w>p             " jump to previous window
:setl scb          " setlocal scrollbind in left window
:let &so=@z        " restore scrolloff
```
The mapping clears `'scrollbind'` before manipulating the windows so 
that the position of the second window can be adjusted without scrolling 
the first window. Setting `'scrolloff'` to 0 allows the cursor to be 
positioned at the bottom of the screen (with command `L`).

### Problems
  * If the cursor is in the last line when the mapping is executed, 
the mapping fails because `j` cannot move the cursor down (and the 
remaining commands are not executed).
  * Register z is changed.
