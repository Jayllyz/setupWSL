*Last update : 07/07/2023*

## Table of Contents

- [Table of Contents](#table-of-contents)
- [What is WSL? :thinking:](#what-is-wsl-thinking)
- [Installation :computer:](#installation-computer)
- [Configuration :wrench:](#configuration-wrench)
  - [Windows Terminal](#windows-terminal)
  - [Better terminal with Zsh](#better-terminal-with-zsh)
  - [Basic installation](#basic-installation)

## What is WSL? :thinking:

The Windows Subsystem for Linux (WSL) is a feature of Windows that allows you to run native Linux command-line tools directly on Windows. It provides a Linux-compatible kernel interface developed by Microsoft, which allows you to use Linux applications on Windows.

WSL is different from a traditional virtual machine in that it allows you to run Linux applications directly on the Windows kernel. This means that you can use Linux tools and utilities at the same level of performance as if they were running on a native Linux system.

learn more [here](https://learn.microsoft.com/en-us/windows/wsl/about). :book:

## Installation :computer:

1. Open PowerShell as Administrator and run:

```powershell
# Default distribution is Ubuntu if you want another one use : wsl --install -d <Distribution name>
# To see all available distribution use : wsl --list -online
wsl --install
```

2. Restart your computer.

3. Search the distribution you have chosen in the Start menu and run it.

4. When installed, you will be prompted to create a new user account and password. This will be the user account you will use to log in to your Linux distribution.

## Configuration :wrench:

### Windows Terminal

1. Open Microsoft Store and install [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=fr-fr&gl=fr&rtc=1).

   > This terminal is a modern, fast, efficient, powerful, and productive terminal application for users of command-line tools and shells like Command Prompt, PowerShell, and WSL.

2. Open Windows Terminal and click on the settings icon in the top right corner.

3. In the settings, click on the dropdown menu under "Default profile" and select your desired Linux distribution.

4. Don't forget to set Windows Terminal as your default terminal and you're good to go!

### Better terminal with Zsh

1. Install [ZSH](https://zsh.sourceforge.io/).

```bash
# Zsh is a shell designed for interactive use, you can have plugins, themes, etc.
sudo apt install zsh -y
```

2. Install [Oh My Zsh](https://ohmyz.sh/).

```bash
# Oh My Zsh is an open source, community-driven framework for managing your Zsh configuration.
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

3. Install Zsh plugins, you can find more plugins [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins).

```bash
# Zsh plugins
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# Add the following line to your ~/.zshrc file:
# plugins=(git sudo docker npm vscode zsh-autosuggestions zsh-syntax-highlighting)
```

4. Install [Powerlevel10k](https://github.com/romkatv/powerlevel10k), if you want to use another theme, you can find more themes [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes).

```bash
# Powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
# Set ZSH_THEME="powerlevel10k/powerlevel10k" in ~/.zshrc.
# exec zsh
# p10k configure
```

5. [Nano](https://www.nano-editor.org/) configuration.

```bash
# Nano is a text editor for Unix-like operating systems.
sudo apt install nano -y

nano ~/.nanorc
# Put this in the file:

set atblanks
set mouse
set cutfromcursor
set softwrap
set suspend
set tabsize 4
set tabstospaces
include "/usr/share/nano/*.nanorc"
set speller "aspell -x -c"
set constantshow
set linenumbers
set casesensitive
set historylog
set positionlog
set zap
set autoindent
bind ^C copy main # CTRC+C - Copy
bind ^V paste all # CTRL+V - Past
bind ^S savefile main # CTRL+S - Save
```

### Basic installation

1. Install build essential.

```bash
sudo apt install build-essential -y
```

2. Install Git.

```bash
sudo apt install git -y
```

3. Install [Docker Desktop](https://docs.docker.com/desktop/wsl/).

   > Docker Desktop uses the dynamic memory allocation feature in WSL 2 to improve the resource consumption.

4. Install Node and NPM (or [pnpm](https://pnpm.io/installation)).

```bash
# Node and NPM
sudo apt install nodejs npm -y
```

5. Update and upgrade package list.

```bash
# Update and upgrade everything
sudo apt update && sudo apt upgrade -y
```

You are now ready to start developing on WSL! :tada:

If your favorite IDE is VSCode, you can find a tutorial [here](https://code.visualstudio.com/docs/remote/wsl).

Made with :heart: by [@Jayllyz](https://github.com/Jayllyz)
