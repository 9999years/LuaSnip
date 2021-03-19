# LuaSnip
Snippet Engine for Neovim written in Lua.

# Features
- Placeholders
- Text-Transformations using Lua functions
- Fast, small, simple

# Requirements
Neovim >= 0.5 (extmarks)

# Setup
- Install using eg. [vim-plug](https://github.com/junegunn/vim-plug)
- Add mappings
  - If there is no jump- or expandable Snippet, insert key:
```vim
imap <silent><expr> <Tab> luasnip#expand_or_jumpable() ? '<Plug>luasnip-expand-or-jump' : '<Tab>'
inoremap <silent> <S-Tab> <cmd>lua ls.jump(-1)<Cr>
```
  - Only try expanding the Snippet/jumping:
```vim
imap <silent><expr> <C-l> <cmd>lua require'luasnip'.expand_or_jump()<Cr>
inoremap <silent> <S-Tab> <cmd>lua require'luasnip'.jump(-1)<Cr>
```
- Add Snippets: Snippets have to be added to the `require'luasnip'.snippets`-table.
`Examples` contains more details. As of now, there is no separation between filetypes.

Inspired by [vsnip.vim](https://github.com/hrsh7th/vim-vsnip/)