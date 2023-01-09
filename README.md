<h1 align="center"> WSL Setup</h1>

## Table of Contents

- [Table of Contents](#table-of-contents)
- [What is WSL? :thinking:](#what-is-wsl-thinking)
- [Installation :computer:](#installation-computer)
- [Configuration :wrench:](#configuration-wrench)
  - [Windows Terminal](#windows-terminal)
  - [Better terminal with Zsh](#better-terminal-with-zsh)
  - [Build essentials, Git, Cmake, Clang \& Node.](#build-essentials-git-cmake-clang--node)

## What is WSL? :thinking:

The Windows Subsystem for Linux (WSL) is a feature of Windows that allows you to run native Linux command-line tools directly on Windows. It provides a Linux-compatible kernel interface developed by Microsoft, which allows you to use a wide range of Linux applications on Windows. With WSL, you can run shell scripts, install and use Linux command-line utilities, and even create and run your own custom scripts.

WSL is different from a traditional virtual machine in that it allows you to run Linux applications directly on the Windows kernel. This means that you can use Linux tools and utilities at the same level of performance as if they were running on a native Linux system.

## Installation :computer:

1. Open PowerShell as Administrator and run:

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

2. Open Microsoft Store and install the latest version of [WSL](https://www.microsoft.com/store/productId/9P9TQF7MRM4R).

3. Again in Microsoft Store, install your desired Linux distribution. I recommend [Ubuntu](https://www.microsoft.com/store/productId/9PDXGNCFSCZV).

4. Restart your computer.

5. Search for your desired Linux distribution in the Start menu and run it.

6. When installed, you will be prompted to create a new user account and password. This will be the user account you will use to log in to your Linux distribution.

## Configuration :wrench:

### Windows Terminal

1. Open Microsoft Store and install [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=fr-fr&gl=fr&rtc=1).

   This terminal is a modern, fast, efficient, powerful, and productive terminal application for users of command-line tools and shells like Command Prompt, PowerShell, and WSL.

2. Open Windows Terminal and click on the settings icon in the top right corner.

3. In the settings, click on the dropdown menu under "Default profile" and select your desired Linux distribution.

4. Don't forget to set Windows Terminal as your default terminal and you're good to go!

### Better terminal with Zsh

1. Install Zsh.

   ```bash
   # Zsh is a shell designed for interactive use, you can have plugins, themes, etc.
   sudo apt install zsh -y
   ```

2. Install Oh My Zsh.

   ```bash
    # Oh My Zsh is an open source, community-driven framework for managing your Zsh configuration.
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

3. Install Zsh plugins, you can find more plugins [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins).

   ```bash
   # Zsh plugins
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   # Add the following lines to your ~/.zshrc file:
   # plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
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

5. Nano

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

### Build essentials, Git, Cmake, Clang & Node.

1. Install build essentials.

   ```bash
   sudo apt install build-essential -y
   ```

2. Install Git.

   ```bash
   sudo apt install git -y
   ```

3. Install Cmake.

   ```bash
   sudo apt install cmake -y
   ```

4. Install Clang and Clang-format.

   ```bash
   # C compiler and formatter
   sudo apt install clang -y
   sudo apt install clang-format -y
   ```

5. Install Node and NPM.

   ```bash
   # Node and NPM
   sudo apt install nodejs -y
   sudo apt install npm -y
   ```

6. Update and upgrade.

   ```bash
   # Update and upgrade everything
   sudo apt update && sudo apt upgrade -y
   ```

You are now ready to start developing on WSL! :tada:

Made with :heart: by [@Jayllyz](https://github.com/Jayllyz)
