[Table of Contents](../README.md)
# Capture ex command output
You can use the `:redir` command to redirect the output of an ex command 
to a register and then paste the contents of the register into a Vim 
buffer.

For example:
```
:redir @a
:set all
:redir END
```
Now, register 'a' will have the output of the "set all" ex command. 
You can paste this into a Vim buffer, using `"ap`.

Here is an example that uses tab pages:
```
function! TabMessage(cmd)
  redir => message
  silent execute a:cmd
  redir END
  if empty(message)
    echoerr "no output"
  else
    " use "new" instead of "tabnew" below if you prefer split windows 
    " instead of tabs.
    tabnew
    setlocal buftype=nofile bufhidden=wipe noswapfile nobuflisted nomodified
    silent put=message
  endif
endfunction
command! -nargs=+ -complete=command TabMessage call TabMessage(<q-args>)
```
To use this:
```
:TabMessage highlight
```
Note that `:redir` can use a variable instead of a register, as shown 
above.

Note also that `:redir` will capture silenced messages as well. While 
this won't be problematic with most builtin commands that echo stuff that 
we are interested in, this is quite problematic when we execute a sequence 
several commands. Since version 7.4-2008, Vim provides an `execute()`
function that'll simplify things and avoid side-effects.
