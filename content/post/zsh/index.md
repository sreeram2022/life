---
title: My Zsh
description: This is my zsh
slug: zsh
date: 2024-06-09 
image: 
categories:
    - Tech
tags:
    - Mac
    - linux
weight: 20       # You can add weight to some posts to override the default sorting (date descending)
---
## My Zsh Setup

Let’s talk about customizing the terminal on a Mac. By default, macOS comes with a basic terminal using zsh, which seems boring. However, with a bit of configuration, you can transform it into a powerful and visually appealing tool. For a long time, I didn’t realize the potential of zsh until I stumbled upon some YouTube tutorials that showcased how to enhance the terminal. 

### Key Enhancements

Almost all the tutorials pointed towards the same setup:

1. **Installing iTerm2 or kitty**: A more feature-rich terminal emulator.
2. **Oh My Zsh Framework**: A community-driven framework for managing `zsh` configurations.
3. **Powerlevel10k Theme**: A highly customizable prompt theme.
4. **Nerd Font**: I use JetBrains Mono for better glyph support.
5. **Configuring `.zshrc`**: Tailoring the terminal with auto-completions, aliases, and other settings.
6. **Transparency**: Making the terminal slightly transparent for a more charming look.

![Neofetch](zsh.png "My Zsh")

### Learning Vim

As I got more into making my terminal look cool, I figured I should learn vim to keep things consistent while coding and taking notes. At first, it felt pretty overwhelming, but after sticking with it, I realized that mastering vim actually helped me work way faster without needing to take my hands off the keyboard.

Some basic `vim` config I use include:

- **NERDTree**: Access with `F1`, toggle with `Ctrl+w`, or use the mouse.
- **Run Python Files**: Use `#!/usr/bin/env python3` at the beginning of a file and press `F2` to run, or use `:!` to execute commands.


### Terminal Multiplexing with Tmux

I also use `tmux` to manage multiple terminal sessions concurrently. It’s a powerful tool for running and switching between several tasks in parallel.

## Aliases

I've learned some basic bash scripting, which can significantly streamline terminal tasks. For example, you can automate running several commands with a single alias.

### Examples Aliases for `.zshrc`

Here's a glimpse of some abbreviations and aliases I've configured:

```sh
# Basic Aliases
alias ll='ls -la'               # List files with detailed info
alias g='git'                   # Shorten 'git' command
alias ..='cd ..'                # Move up one directory
alias ...='cd ../..'            # Move up two directories

# Useful Commands
alias c='clear'                # Clear the terminal screen
alias h='history'              # Show command history
alias py='python3'             # Use python3 for 'py'

# macOS Specific Commands
alias def='defaults'               # Access macOS defaults system
alias saytessa='say -V tessa'      # Use macOS TTS with the Tessa voice

alias editzsh='nvim ~/.zshrc' #Editign .zshrc from anywhere
alias vimrc='nvim ~/.vimrc' #Editign .vimrc from anywhere

alias gacp='f() { git add . && git commit -m "$1" && git push origin main; }; f'


```

## Homebrew

Homebrew is a popular package manager for macOS (and Linux) that simplifies the installation of software. It allows you to easily install, update, and manage packages and dependencies from the command line. With Homebrew, you can get access to a wide range of open-source tools, libraries, and applications that aren’t included by default on your system. It’s a must-have for developers and power users who want to streamline their workflow on a Mac. Not only for the efficiency, it also has some fun commands like cmatrix, tetris, toilet, sl and more.
### Homebrew Commands

* `brew install git`	Install a package
* `brew uninstall git` Uninstall a package
* `brew upgrade git`	Upgrade a package
* `brew unlink git`	Unlink
* `brew link git`	Link
* `brew switch git 2.5.0`	Change versions
* `brew info git`	List versions, caveats, etc
* `brew cleanup git`	Remove old versions
* `brew update`	Update brew and cask
* `brew upgrade`	Upgrade all packages
* `brew list` List installed
* `brew doctor` Diagnose brew issues


I've installed lynx to use my terminal as a web browser & added auto completion and some other pluggins for accessibility.
## My .zshrc

```shell
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi
export LUAVER_DIR="$HOME/.luaver"
[ -s "$LUAVER_DIR/luaver" ] && . "$LUAVER_DIR/luaver"

export ZSH="$HOME/.oh-my-zsh"
PATH=$PATH:~/.local/bin
ZSH_THEME="powerlevel10k/powerlevel10k"

 DISABLE_MAGIC_FUNCTIONS="true"

plugins=(git zsh-syntax-highlighting zsh-autosuggestions web-search)

source $ZSH/oh-my-zsh.sh
alias python=/usr/bin/python3
# Basic Aliases
alias ll='ls -la'               # List files with detailed info
alias g='git'                   # Shorten 'git' command
alias ..='cd ..'                # Move up one directory
alias ...='cd ../..'            # Move up two directories

# Useful Commands
alias c='clear'                # Clear the terminal screen
alias h='history'              # Show command history
alias py='python3'             # Use python3 for 'py'

# macOS Specific Commands
alias def='defaults'               # Access macOS defaults system
alias saytessa='say -V tessa'      # Use macOS TTS with the Tessa voice

alias editzsh='nvim ~/.zshrc' #Editign .zshrc from anywhere
alias vimrc='nvim ~/.vimrc' #Editign .vimrc from anywhere

# >>> conda initialize >>>
__conda_setup="$('/opt/homebrew/Caskroom/miniforge/base/bin/conda' 'shell.zsh' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/opt/homebrew/Caskroom/miniforge/base/etc/profile.d/conda.sh" ]; then
        . "/opt/homebrew/Caskroom/miniforge/base/etc/profile.d/conda.sh"
    else
        export PATH="/opt/homebrew/Caskroom/miniforge/base/bin:$PATH"
    fi
fi
unset __conda_setup
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh
HISTSIZE=10000
alias gacp='f() { git add . && git commit -m "$1" && git push origin main; }; f'

```
