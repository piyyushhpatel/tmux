# Neovim (NVIM) Cheat Sheet

A quick reference guide for **Neovim** modes, movement, editing, windows, buffers, and key commands.

---

## 🚦 Neovim Modes

| Mode | Command | Description |
| :--- | :--- | :--- |
| **Normal** | `<Esc>` | Default mode for navigation and commands |
| **Insert** | `i` | Insert text before cursor |
| **Visual** | `v` | Highlight character-by-character |
| **Visual Line** | `V` | Highlight line-by-line |
| **Visual Block** | `<C-v>` | Highlight rectangular blocks of text |
| **Command-line** | `:` | Enter command prompt |
| **Terminal** | `:term` | Open built-in terminal mode |

---

## 🏃 Basic Movement (Normal Mode)

### Basic Navigation
* `h` - Left
* `j` - Down
* `k` - Up
* `l` - Right

### Word & Line Navigation
* `w` - Jump forward to start of next word
* `b` - Jump backward to start of previous word
* `e` - Jump forward to end of word
* `0` - Jump to beginning of line
* `^` - Jump to first non-blank character of line
* `$` - Jump to end of line

### File Navigation
* `gg` - Go to first line of file
* `G` - Go to last line of file
* `<number>G` or `:<number>` - Go to line `<number>`
* `%` - Move to matching bracket `()`, `{}`, `[]`

### Screen Scrolling
* `<C-u>` - Scroll Up half page
* `<C-d>` - Scroll Down half page
* `<C-b>` - Scroll Up full page
* `<C-f>` - Scroll Down full page
* `zz` - Center current line on screen

---

## ✏️ Entering Insert Mode

* `i` - Insert before cursor
* `I` - Insert at beginning of line
* `a` - Append after cursor
* `A` - Append at end of line
* `o` - Open new line **below** current line
* `O` - Open new line **above** current line
* `s` - Delete current character and enter Insert mode
* `S` - Clear current line and enter Insert mode

---

## ✂️ Editing: Delete, Copy & Paste

> **Vim Grammar:** `<operation> + <motion>` (e.g., `dw` = Delete Word)

| Operation | Command | Description |
| :--- | :--- | :--- |
| **Delete/Cut** | `x` | Delete single character |
| | `dw` | Delete to end of word |
| | `dd` | Delete (cut) current line |
| | `d$` or `D` | Delete from cursor to end of line |
| **Yank (Copy)**| `yy` or `Y` | Copy current line |
| | `yw` | Copy word |
| | `y$` | Copy to end of line |
| **Paste** | `p` | Paste after cursor/line |
| | `P` | Paste before cursor/line |
| **Change** | `cw` | Change word (delete & enter Insert mode) |
| | `cc` | Change entire line |
| **Undo / Redo**| `u` | Undo last action |
| | `<C-r>` | Redo last undone action |
| | `.` | Repeat last editing command |

---

## 🔍 Search & Replace

* `/text` - Search forward for `text`
* `?text` - Search backward for `text`
* `n` - Jump to next search match
* `N` - Jump to previous search match
* `*` - Search for word under cursor (forward)
* `#` - Search for word under cursor (backward)
* `:nohlsearch` or `:noh` - Clear search highlighting

### Substitute Syntax
`:s/pattern/replace/flags`

* `:s/old/new/g` - Replace all occurrences on current line
* `:%s/old/new/g` - Replace all occurrences in entire file
* `:%s/old/new/gc` - Replace in file with confirmation prompt

---

## 📑 Buffers, Windows & Tabs

### Managing Buffers
* `:ls` or `:buffers` - List open buffers
* `:bnext` or `:bn` - Go to next buffer
* `:bprev` or `:bp` - Go to previous buffer
* `:b <number>` - Switch to buffer by number
* `:bd` - Delete (close) current buffer

### Splitting Windows
* `:split` or `:sp` - Split window horizontally
* `:vsplit` or `:vsp` - Split window vertically
* `<C-w>h / j / k / l` - Navigate to left/down/up/right window
* `<C-w>w` - Cycle through open windows
* `<C-w>q` - Close focused window
* `<C-w>=` - Make all windows equal size

### Tab Page Management
* `:tabnew` - Open a new tab
* `:tabnext` or `gt` - Go to next tab
* `:tabprev` or `gT` - Go to previous tab
* `:tabclose` - Close current tab

---

## ⚡ Built-in LSP & Treesitter Commands (NVIM Default/Common)

| Command / Shortcut | Description |
| :--- | :--- |
| `K` | Hover documentation for symbol under cursor |
| `gd` | Go to definition |
| `gD` | Go to declaration |
| `gi` | Go to implementation |
| `gr` | Find references |
| `<C-x><C-o>` | Trigger omni-completion in Insert mode |
| `[d` / `]d` | Jump to previous / next diagnostic warning or error |

---

## 💾 Saving & Exiting

* `:w` - Save (write) current file
* `:w filename` - Save as `filename`
* `:q` - Quit current window
* `:q!` - Quit without saving changes
* `:wq` or `:x` or `ZZ` - Save and quit
* `:qa` - Quit all open windows/buffers

---

## 🛠️ Configuration & lua Basics

Neovim uses Lua (`init.lua`) or Vimscript (`init.vim`) for configuration.

### Common `init.lua` Options

```lua
-- Essential Settings
vim.opt.number = true          -- Show line numbers
vim.opt.relativenumber = true  -- Show relative line numbers
vim.opt.tabstop = 4            -- Number of spaces per tab
vim.opt.shiftwidth = 4         -- Indent size
vim.opt.expandtab = true       -- Convert tabs to spaces
vim.opt.ignorecase = true      -- Case-insensitive search
vim.opt.smartcase = true       -- Case-sensitive if capital typed
vim.opt.termguicolors = true   -- Enable 24-bit RGB colors

-- Map Leader Key
vim.g.mapleader = " "          -- Set space as leader key

-- Custom Keybinding Example
vim.keymap.set("n", "<leader>pv", vim.cmd.Ex, { desc = "Open File Explorer" })
```
