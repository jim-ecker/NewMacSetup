## Table of Contents

- [System Settings](#system-settings)
  - [Keyboard](#keyboard)
  - [Siri](#siri)
    - [Disable Voice Responses](#disable-voice-responses)
    - [Enable Type to Siri](#enable-type-to-siri)
  - [Dock](#dock)

- [Finder Preferences](#finder-preferences)
  - [View](#view)
  - [Finder Settings](#finder-settings)
    - [General](#general)
    - [Sidebar](#sidebar)
    - [Advanced](#advanced)

- [Homebrew](#homebrew)

- [Ghostty Terminal Setup](#ghostty-terminal-setup-with-powerlevel10k--nerd-font)
  - [Step-by-Step Setup](#-step-by-step-setup)
    - [Install Ghostty](#1-install-ghostty-macos)
    - [Install a Nerd Font](#2-install-a-nerd-font)
    - [Create a Ghostty Config File](#3-create-a-ghostty-config-file)
    - [Fix HOME and END Keys in Zsh/Vim](#4-fix-home-and-end-keys-in-zshvim)
    - [Inline Image Tools](#6-inline-image-tools)
    - [Debugging Tips](#7-debugging-tips)

- [iTerm (Alternative Terminal)](#iterm-good-alternative-what-i-used-to-use-as-my-main-terminal)
  - [Oh-My-ZSH](#oh-my-zsh)
    - [zsh-autosuggestions](#zsh-autosuggestions)
    - [zsh-syntax-highlighting](#zsh-syntax-highlighting)
    - [powerlevel10k](#powerlevel10k)
  - [iTerm Preferences](#iterm-preferences)

- [Apps](#apps)
  - [eza](#eza)
  - [bat](#bat)
  - [Midnight Commander](#midnight-commander)
  - [Zoxide](#zoxide)

- [Modern Neovim Setup (macOS)](#modern-neovim-setup-step-by-step-for-macos)
  - [Install Neovim](#1-install-neovim)
  - [Set Up Config Directory](#2-set-up-config-directory)
  - [Configure initlua](#3-configure-initlua)
  - [optionslua](#4-optionslua-basic-settings)
  - [keymapslua](#5-keymapslua-custom-shortcuts)
  - [pluginslua](#6-pluginslua-install-lazynvim-plugins)
  - [Enable Gruvbox Theme](#7-enable-gruvbox-theme)
  - [Launch Neovim](#8-launch-neovim)
  - [Verify Setup](#verify-setup)

# System Settings

## Keyboard

In **System Settings** > **Keyboard**, in the **Text Input** section, click the **Edit...** button

- Disable
  - Correct spelling automatically
  - Capitalize words automatically
  - Add period with double-space
 
![Keyboard Input Settings](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Keyboard%20Input%20Settings.png)

## Siri

### Disable Voice Responses

In **System Settings** > **Apple Intelligence & Siri**, click the **Siri Responses...** button

- Disable
  - Voice Feedback
 
![Siri Voice Feedback](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Siri%20Voice%20Feedback.png)

### Enable **Type to Siri**

In **System Settings** > **Apple Intelligence & Siri**, in the **Siri Requests** section

- Select
  - Listen For
    - Off
   
- Keyboard Shortcut
  - Select
    - Press Either Command Key Twice
      - press a cmd key twice and enable the text to Siri shortcut
 
![Type to Siri](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Type%20to%20Siri.png)

## Dock

In **System Settings** > **Desktop & Dock**

- Change
  - Minimize Windows Using
    - Scale Effect
- Enable
  - Automatically hide and show the Dock
- Disable
  - Show suggested and recent apps in Dock
 
![Dock Settings](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Dock%20Settings.png)

# Finder Preferences

## View

In **Finder** > **View**

- Select
  - Show Path Bar
  - Show Status Bar
 
![Finder View](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20View.gif)

In **Finder** > **View** > **Customize Toolbar...**

Click and drag **Airdrop** to the **Toolbar** section of the **Finder** window

![Finder Airdrop](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Airdrop.gif)

This will allow you to highlight a file, then click the **Airdrop** icon in the **Finder** **Toolbar** to bring up an **Airdrop** dialog

![Finder Airdrop Demo](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Airdrop%20Demo.gif)

This is a much better way to **Airdrop** than doing it through the **Finder** **Sidebar**

## Finder Settings

## General

In **Finder** > **Settings...** > **General**

In **Show these items on the desktop**:

- Enable
  - Hard disks

In **New Finder windows show**:

- Change
  - Downloads
    - You will have to select **Other...** and then select **Downloads** from the directory selector

![Finder General Settings](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Settings%20General.png)

## Sidebar

In **Finder** > **Settings...** > **Sidebar**

- Enable
  - In the **Favorites** section
    - your home folder
- Disable
  - In the **Favorites** section
    - Recents
  - In the **Tags** section
    - Recent Tags

![Finder Sidebar Settings](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Sidebar%20Settings.png)

## Advanced

In **Finder** > **Settings...** > **Advanced**

- Enable
  - Show all filename extensions

![Finder Advanced Settings](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Advanced%20Settings.png)

# Homebrew

You need a package manager.

Pull up your terminal:

\<command\> + \<space bar\> to bring up Spotlight Search and type in:

```
terminal.app  
```

then copy/paste this command:
  
```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Homebrew will tell you to use these commands to add it to your PATH but it's easy to miss so here they are

```zsh
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> $HOME/.zprofile

eval "$(/opt/homebrew/bin/brew shellenv)"
```

# Ghostty Terminal Setup (with Powerlevel10k + Nerd Font)

This guide walks you through configuring Ghostty with Nerd Fonts, Powerlevel10k, keybindings, and inline image support.

---

## ✅ Step-by-Step Setup

### 1. Install Ghostty (macOS)

Download Ghostty from the official site:

```bash
brew install --no-quarantine --cask ghostty
```

Or download the `.app` from: https://github.com/ghostty-org/ghostty

---

### 2. Install a Nerd Font

Powerlevel10k and dev icons need a patched Nerd Font:

```bash
brew tap homebrew/cask-fonts
brew install --cask font-meslo-lg-nerd-font
```

In Ghostty preferences:

- Set **Font Family** to: `MesloLGS Nerd Font Mono`

---

### 3. Create a Ghostty Config File

Create the file:

```bash
mkdir -p ~/.config/ghostty
vim ~/Library/Application\ Support/com.mitchellh.ghostty/config
```

Paste this configuration:

```ini
theme = Hardcore
shell-integration = zsh
font-family = "MesloLGS Nerd Font Mono"
font-size = 14

```

Save and restart Ghostty.

---

## Fix HOME and END Keys in Zsh/Vim

On macOS and some terminals (including Ghostty), the HOME and END keys may not work properly in Zsh or Vim. Here's how to fix them.

### 1. Check Current Bindings

Run this in your terminal:

```bash
bindkey | grep '\[H'
```

If you see:

```bash
"^[H" run-help
```

Then `HOME` is incorrectly mapped to Zsh’s `run-help`.

### 2. Remap Keys in `.zshrc`

Add these lines to your `~/.zshrc`:

```zsh
bindkey "\e[H" beginning-of-line
bindkey "\e[F" end-of-line
```

Then reload your shell:

```bash
source ~/.zshrc
```

### 3. Test It

- Type a command
- Press `HOME` → should jump to the beginning of the line
- Press `END`  → should jump to the end of the line

### Vim Note

In Vim, HOME and END typically just work, but if not, you can add these to your `.vimrc` or `init.vim`:

```vim
map <Esc>[H <Home>
map <Esc>[F <End>
```

### 6. Inline Image Tools

Ghostty supports **Kitty protocol** for inline images. Try:

```bash
brew install chafa viu
```

Render images:

```bash
chafa --symbols=block --colors=16 --size=$(tput cols)x$(tput lines) image.jpg
```

To test minimal color output:

```bash
chafa --symbols=ascii --dither=none --colors=2 image.jpg
```

Ghostty may render these as overlays rather than inline depending on protocol.

---

### 7. Debugging Tips

- If HOME/END do nothing: check `~/.config/ghostty/config` for typos or invalid escape codes.
- If colors don’t render correctly: verify Ghostty uses a theme with truecolor enabled.
- If images don't render inline: test with `viu` or `chafa` and make sure Kitty protocol is supported.

---



# iTerm (good alternative, what I used to use as my main terminal)

Install iTerm using Homebrew

```zsh
brew install --cask iterm2
```

At first its going to be boring like this

![New Install of iTerm](https://github.com/jim-ecker/NewMacSetup/blob/main/images/iterm_new.png "New Install of iTerm")

Let's make it look better

## Oh-My-ZSH

Install Oh My ZSH

```zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

When it's done you'll see something like this

![New Install of Oh My ZSH](https://github.com/jim-ecker/NewMacSetup/blob/main/images/ohmyzsh_install.png "New Install of Oh My ZSH")

### Oh My ZSH Plugins ###

Now we want to install some plugins

#### [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) ####

1. Clone this repository into `$ZSH_CUSTOM/plugins` (by default `~/.oh-my-zsh/custom/plugins`)

    ```zsh
    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    ```

2. Add the plugin to the list of plugins for Oh My Zsh to load (inside `~/.zshrc`):

    ```zsh
    plugins=( 
        # other plugins...
        zsh-autosuggestions
    )
    ```

3. Start a new terminal session.

#### [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) ####

1. Install via Homebrew

```zsh
brew install zsh-syntax-highlighting
```

2. To activate the syntax highlighting, add the following at the end of your `.zshrc`:

```zsh
  source /opt/homebrew/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```

#### [powerlevel10k](https://github.com/romkatv/powerlevel10k) ####

Install Powerlevel10k to customize the command line bar

```zsh
brew install powerlevel10k
echo "source $(brew --prefix)/share/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc
```
Restart your terminal. Once you do Powerlevel10k's installation wizard will start. Step through it to set up your customization

![Powerlevel10k Init](https://github.com/jim-ecker/NewMacSetup/blob/main/images/powerlevel10k_init.png "Powerlevel10k Init")

Once you're done you'll have a cool looking cli bar like this:

![Powerlevel10k bar](https://github.com/jim-ecker/NewMacSetup/blob/main/images/init_done.png "Powerlevel10k Bar")

## iTerm Preferences

1. Use Ligatures

**iTerm > Settings > Profiles >** ***Text***

checkmark *Use ligatures*

2. Color Scheme

**iTerm > Settings > Profiles >** ***Colors***

Click the *Color Presets...* dropdown and select *Solarized Dark*

3. Transparency

**iTerm > Settings > Profiles >** ***Window***

Set *Transparency* to 5

# Apps

## [eza](https://github.com/eza-community/eza)

---

**eza** is a modern, maintained replacement for the venerable file-listing command-line program `ls` that ships with Unix and Linux operating systems, giving it more features and better defaults.
It uses colours to distinguish file types and metadata.
It knows about symlinks, extended attributes, and Git.
And it’s **small**, **fast**, and just **one single binary**.

By deliberately making some decisions differently, eza attempts to be a more featureful, more user-friendly version of `ls`.

---
```zsh
brew install eza
```

Then alias ls to point to exa now. Add this to your `.zshrc` file:

```zsh
alias ls="eza --icons -lh"
```

add an alias to print the directory map as a tree with icons

```zsh
alias tree="eza --icons --tree"
```

## [bat](https://github.com/sharkdp/bat)

---

A *cat(1)* clone with syntax highlighting and Git integration.

*bat* allows you to *cat(1)* files with syntax highlighting and line numbering, which makes reading code on cli on the fly much easier

---

```zsh
brew install bat
```

I like to alias bat so that I can envoke it using "cat"

```zsh
alias cat="bat"
```

## [Midnight Commander](https://github.com/MidnightCommander/mc)

---

**Midnight Commander** allows you to manage files while making the most of
your screen and giving you a clear representation of the filesystem, yet
it's simple enough to be run over a telnet or ssh session.

---

```zsh
brew install midnight-commander
```

---

## [Zoxide](https://github.com/ajeetdsouza/zoxide)

zoxide is a smarter cd command, inspired by z and autojump.

It remembers which directories you use most frequently, so you can "jump" to them in just a few keystrokes.
zoxide works on all major shells.

---
```zsh
brew install zoxide
```
---

then alias zoxide to run when you use cd

```zsh
alias cd=z
```
## Modern Neovim Setup (Step-by-Step for macOS)

This guide walks you through installing and configuring Neovim with Lazy.nvim, Gruvbox, Treesitter, LSP, file explorer, and fuzzy finder — all tuned for use with Ghostty and Powerlevel10k.

---

### Step-by-Step Instructions

#### 1. Install Neovim

```bash
brew install neovim
```

Verify install:

```bash
nvim --version
```

---

#### 2. Set Up Config Directory

Create Neovim config folders:

```bash
mkdir -p ~/.config/nvim/lua/core
```

---

#### 3. Configure `init.lua`

Create `~/.config/nvim/init.lua` and paste:

```lua
require("core.options")
require("core.keymaps")
require("core.plugins")
```

---

#### 4. `options.lua`: Basic Settings

Create `~/.config/nvim/lua/core/options.lua`:

```lua
vim.opt.relativenumber = true
vim.opt.number = true
vim.opt.tabstop = 4
vim.opt.shiftwidth = 4
vim.opt.expandtab = true
vim.opt.termguicolors = true
vim.opt.mouse = "a"
vim.opt.clipboard = "unnamedplus"
vim.g.loaded_netrw = 1
vim.g.loaded_netrwPlugin = 1
```

---

#### 5. `keymaps.lua`: Custom Shortcuts

Create `~/.config/nvim/lua/core/keymaps.lua`:

```lua
vim.g.mapleader = " "
local keymap = vim.keymap.set

keymap("n", "<leader>ff", "<cmd>Telescope find_files<cr>", { desc = "Find Files" })
keymap("n", "<leader>fg", "<cmd>Telescope live_grep<cr>", { desc = "Live Grep" })
keymap("n", "<leader>fb", "<cmd>Telescope buffers<cr>", { desc = "Buffers" })
keymap("n", "<leader>fh", "<cmd>Telescope help_tags<cr>", { desc = "Help Tags" })
keymap("n", "<leader>e", "<cmd>NvimTreeToggle<CR>", { desc = "Toggle File Tree" })
```

---

#### 6. `plugins.lua`: Install Lazy.nvim Plugins

Create `~/.config/nvim/lua/core/plugins.lua`:

```lua
local lazy = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"
if not vim.loop.fs_stat(lazy) then
  vim.fn.system({ "git", "clone", "--filter=blob:none", "https://github.com/folke/lazy.nvim.git", lazy })
end
vim.opt.rtp:prepend(lazy)

require("lazy").setup({
  { "ellisonleao/gruvbox.nvim" },
  { "nvim-lualine/lualine.nvim" },
  { "nvim-tree/nvim-tree.lua" },
  { "nvim-telescope/telescope.nvim", dependencies = { "nvim-lua/plenary.nvim" } },
  { "nvim-treesitter/nvim-treesitter", build = ":TSUpdate" },
  { "neovim/nvim-lspconfig" },
  { "williamboman/mason.nvim" },
  { "williamboman/mason-lspconfig.nvim" },
  { "hrsh7th/nvim-cmp" },
  { "hrsh7th/cmp-nvim-lsp" },
  { "L3MON4D3/LuaSnip" },
  { "lewis6991/gitsigns.nvim" },
  { "nvim-tree/nvim-web-devicons" },
})
```

---

#### 7. Enable Gruvbox Theme

Add to `~/.config/nvim/init.lua`:

```lua
vim.cmd("colorscheme gruvbox")
vim.opt.background = "dark"
```

---

#### 8. Launch Neovim

Start Neovim:

```bash
nvim
```

Then run:

```vim
:Lazy sync
:Mason
```

Install your LSPs (e.g. `pyright`, `lua_ls`).

---

#### Verify Setup

- `<Space>e` → File tree
- `<Space>ff` → Fuzzy finder
- `:TSInstall all` → Treesitter parsers
- `:checkhealth` → Troubleshooting

---

