# ezmap.nvim
Set your keymaps with ease.

## Installation
Install via your plugin manager. e.g.
```bash
use 'tiagovla/ezmap'
```

## Usage
Use with ``keywords``
```lua
require'ezmap'.map({
    {mode = 'n', lhs = '<C-N>', rhs = '<cmd>bnext<cr>', opts={'noremap'}},
    {mode = 'n', lhs = '<C-P>', rhs = '<cmd>bprev<cr>', opts={'noremap=true'}}
})
```

Use with ``keywords`` and multiple options
```lua
require'ezmap'.map({
    {mode = 'n', lhs = '<C-N>', rhs = ':bnext<cr>', opts={'noremap', 'silent'}},
    {mode = 'n', lhs = '<C-P>', rhs = ':bprev<cr>', opts={noremap=true, silent=true}}
})
```

Use without ``keywords`` and with default options if none is provided
```lua
local telescope_mappings = {
    {'n', '<C-F>', "<nop>"},
    {'n', '<C-F>f', ":lua require('telescope.builtin').find_files()<cr>"},
    {'n', '<C-F>g', ":lua require('telescope.builtin').live_grep()<cr>"},
    {'n', '<C-F>b', ":lua require('telescope.builtin').buffers()<cr>"},
    {'n', '<C-F>h', ":lua require('telescope.builtin').help_tags()<cr>"}
}
require'ezmap'.map(telescope_mappings, {'noremap', 'silent'})
```

## API

### ezmap.map(mappings, default_opts)

### ezmap.map_buf(mappings, bufnr, default_opts)
