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
