- [System Preferences](#system-preferences)
  - [Keyboard](#keyboard)
  - [Siri](#siri)
    - [Disable Voice Responses](#disable-voice-responses)
    - [Enable Type to Siri](#enable-type-to-siri)
  - [Dock](#dock)
- [Finder Preferences](#finder-preferences)
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

In **Finder** > **View**

- Select
  - Show Path Bar
  - Show Status Bar
 
![Finder View](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20View.gif)

In **Finder** > **Settings...** > **General**

In **Show these items on the desktop**:

- Enable
  - Hard disks

In **New Finder windows show**:

- Change
  - Downloads
    - You will have to select **Other...** and then select **Downloads** from the directory selector

![Finder General Settings](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Settings%20General.png)

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

In **Finder** > **Settings...** > **Advanced**

- Enable
  - Show all filename extensions

![Finder Advanced Settings](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Advanced%20Settings.png)

In **Finder** > **View** > **Customize Toolbar...**

Click and drag **Airdrop** to the **Toolbar** section of the **Finder** window

![Finder Airdrop](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Airdrop.gif)

This will allow you to highlight a file, then click the **Airdrop** icon in the **Finder** **Toolbar** to bring up an **Airdrop** dialog

![Finder Airdrop Demo](https://github.com/jim-ecker/NewMacSetup/blob/main/images/Finder%20Airdrop%20Demo.gif)

This is a much better way to **Airdrop** than doing it through the **Finder** **Sidebar**

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
