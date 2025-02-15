<!-- PROJECT LOGO -->
<br />
<p align="center">
  <img src="https://user-images.githubusercontent.com/6236123/194855268-2608742d-ccf2-4767-923e-2e4a99ac8642.png" alt="Lesvim Nvim Screenshot" />
</p>

<p align="center">
  <h1 align="center"><a href="https://github.com/MiaadTeam/lesvim"><span align='center'>LESVIM</span> </a></h1>

<h3 align="center"> <code>LESVIM</code> hosts custom <a href="https://github.com/neovim/neovim"><span align='center'>Nvim</span> </a> configuration for all the platforms, focused on JavaScript, TypeScript, Rust and Lua</h3>
  <br />
<p align="center">
  <a href='https://github.com/MiaadTeam/lesvim/graphs/contributors'>
    <img alt="GitHub contributors" src="https://img.shields.io/github/contributors/MiaadTeam/lesvim?style=for-the-badge">
  </a>
  <a href='https://github.com/MiaadTeam/lesvim/issues'>
    <img alt="GitHub issues" src="https://img.shields.io/github/issues/MiaadTeam/lesvim?style=for-the-badge">
  </a>
</p>

<p align="center">
    <br />
    ·
    <a href="https://github.com/MiaadTeam/lesvim/issues">Report Bug</a>
    ·
    <a href="https://github.com/MiaadTeam/lesvim/issues">Request Feature</a>
  </p>
</p>

<details open="open"><summary>Table of Contents</summary>

- [About The Project](#about-the-project)
- [Getting Started](#getting-started)
  - [Recommendation](#recommendation) _Read this section for having best experience in this development environment_
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [_Wezterm_](#wezterm)
  - [_Vim or Neovim_](#vim-or-neovim)
  - [_LSP_](#lsp)
  - [_Copilot_](#copilot)
- [Plugins](#plugins) _Read this section to increase your mastery of this development environment_
- [Show your support](#show-your-support)

</details>

## About The Project

We want to create an awesome Development Environment's so a big part of this document is not about Neovim, we briefly talk about the terminal emulator and prompt and other terminal tools, that make possible the whole Development Life live in Terminal.

<img width="1680" alt="Screen Shot 1400-08-18 at 19 05 55" src="https://user-images.githubusercontent.com/6236123/194859831-711b6d8c-ac49-4de3-8cfe-f89b5950c16c.png">
<img width="1680" alt="Screen Shot 1400-08-18 at 23 11 12" src="https://user-images.githubusercontent.com/6236123/140993424-525cf9d2-4530-4412-9f4b-44d29cfa9964.png">

## Getting Started

### Recommendation

- We highly recommend using `Linux` or `Mac` as your operating system.

- [Using `Wezterm` as your default Terminal emulator.](https://github.com/wez/wezterm)

  It is a GPU-accelerated cross-platform terminal emulator and multiplexer written by @wez and implemented in Rust

  [It's my `wezterm.lua`](https://raw.githubusercontent.com/hemedani/dotfiles/main/wezterm/wezterm.lua), you should put it in `$HOME/.config/wezterm/wezterm.lua`:

- [Using `Fish SHELL` as your default Shell.](https://github.com/fish-shell/fish-shell)

  It is a user-friendly command-line shell.

  [It's my `config.fish`](https://raw.githubusercontent.com/hemedani/dotfiles/main/config.fish), you should put it in `$HOME/.config/fish/config.fish`:
  please note that you should be install [`exa`](https://github.com/ogham/exa) [`zoxide`](https://github.com/ajeetdsouza/zoxide) and [`starship`](https://github.com/starship/starship) to avoid throwing error for `functions` and `init` command in the config file

- [Using `starship` as your default Shell prompt.](https://github.com/starship/starship)

  It is the minimal, blazing-fast, and infinitely customizable prompt for any shell!

  [It's my `starship.toml`](https://raw.githubusercontent.com/hemedani/dotfiles/main/starship.toml), you should put it in `$HOME/.config/starship.toml`

- Using [`lazygit`](https://github.com/jesseduffield/lazygit) or [`GitUI`](https://github.com/extrawurst/gitui) for interacting with GIT it's is:

  Simple terminal UI for git commands,

  Blazing 💥 fast terminal-UI for git written in rust 🦀

  [It's my `GitUI` `VIM Like` keybinding](https://raw.githubusercontent.com/hemedani/dotfiles/main/gitui/key_bindings.ron), you should put it in `$HOME/.config/gitui/key_bindings.ron`

- Using [`exa`](https://github.com/ogham/exa) as a `ls` command in the terminal:

  A modern replacement for ‘ls’.

  I personally set `ll` alias to `exa --tree --level=2 -a --long --header --accessed` with this functions in `fish` shell:

  ```fish
  function ll --wraps=ls --wraps=exa --description 'List contents of directory using exa tree'
      exa --tree --level=2 -a --long --header --accessed --git $argv
  end
  ```

- Using [`zoxide`](https://github.com/ajeetdsouza/zoxide) as a `cd` command in terminal:

  A smarter cd command. Supports all major shells.

- Using [`RipGrep`](https://github.com/BurntSushi/ripgrep) as a replacement for `grep`:

  ripgrep recursively searches directories for a regex pattern while respecting your gitignore

- Using [`Bat`](https://github.com/sharkdp/bat) as a replacement for `cat`:

  A cat(1) clone with wings.

- Using [`fd`](https://github.com/sharkdp/fd) as a replacement for `find`:

  A simple, fast, and user-friendly alternative to 'find'

- Using [`gnu-sed`](https://www.gnu.org/software/sed/) sed (stream editor) is a non-interactive command-line text editor:

  sed is commonly used to filter text, i.e., it takes text input, performs some operation (or set of operations) on it, and outputs the modified text. sed is typically used for extracting part of a file using pattern matching or substituting multiple occurrences of a string within a file.

  MacOs:
  you need run `brew install gnu-sed`

you can read a little bit more about the above utils in [this article](https://medium.com/@hemedani/create-an-awesome-development-environment-with-the-terminal-in-mac-os-like-window-manager-2da824f03572) if you want's

### Prerequisites

- Install [Rust](https://www.rust-lang.org/tools/install)
- Install [Node JS](https://github.com/Schniz/fnm)
- Install [Deno](https://deno.land/#installation)
- Install [Neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim)
  - please install the nightly version of Neovim and install LuaJit.
- Install [`Cascadia Code`](https://github.com/microsoft/cascadia-code), [`Hack Nerd`](https://github.com/ryanoasis/nerd-fonts) and [`Adobe Arabic`](https://www.download-free-fonts.com/details/75203/adobe-arabic-regular) fonts
- Install Meslo Nerd Font patched
  - Manual Meslo font installation:
    1. Download these four ttf files:
       - [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
       - [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
       - [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
       - [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)
    2. Double-click on each file and click "Install". This will make `MesloLGS NF` font available to all
       applications on your system.
- If you decide to use the [`luffy`](https://github.com/windwp/windline.nvim#luffy) [`windline`](https://github.com/windwp/windline.nvim) config, install [`Fira Code iCursive S12`](https://github.com/windwp/windline.nvim/wiki/fonts/FiraCodeiCursiveS12-Regular.ttf).

- _Installing the Formatter_

  The major problem regarding the performance of IDE or IDE-Like is owing to the process of formatting documents. So we aim to speed up this process as much as possible.

  We are trying to format documents with utils written in rust `RUST`

  - Install [`dprint`](https://github.com/dprint/dprint) and set it to your `$PATH` (Pluggable and configurable code formatting platform written in Rust.)

  - It's my [`dprint.json`](https://raw.githubusercontent.com/hemedani/dotfiles/main/dprint/dprint.json) file, you should put it in `$HOME/.config/dotfiles/dprint/dprint.json`

  - Install [`stylua`](https://github.com/JohnnyMorganz/StyLua) and set it to your `$PATH` (An opinionated Lua code formatter written in rust)

  - It's my [`stylua.toml`](https://raw.githubusercontent.com/hemedani/dotfiles/main/stylua.toml) file, you should put it in `$HOME/.config/dotfiles/stylua.toml`

  - Install `prettier` globally: `npm i -g prettier` (Sorry for using this poorly performing package, however, we need it just for a few filetypes)

- _Install LSPs_

  `Deno` and `Rust` LSPs are installed and attached to the relevant buffer when you execute the `nvim` command on your proper root project;

  - For installing `tsserver` LSP just run: `npm install -g typescript typescript-language-server`. You can read the rest of its doc [here](https://github.com/neovim/nvim-lspconfig/blob/master/doc/server_configurations.md#tsserver)

  - For installing `sumneko_lua` LSP read [this doc](https://github.com/sumneko/lua-language-server/wiki/Build-and-Run) and [this doc](https://github.com/neovim/nvim-lspconfig/blob/master/doc/server_configurations.md#sumneko_lua)

    briefly i used this way for mac and linux:

    1. Install [ninja](https://github.com/ninja-build/ninja/wiki/Pre-built-Ninja-packages)
    2. Make sure you have C++17
    3. Execute these commands line by line in terminal
       ```fish-shell
       git clone https://github.com/sumneko/lua-language-server ~/.config/sumneko
       cd ~/.config/sumneko
       git submodule update --init --recursive
       cd 3rd/luamake
       ./compile/install.sh
       cd ../..
       ./3rd/luamake/luamake rebuild
       ```
       To be noticed your executables bin PATH of sumneko should be placed at `~/.config/sumneko/bin/lua-language-server`

### Installation

- _Copy or clone this repo to `.config/nvim` :_

  `git clone https://github.com/MiaadTeam/lesvim.git ~/.config/nvim`

- _Install plugins :_

  - `:PackerInstall`
  - `:PackerCompile`

    Please quit and reopen Neovim and execute `:PackerUpdate` and `:PackerCompile` again

- After launching Neovim, install these `TreeSitter` lib with `:TSInstall` :

  `:TSInstall comment css fish graphql javascript lua regex scss toml tsx vim http json dockerfile`

- And any other you want

## Usage

### _Wezterm_

- _Tabs and Pane's creation deletion_

  - `command + shift + N` or `super + shift + N` shortcut to create a new terminal window.
  - `command + ctrl + f` or `super + ctrl + f` toggle full screen windows.
  - `command + shift + L` or `super + shift + L` show launcher.
  - `command + t` or `super + t` shortcut to create a new terminal tab.
  - `command + w` or `super + w` shortcut to close the current terminal tab.
  - `command + '` or `super + '` shortcut to create a new vertical terminal split pane.
  - `command + /` or `super + /` shortcut to create new horizontal terminal split pane.
  - `command + x` or `super + x` shortcut to close the current terminal pane.
  - `command + z` or `super + z` shortcut to toggle the current terminal pane zoom.

- _Tabs navigation_

  - `command + ,` or `super + ,` goes to the right available tab.
  - `command + m` or `super + m` goes to the left available tab.
  - `command shift + T` or `super + shift + T` show tabs navigator menu.

- _Pane navigation_

  - `command + ctrl + h` or `super + ctrl + h` goes to the left available pane.
  - `command + ctrl + l` or `super + ctrl + l` goes to the right available pane.
  - `command + ctrl + k` or `super + ctrl + k` goes to the top available pane.
  - `command + ctrl + j` or `super + ctrl + j` goes to the bottom available pane.

- _Pane cycles_

  - `command + [` or `super + [` goes to the next available pane.
  - `command + ]` or `super + ]` goes to the prev available pane.

- _Pane resizing_

  - `command + shift + H` or `super + shift + H` increase right available pane to left.
  - `command + shift + L` or `super + shift + L` increase left available pane to right.
  - `command + shift + K` or `super + shift + K` increase the bottom available pane to the top.
  - `command + shift + J` or `super + shift + J` increase the top available pane to the bottom.

- _Searching_

  - `command + shift + F` or `super + shift + F` search for the string **"hash"** matches regardless of case.
  - `command + shift + space` or `super + shift + space` go to quick search tools.

You might have already noticed that all the shortcuts here begin with `command` or `super` key except the `ctrl + tab` which is switched between available tabs, so we try not to use `command` or `super` key in `vim` shortkey.

### _Vim or Neovim_

- Core:

  - Relative Neovim number is set to true.

    For instance, you can easily jump between lines with a glance by pressing `<number>j|k`.

  - As mentioned in the setup section, we manage plugins with [Packer](https://github.com/wbthomason/packer.nvim).

    A use-package inspired plugin manager for Neovim. Uses native packages, supports Luarocks dependencies, written in Lua, allows for expressive config

  - We used [`tokyonight`](https://github.com/folke/tokyonight.nvim) as a theme.

    🏙 A clean, dark Neovim theme written in Lua, with support for LSP, treesitter, and lots of plugins. It includes additional themes for Kitty, Alacrity, iTerm, and Fish

- Keybinding:

  If you press any key which has something bound to it and waits for a few seconds, `which-key` shows you an awesome hint for continuing press-related keys.

- Scrolling
  - Smooth scrolling for window movement commands (mappings optional): `<C-u>`, `<C-d>`, `<C-b>`, `<C-f>`, `<C-y>`, `<C-e>`, `zt`, `zz`, `zb`.

- Leader Key:

  The `leader` is often set to `space` key, so when you press `space` and wait for a few second `which-key` show all grouped and singleton of its binding keys. The following section briefly introduces a few of them:

  - `leader + e` toggle `Nvim Tree` explorer and immediately find the currently active buffer file in the tree.
  - `leader + /` comment just one line in `Normal and Visual` mode. (commenting keybinding has been explained below)
  - `leader + c` close current active buffer.
  - `ctrl + w` manipulate splited buffers in the current window.(create and modify the slipt window explained below)
  - `leader + f` open Telescope and find any file fuzzy in CWD.
  - `leader + h` jump to any word with the help of the HOP plugin (like sneak but much better)
  - `leader + q` quit nvim
  - `leader + t` show lsp action menu
  - `leader + r` format and regex things
    - `f` format current buffer
    - `r` display regex pattern in popup
    - `s` display regex pattern in split window
  - `leader + H` HTTP request things
    - `r` run the request under the cursor.
    - `p` preview the request cURL command.
    - `l` re-run the last request.
  - `leader + s` searching sections:
    - `b` searching branch and checkout to it.
    - `c` searching color schema and set it.
    - `C` searching command and execute it.
    - `f` find a file in this CWD.
    - `h` searching in all help.
    - `k` searching in all keymaps.
    - `M` finding in all MAN pages and open it
    - `p` searching all color schemes with preview
    - `R` searching in registers
    - `r` open recent files with the telescope
    - `t` search text in all files in the current CWD
    - `g` search and replace text with ripgrep in current CWD
    - `w` search and replace word under the cursor with ripgrep in current CWD
    - `l` search and replace text in active with ripgrep
  - `leader + b` buffer things:
    - `j` pick buffer by the first character
    - `f` find buffer in the telescope
    - `w` wipe buffer except for the current one
    - `r` close all buffer to the right
    - `l` close all buffer to left
    - `d` sort all buffer by directory
    - `n` sort all buffer by language
    - `t` sort all buffer by tabs
  - `leader + g` is for git stuff:
    - `b` checkout branch with the telescope
    - `c` checkout commit with the telescope
    - `C` checkout commit for the current file with the telescope
    - `j` jump to the next hunk
    - `k` jump to the previous hunk
    - `l` show git blame of current line
    - `o` open changed files in the telescope
    - `p` preview hunk
    - `r` reset current hunk
    - `R` reset the current buffer
    - `s` stage current hunk
    - `u` unstage hunk
  - `leader + l` for lsp things:
    - `a` show code action for the word is under the cursor if it is available
    - `d` show document diagnostics
    - `f` for format document with attached LSPs
    - `i` show configured and attached LSPs
    - `j` jump to the next diagnostic in the document
    - `k` jump to the previous diagnostic in the document
    - `q` select first actions in code actions (quick fixed)
    - `r` rename word with referenced with LSP (just like F2 in vscode)
    - `S` shows workspace symbols with the telescope
    - `s` show document symbols with the telescope
    - `t` find document or project troubles
    - `w` show workspace diagnostics
  - `leader + p` is for packer things:
    - `i` install the package if a new package is available
    - `c` compile packer and create `plugin/packer_compiled.lua` file
    - `s` sync packages with git repos
    - `u` update packages
    - `r` clean unused package
    - `S` packer status
  - `leader + z` for spell stuff:
    - `p` a special command that fixed a spell and jumps to the next misspelled word
    - `t` toggle spell checker to on and off
  - `leader + m` for markdown tools
    - `p` start/stop the live server to preview the current markdown file in the default browser
    - `t` preview markdown directly in a modal window in the terminal

- `Insert MODE` keybinds:

  press `jk | kj` in either Insert or Visual mode to enter Normal mode (Can be changed in /lua/keymap/escape.lua)

### _LSP_

- Press `gd` to jump to the definition word under the cursor.
- Press `gi` to jump to the implementation word under the cursor.
- Press `gr` to show where this word is referenced and used.
- Press `K` (CAPITAL K or `shift + k`) to show declarations of the word under the cursor.
- Press `ctrl + k` to show the signature of the word is available.
- Press `[d` to jump to the next diagnostic of the opened buffers.
- Press `]d` to jump to the previous diagnostic of the opened buffers.

### _Copilot_

- to setup `copilot` just enter `: Copilot setup` in the command line. everything should work fine if you have an invite to [GitHub Copilot](https://copilot.github.com) project.
- to accept it suggest just press `<C-j>` or `ctrl + j`.

## Plugins

_We tried to use Lua plugins as much as possible_
<br />
Some of the plugins have a unique configuration, some of them just copied configuration from its readme file, and some others we want's to add the best config we can piece by piece in the future

##### So We use this plugins:

- [`packer`](https://github.com/wbthomason/packer.nvim) for manage plugins:

  A use-package inspired plugin manager for Neovim. Uses native packages, supports Luarocks dependencies, written in Lua, allows for expressive config

- [`plenary`](https://github.com/nvim-lua/plenary.nvim) as dependencies for many plugins and Lua utils:

  plenary: full; complete; entire; absolute; unqualified. All the Lua functions I don't want to write twice.

- [`popup`](https://github.com/nvim-lua/popup.nvim) as a Popup tools :

  [WIP] An implementation of the Popup API from vim in Neovim. Hope to upstream when complete

- [`windline`](https://github.com/windwp/windline.nvim) for the status line:

  Animation status line, floating window status line. Using **lua + luv** would make some wind.

- [`Telescope`](https://github.com/nvim-telescope/telescope.nvim) as a finder modal:

  Find, Filter, Preview, Pick. All Lua, all the time.

- [`which-key.nvim`](https://github.com/folke/which-key.nvim) for amazing keybinding:

  💥 Create key bindings that stick. WhichKey is a Lua plugin for Neovim 0.5 that displays a popup with possible keybindings of the command you started typing.

- [`alpha-nvim`](https://github.com/goolord/alpha-nvim) for Dashboard like things:

  a Lua powered greeter like vim-startify / dashboard-nvim

- [`format.nvim`](https://github.com/lukas-reineke/format.nvim) for formatting document:

  Neovim Lua plugin to format the current buffer with external executables

- [`fugitive`](https://github.com/tpope/vim-fugitive) as a git ui for vim:

  fugitive.vim: A Git wrapper so awesome, it should be illegal

- [`nvim-cursorline`](https://github.com/yamatsum/nvim-cursorline) for the highlighted word:

  A plugin for neovim that highlights cursor words and lines

- [`renamer`](https://github.com/filipdutescu/renamer.nvim) for search and rename a variable|method and etc:

  VS Code-like renaming UI for Neovim, written in Lua.

- [`nvim-spectre`](https://github.com/windwp/nvim-spectre) for search and with ripgrep:

  Find the enemy and replace them with dark power.

- [`bracey`](https://github.com/turbio/bracey.vim) for HTTP live server:

  live edit HTML, CSS, and javascript in vim

- [`markdown-preview`](https://github.com/iamcco/markdown-preview.nvim) for preview markdown in browser:

  markdown preview plugin for (neo)vim

- [`nvim-ts-autotag`](https://github.com/windwp/nvim-ts-autotag) for close and rename HTML tags:

  Use treesitter to auto-close and auto-rename HTML tag

- [`vim-surround`](https://github.com/tpope/vim-surround) for manage word inside parentheses/quotes/XML-tags etc :

  surround.vim: Delete/change/add parentheses/quotes/XML-tags/much more with ease

- [`hop.nvim`](https://github.com/phaazon/hop.nvim) for motion beetween words:

  Neovim motions on speed!

- [`nvim-ts-rainbow`](https://github.com/p00f/nvim-ts-rainbow) for coloring matches parentheses/braces and etc in variety of rainbow color:

  Rainbow parentheses for neovim using tree-sitter. Also at https://sr.ht/~p00f/nvim-ts-rainbow

- [`alpha-nvim`](https://github.com/goolord/alpha-nvim) for greeter page:

  a lua powered greeter like vim-startify / dashboard-nvim

- [`indent-blankline.nvim`](https://github.com/lukas-reineke/indent-blankline.nvim) for coloring indent blankline:

  Indent guides for Neovim

- [`winshift.nvim`](https://github.com/sindrets/winshift.nvim) for managing Windows:

  Rearrange your windows with ease.

- [`gitsigns.nvim`](https://github.com/lewis6991/gitsigns.nvim) for git integration:

  Git integration for buffers

- [`nvim-treesitter`](https://github.com/nvim-treesitter/nvim-treesitter) Highlight, edit, and navigate code using a fast incremental parsing library:

  Nvim Treesitter configurations and abstraction layer

- [`nvim-treesitter-textobjects`](https://github.com/nvim-treesitter/nvim-treesitter-textobjects) Additional textobjects for treesitter:

  Syntax aware text-objects, select, move, swap, and peek support.

- [`nvim-treesitter-context`](https://github.com/romgrk/nvim-treesitter-context) Show code context in the above:

  Lightweight alternative to context.vim implemented with nvim-treesitter.

- [`nvim-lspconfig`](https://github.com/neovim/nvim-lspconfig) Collection of configurations for built-in LSP client:

  Quickstart configurations for the Nvim LSP client

- [`lspkind-nvim`](https://github.com/onsails/lspkind-nvim) Pictograms for built-in LSP client:

  vscode-like pictograms for neovim LSP completion items

- [`lspsaga.nvim`](https://github.com/glepnir/lspsaga.nvim) a lsp plugin:

  A light-weight LSP plugin based on neovim built-in LSP with highly a performant UI.

- [`trouble.nvim`](https://github.com/folke/trouble.nvim) a diagnostics tools:

  🚦 A pretty diagnostics, references, telescope results, quick-fix and location list to help you solve all the trouble your code is causing.

- [`nvim-cmp`](https://github.com/hrsh7th/nvim-cmp) Completion plugin :

  A completion plugin for neovim coded in Lua.

- [`cmp-nvim-lsp`](https://github.com/hrsh7th/cmp-nvim-lsp) Completion plugin for LSP:

  nvim-cmp source for neovim builtin LSP client

- [`cmp-buffer`](https://github.com/hrsh7th/cmp-buffer) Completion plugin for buffer:

  nvim-cmp source for buffer words

- [`cmp-path`](https://github.com/hrsh7th/cmp-path) Completion plugin for PATH:

  nvim-cmp source for path

- [`cmp-cmdline`](https://github.com/hrsh7th/cmp-cmdline) Completion plugin for command-line:

  nvim-cmp source for vim's cmdline

- [`nvim-snippy`](https://github.com/dcampos/nvim-snippy) for handling Snippets:

  Snippet plugin for Neovim

- [`cmp-snippy`](https://github.com/dcampos/cmp-snippy) for handling nvim-snippy in nvim-cmp:

  nvim-snippy completion source for nvim-cmp.

- [`registers.nvim`](https://github.com/tversteeg/registers.nvim) for handling vim registers:

  📑 Neovim plugin to preview the contents of the registers

- [`nvim-autopairs`](https://github.com/windwp/nvim-autopairs) for handling autopairs:

  autopairs for neovim written by lua

- [`nvim-toggleterm.lua`](https://github.com/akinsho/nvim-toggleterm.lua) for managing multiple terminal:

  A neovim lua plugin to help easily manage multiple terminal windows

- [`consolation.nvim`](https://github.com/pianocomposer321/consolation.nvim) a built-in neovim terminal:

  A general-purpose terminal wrapper and management plugin for neovim, written in lua

- [`nvim-code-action-menu`](https://github.com/weilbith/nvim-code-action-menu) a better code action:

  Pop-up menu for code actions to show meta-information and diff preview

- [`nvim-bufferline.lua`](https://github.com/akinsho/nvim-bufferline.lua) a buffer line to show nice data in the buffer header:

  A snazzy 💅 buffer line (with tabpage integration) for Neovim built using lua.

- [`nvim-tree.lua`](https://github.com/kyazdani42/nvim-tree.lua) a tree like file explorer:

  A file explorer tree for neovim written in Lua

- [`project.nvim`](https://github.com/ahmedkhalf/project.nvim) a project management:

  🗃️ project.nvim is an all-in-one neovim plugin written in Lua that provides superior project management.

- [`filetype.nvim`](https://github.com/nathom/filetype.nvim) speed up neovim startup:

  Easily speed up your neovim startup time!

- [`twilight.nvim`](https://github.com/folke/twilight.nvim) dims inactive portions of the code you're editing:

  🌅 Twilight is a Lua plugin for Neovim 0.5 that dims inactive portions of the code you're editing using TreeSitter.

- [`formatter.nvim`](https://github.com/mhartington/formatter.nvim) for format documents:

  A format runner for neovim, written in Lua.

- [`nvim-ts-context-commentstring`](https://github.com/JoosepAlviste/nvim-ts-context-commentstring) for correctly handling code commenting:

  Neovim treesitter plugin for setting the commentstring based on the cursor location in a file.

- [`Comment.nvim`](https://github.com/numToStr/Comment.nvim) for code commenting:

  🧠 💪 // Smart and powerful comment plugin for neovim. Supports treesitter, dot repeat, left-right/up-down motions, hooks, and more

- [`stabilize.nvim`](https://github.com/luukvbaal/stabilize.nvim) for fixing a little jump when a modal open/close from the bottom or top:

  Neovim plugin to stabilize buffer content on window open/close events.

- [`glow.nvim`](https://github.com/ellisonleao/glow.nvim) for preview markdown directly in neovim:

  A markdown preview directly in your neovim.

- [`rest.nvim`](https://github.com/NTBBloodbath/rest.nvim) for sending http request:

  A fast Neovim HTTP client written in Lua

- [`nvim-hlslens`](https://github.com/kevinhwang91/nvim-hlslens) for better search highlights in buffer:

  nvim-hlslens helps you better glance at matched information, and seamlessly jump between matched instances.

- [`rust-tools.nvim`](https://github.com/simrat39/rust-tools.nvim) rust development utils:

  Extra rust tools for writing applications in neovim using the native LSP. This plugin adds extra functionality to rust analyzer.

- [`crates.nvim`](https://github.com/saecki/crates.nvim) for getting information on cargo crates in toml files:

  A neovim plugin that helps manage crates.io dependencies

- [`nvim-dap`](https://github.com/mfussenegger/nvim-dap) a debugging tools:

  Debug Adapter Protocol client implementation for Neovim (>= 0.5)

- [`nvim-colorizer.lua`](https://github.com/norcalli/nvim-colorizer.lua) a color highlighter:

  A high-performance color highlighter for Neovim which has no external dependencies! Written in performant Luajit.

- [`nvim_context_v`](https://github.com/haringsrob/nvim_context_vt) extra virtual text:

  Shows the virtual text of the current context after functions, methods, statements, etc.

- [`vim-yin-yang`](https://github.com/pgdouyon/vim-yin-yang) low contrast theme:

  Yin-Yang is a black and white color scheme for Vim and is heavily inspired by preto and base16-grayscale.

- [`better-escape.nvim`](https://github.com/max397574/better-escape.nvim) for better escape with `jk` or `kj`:

  Escape from insert mode without delay when typing

- [`numb.nvim`](https://github.com/nacro90/numb.nvim) for peeking lines just when you intend :

  numb.nvim is a Neovim plugin that peeks lines of the buffer in a non-obtrusive way.

- [`nvim-regexplainer`](https://github.com/bennypowers/nvim-regexplainer) for display regex pattern :

  Describe the regexp under the cursor

- [`folke/noice.nvim`](https://github.com/folke/noice.nvim) for replaces the UI for `messages`, `cmdline` and the `popupmenu` :

  💥 Highly experimental plugin that completely replaces the UI for messages, cmdline and the popupmenu.

- [`copilot.vim`](https://github.com/github/copilot.vim) for AI code suggestion :

  GitHub Copilot is an AI pair programmer which suggests line completions and entire function bodies as you type.

## Show your support

Give a ⭐️ if this project helped you!

<!--
## License

This project is [AGPL--3.0 License](https://github.com/MiaadTeam/lesvim/blob/main/LICENSE) licensed. -->
