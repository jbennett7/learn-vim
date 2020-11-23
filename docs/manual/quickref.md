# Left-right motion

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
