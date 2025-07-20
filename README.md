- [System Preferences](#system-preferences)
  - [Keyboard](#keyboard)
  - [Siri](#siri)
    - [Disable Voice Responses](#disable-voice-responses)
    - [Enable Type to Siri](#enable-type-to-siri)
  - [Dock](#dock)
- [Finder Preferences](#finder-preferences)
  - [View](https://github.com/jim-ecker/NewMacSetup/tree/main#view)
  - [Finder Settings](https://github.com/jim-ecker/NewMacSetup/tree/main#finder-settings)
    - [General](https://github.com/jim-ecker/NewMacSetup/tree/main#general)
    - [Sidebar](https://github.com/jim-ecker/NewMacSetup/tree/main#sidebar)
    - [Advanced](https://github.com/jim-ecker/NewMacSetup/tree/main#advanced)
- [Homebrew](#homebrew)
- [iTerm](#iterm)
  * [Oh-My-ZSH](#oh-my-zsh)
    + [Oh My ZSH Plugins](#oh-my-zsh-plugins)
      - [zsh-autosuggestions](#-zsh-autosuggestions--https---githubcom-zsh-users-zsh-autosuggestions-)
      - [zsh-syntax-highlighting](#-zsh-syntax-highlighting--https---githubcom-zsh-users-zsh-syntax-highlighting-)
      - [powerlevel10k](#-powerlevel10k--https---githubcom-romkatv-powerlevel10k-)
  * [iTerm Preferences](#iterm-preferences)
- [Apps](#apps)
  * [eza](#eza)
  * [bat](#bat)
  * [Midnight Commander](#midnight-commander)
 
# System Preferences

## Keyboard

In **System Preferences** > **Keyboard**, in the **Text Input** section, click the **Edit...** button

- Disable
  - Correct spelling automatically
  - Capitalize words automatically
  - Add period with double-space
 
![Keyboard Input Settings](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Keyboard%20Input%20Settings.png)

## Siri

### Disable Voice Responses

In **System Preferences** > **Siri & Spotlight**, click the **Siri Responses...** button

- Disable
  - Voice Feedback
 
![Siri Voice Feedback](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Siri%20Voice%20Feedback.png)

### Enable **Type to Siri**

In **System Preferences** > **Accessibility**, in the **General** section, click **Siri**

- Enable
  - Type to Siri
 
![Type to Siri](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Type%20to%20Siri.png)

## Dock

In **System Preferences** > **Desktop & Dock**

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

# iTerm

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
echo "source $(brew --prefix)/opt/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc
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
vim ~/.config/ghostty/config
```

Paste this configuration:

```ini
font-family = MesloLGS Nerd Font Mono
font-size = 19
background-opacity = 0.9
theme = Argonaut

# Fix HOME and END keys
key home = "\x1b[H"
key end  = "\x1b[F"
```

Save and restart Ghostty.

---

### 4. Fix HOME and END Keys in Zsh/Vim

Verify the keybindings:

```bash
bindkey | grep '\[H'
```

If you see this:
```
"^[H" run-help
```

Then HOME is mapped to `run-help`. You can test by typing a command and pressing `Alt+h` to get help.

---

### 5. Powerlevel10k Zsh Prompt

Install Powerlevel10k with Oh My Zsh:

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

In `~/.zshrc`, set:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Then reload:

```bash
source ~/.zshrc
```

---

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

# Modern Neovim Configuration (Ghostty + Powerlevel10k + Nerd Font)

This is a complete, modern Neovim setup tailored for:

- GPU-accelerated terminal: **Ghostty**
- Nerd Font icon support
- Powerlevel10k prompt
- Lua-based plugin configuration via **Lazy.nvim**
- Gruvbox theme, Telescope, Tree-sitter, LSP, and file explorer

---

## Features Included

- [x] Lazy.nvim plugin manager
- [x] Gruvbox color theme with truecolor
- [x] Telescope fuzzy finder (`<leader>ff`, `<leader>fg`, etc.)
- [x] Treesitter syntax highlighting
- [x] Built-in LSP with Mason (Lua, Bash, Python)
- [x] Auto-completion with `nvim-cmp`
- [x] Statusline with `lualine.nvim`
- [x] Git status via `gitsigns.nvim`
- [x] Nerd Font + Web Dev Icons
- [x] Modern file explorer with `nvim-tree.lua` (`<leader>e`)

---

## File Structure

Your config lives in:

```
~/.config/nvim/
├── init.lua
└── lua/
    └── core/
        ├── options.lua
        ├── keymaps.lua
        ├── plugins.lua
        └── lsp.lua
```

---

## Key Bindings

| Key Combo      | Action               |
|----------------|----------------------|
| `<leader>ff`   | Find files           |
| `<leader>fg`   | Live grep            |
| `<leader>fb`   | List buffers         |
| `<leader>fh`   | Help tags            |
| `<leader>e`    | Toggle file explorer |

(`leader` is set to **space**)

---

## Setup Notes

- **Leader key** is set at the top of your config:
  ```lua
  vim.g.mapleader = " "
  ```
- **netrw is disabled** to avoid conflict with `nvim-tree`:
  ```lua
  vim.g.loaded_netrw = 1
  vim.g.loaded_netrwPlugin = 1
  ```
- **Auto-launch file tree** when starting Neovim in a folder:
  ```lua
  if vim.fn.argc() == 1 and vim.fn.isdirectory(vim.fn.argv(0)) == 1 then
    vim.cmd.cd(vim.fn.argv(0))
    require("nvim-tree.api").tree.open()
  end
  ```

---

## Tips

- Run `:Lazy` to manage plugins
- Run `:Mason` to install/manage LSPs
- Use `:map <leader>` to list active leader keymaps
- If key mappings don’t work, check for null bytes (`^@`) with `nvim -b`

---

Happy hacking in Neovim + Ghostty!
