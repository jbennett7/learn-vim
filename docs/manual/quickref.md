# Quick reference guide

## Left-right motion

| Command | Multi Command | Description                                                                    |
|:-------:|:-------------:|--------------------------------------------------------------------------------|
|   `h`   |     `N h`     | left (also: `<C-H>`, or `<Left>` key)                                          |
|   `l`   |     `N l`     | right (also: `<Space>`, or `<Right>` key)                                      |
|   `0`   |      `0`      | to first character in the line (also: `<Home>` key)                            |
|   `^`   |      `^`      | to first non-blank character in the line                                       |
|   `$`   |     `N $`     | to the last character in the line (`N-1` lines lower) (also: `<End>` key)      |
|   `g0`  |      `g0`     | to first character in screen line (differes from `0` when lines wrap)          |
|   `g^`  |      `g^`     | to first non-blank character in screen line (differs from `^` when lines wrap) |
|   `g$`  |     `N g$`    | to last character in screen line (differs from `$` when lines wrap)            |
|   `gm`  |      `gm`     | to middle of the screen line                                                   |
|   `gM`  |      `gM`     | to middle of the line                                                          |
|  `bar`  |     `N \|`    | to column `N` (default: 1)                                                     |
|   `f`   |  `N f{char}`  | to the `N`th occurrence of `{char}` to the right                               |
|   `F`   |  `N F{char}`  | to the `N`th occurrence of `{char}` to the left                                |
|   `t`   |  `N t{char}`  | till before the `N`th occurrence of `{char}` to the right                      |
|   `T`   |  `N T{char}`  | till before the `N`th occurrence of `{char}` to the left                       |
|   `;`   |     `N ;`     | repeat the last `f`, `F`, `t`, or `T` `N` times                                |
|   `,`   |     `N ,`     | repeat the last `f`, `F`, `t`, or `T` `N` times in opposite direction          |

## Up-down motions

| Command | Multi Command | Description                                                                                   |
|:-------:|:-------------:|-----------------------------------------------------------------------------------------------|
|   `k`   |     `N k`     | up `N` lines (also: `<C-P>` and `<Up>`)                                                       |
|   `j`   |     `N j`     | down `N` lines (also: `<C-J>`, `<C-N>`, `<NL>`, and `<Down>`)                                 |
|   `-`   |     `N -`     | up `N` lines, on the first non-blank character                                                |
|   `+`   |     `N +`     | down `N` lines, on the first non-blank character (also: `<C-M>` and `<CR>`)                   |
|   `_`   |     `N _`     | down `N`-1 lines, on the first non-blank character                                            |
|   `G`   |     `N G`     | goto line `N` (default: last line), on the first non-blank character                          |
|   `gg`  |     `N gg`    | goto line `N` (default: first line), on the first non-blank character                         |
|   `N%`  |     `N %`     | goto line `N` percentage down in the file; `N` must be given, otherwise it is the `%` command |
|   `gk`  |     `N gk`    | up `N` screen lines (differs from "k" when line wraps)                                        |
|   `gj`  |     `N gj`    | down `N` screen lines (differs from "j" when line wraps)                                      |
