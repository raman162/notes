# Vim Notes

## Registers

Registers are places in memory of vim that stores text.

`"r` access content of register named 'r'
`"rp` pastes the content of registed named 'r'
`:reg` will show all registers and their content

### The Unamed Register

Vim has an unamed register that is used everytime you yank,
delete, paste text.

### The Numbered Registers

Vim has a series of numbered registers that range from 0 - 9
the `0` reigster will have the content of the latest yank.
This means that `"0p` will always paste what you last yanked.

Registers `1-9` will have deleted text with `"1` being the newest
and `"9` being the oldest.

### Read Only Registers

Vim has read only registers too. The read-only registers are:
`.`, `%`, `:`, `#`

`".` stores the last inserted text.
`"%` has the current file path
`":` has the most recently executed command
`"#` is the alternate-file *Look at alternate file in vim*
