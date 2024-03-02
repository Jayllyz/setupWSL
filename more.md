# Useful tools

Thanks for using this guide, this part gives more useful tools and configurations.

## Packages

There are some packages that I use in my daily life, you can install them if you want.

### [Bat](https://github.com/sharkdp/bat)

Bat improves the `cat` command, it adds syntax highlighting and git integration.

```bash
sudo apt install bat -y
```

You can add theses aliases in your `~/.zshrc` file :

```bash
# bat
alias cat='batcat --style="header" --paging=never'
alias catn='batcat --pager "less -RF"'
alias batn='batcat --pager "less -RF"'
```

### [Fzf](https://github.com/junegunn/fzf)

Fzf is a command-line fuzzy finder, it's a very useful tool to find files, folders, and more.

```bash
sudo apt install fzf -y
```

You can add theses aliases in your `~/.zshrc` file :

```bash
# fzf
alias f='fzf'
alias ff='fzf -m'
alias fff='fzf -m --preview "batcat --style=header --color=always --line-range :500 {}"'
```

> [!WARNING]
> You need to install [Bat](#bat) to use the `fff` alias.

### [btop](https://github.com/aristocratos/btop)

btop is a resource monitor, it's a very useful tool to monitor your system, it's like htop but with a better UI and more features.

```bash
sudo apt install btop -y
```

You can add theses aliases in your `~/.zshrc` file :

```bash
# btop
alias top="btop --utf-force"
alias btop="btop --utf-force"
alias htop="btop --utf-force"
```

### [eza](https://github.com/eza-community/eza)

eza is a modern replacement for `ls`, it adds more features and a better UI.

```bash
sudo apt install eza -y
```

You can add theses aliases in your `~/.zshrc` file :

```bash
# eza
alias ls='eza -a --icons'                                               # ls
alias l='eza -lbF --git'                                                # list, size, type, git
alias ll="eza -1a --icons"                                              # list, 1 per line
alias lat="eza -lagh --tree --icons"                                    # list with info and tree
```

### [duf](https://github.com/muesli/duf)

duf is a modern replacement for `df -h`, it adds more features and a better UI.

```bash
sudo apt install duf -y
```

You can add theses aliases in your `~/.zshrc` file :

```bash
# duf
alias df='duf'                                                          # df
alias duf='duf -h -a --si'                                              # duf
```

> [!NOTE]
> You might need to do `unalias duf` before using the `duf` alias since it's already an alias by default.

### [nala](https://github.com/volitank/nala)

Nala is a modern replacement for apt, it adds more features and a better UI.
> [!NOTE]
> Outside of pretty formatting, the number 1 reason to use Nala over apt is parallel downloads.

```bash
sudo apt install nala -y
```

Good video about [nala](https://youtu.be/oroSkR4Nn_w?si=uk__FOcTip7LX9xh).

## More useful aliases

You can add theses aliases in your `~/.zshrc` file :

```bash
# cd
alias ..='cd ..'
alias ...='cd ../..'

# update
alias update='sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y'
# if you use nala
alias update='nala update && nala upgrade -y'

# network
alias ip='curl -s https://ipinfo.io/ip'
alias localip='ipconfig getifaddr en0'

# zsh
alias zshrc='nano ~/.zshrc'

# git
alias gs='git status'
alias ga='git add .'

# wheather
alias wheather='curl wttr.in'
```

## Ressources

- [Linux-Bash-Commands](https://github.com/trinib/Linux-Bash-Commands) - A list of useful Linux Bash commands.
- [awesome-zsh-plugins](https://github.com/unixorn/awesome-zsh-plugins) - A collection of ZSH frameworks, plugins & themes.
- [cheat.sh](https://github.com/chubin/cheat.sh) - The only cheat sheet you need.
- [awesome-console-services](https://github.com/chubin/awesome-console-services) - List of useful console services. (inactive but still useful)

Thank you for reading this part of the guide, I hope you found it useful and feel free to contribute to this guide by creating a pull request. :smile: 👍
