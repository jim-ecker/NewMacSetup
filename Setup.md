# Mambaforge

Install Mambaforge. Make sure you get the installer for Apple Silicon

[ Mambaforge Installer](https://github.com/conda-forge/miniforge#mambaforge)

The installer should be in your Downloads folder. You need to make it executable and then run it

```bash
cd ~/Downloads
sudo chmod +x <installer file name>.sh
./<installer file name>.sh
```

This will run the installer. It will ask you which directory you want to install it to. I like to install it to a hidden folder instead of the default so when it asks put in:

```
~/.mambaforge
```

Once it finishes it'll ask you if you want to run ```conda init```. Say yes then restart the your terminal

# Homebrew

You need a package manager.

Pull up your terminal:

\<command\> + \<space bar\> to bring up Spotlight Search and type in:

```
terminal.app  
```

then copy/paste this command:
  
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
