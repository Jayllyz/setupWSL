# setupWSL

![GitHub last commit (by committer)](https://img.shields.io/github/last-commit/jayllyz/setupWSL)
[![Super-Linter](https://github.com/jayllyz/setupWSL/actions/workflows/lint.yml/badge.svg)](https://github.com/marketplace/actions/super-linter)

- [setupWSL](#setupwsl)
  - [What is WSL? :thinking:](#what-is-wsl-thinking)
  - [Installation :computer:](#installation-computer)
  - [Configuration :wrench:](#configuration-wrench)
    - [Terminal](#terminal)
    - [Better terminal with Zsh](#better-terminal-with-zsh)
    - [Configuration](#configuration)
  - [Useful Tools and Informations](#useful-tools-and-informations)
  - [Thank you for reading! :sparkles:](#thank-you-for-reading-sparkles)

## What is WSL? :thinking:

The Windows Subsystem for Linux (WSL) is a feature of Windows that allows you to run native Linux command-line tools directly on Windows. It provides a Linux-compatible kernel interface developed by Microsoft, which allows you to use Linux applications on Windows.

This means that you can use Linux tools and utilities at the same level of performance as if they were running on a native Linux system, which is way better than using a virtual machine.

learn more [here](https://learn.microsoft.com/en-us/windows/wsl/about). :book:

## Installation :computer:

1. Open PowerShell as Administrator and run:

   - Default distribution is Ubuntu if you want another one use : `wsl --install -d <Distribution name>`
   - To see all available distribution use : `wsl --list --online`

   ```powershell
   wsl --install
   ```

     > ℹ️ Later you can update wsl in Microsoft store or by using `wsl --update` in powershell/cmd.

2. Restart your computer.

3. Search the distribution you have chosen in the Start menu and run it.

4. When installed, you will be prompted to create a new user account and password. This will be the user account you will use to log in to your Linux distribution.

## Configuration :wrench:

### Terminal

   I recommend using [Windows Terminal](https://aka.ms/terminal) or [WezTerm](https://wezfurlong.org/wezterm/), they are both great and have a lot of features to enhance your development experience.

   Recommend to use a [Nerd Fonts](https://www.nerdfonts.com/font-downloads) for icons support (JetBrains Mono is a good choice).

### Better terminal with Zsh

1. Install [Zsh](https://zsh.sourceforge.io/) & [cURL](https://curl.se/).

   ```bash
   # Zsh is a shell designed for interactive use, you can have plugins, themes, etc.
   sudo apt update && sudo apt upgrade -y
   sudo apt install zsh curl -y
   ```

2. Install [Oh My Zsh](https://ohmyz.sh/).

   ```bash
   # Oh My Zsh is an open source, community-driven framework for managing your Zsh configuration.
   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

3. Install Zsh plugins, you can find more plugins [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins).

   ```bash
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   ```

   Then add the following line to your `~/.zshrc file` :

   ```bash
   plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
   ```

4. *(optional)* Install [starship](https://starship.rs/).

   ```bash
   # Starship is a minimal, fast, and customizable prompt
   curl -fsSL https://starship.rs/install.sh | bash
   ```

   Then add the following line at the end of your `~/.zshrc` file :

   ```bash
   eval "$(starship init zsh)"
   ```

   Then you need to set your Zsh theme to an empty string in your `~/.zshrc` file :

   ```bash
   ZSH_THEME=""
   ```

   For more information about starship, refer to the [starship documentation](https://starship.rs/).

5. [Nano](https://www.nano-editor.org/) configuration.
   > Configuring Nano is optional, you can use another editor like Vim, Emacs, if you prefer.

   ```bash
   nano ~/.nanorc

   # Add this in the file :
   set atblanks
   set mouse
   set cutfromcursor
   set softwrap
   set tabsize 4
   set tabstospaces
   include "/usr/share/nano/*.nanorc"
   set speller "aspell -x -c"
   set constantshow
   set linenumbers
   set casesensitive
   set historylog
   set positionlog
   set smarthome
   set zap
   set autoindent
   bind ^C copy main # CTRC+C - Copy
   bind ^V paste all # CTRL+V - Past
   bind ^S savefile main # CTRL+S - Save
   ```

### Configuration

1. Install build essential. (gcc, g++, make, must have for development)

   ```bash
   sudo apt install build-essential -y
   ```

2. Install Git.

   ```bash
   sudo apt install git -y
   git config --global user.email 'your email'
   git config --global user.name 'your name'
   ```

3. Install [Docker Desktop](https://docs.docker.com/desktop/wsl/)

   > Docker Desktop uses the dynamic memory allocation feature in WSL 2 to optimize resource consumption.<br>
   > For more information, refer to the [Working with Docker & WSL documentation](https://docs.docker.com/desktop/wsl/).

4. Tool versioning.

   > Managing version of tools is usefull for development, my favorite tool for this is [proto](https://moonrepo.dev/proto). <br>
   >
   > If you only need to manage Node.js version, you can use [fnm](https://github.com/Schniz/fnm).

   ```bash
   # Requirements
   sudo apt install unzip gzip xz-utils -y

   curl -fsSL https://moonrepo.dev/install/proto.sh | bash

   proto setup

   # Install what you need :
   proto install node lts
   proto install python 
   ```

   You can find more information about proto [here](https://moonrepo.dev/proto).

5. Update, upgrade and clean package list.

   ```bash
   sudo apt update && sudo apt upgrade -y && sudo apt autoremove
   ```

## Useful Tools and Informations

> [!NOTE]
> There are numerous useful tools you can install to enhance your experience on Linux and WSL [link](more.md). <br>
> Microsoft has also created a guide to help you maximize the benefits of WSL if you use VS Code [link](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode). <br>
>
> When working with WSL, always clone or create your projects inside the Linux file system, <br> otherwise performance may significantly decrease, and certain features might not work properly (e.g: hot reloading).<br>
> For more information, refer to the [Docker best practices documentation](https://docs.docker.com/desktop/wsl/best-practices/).

## Thank you for reading! :sparkles:

**[`^ back to top ^`](#setupwsl)**

You are now ready to start developing on WSL! :tada:

Made with :heart: by [@Jayllyz](https://github.com/Jayllyz)
