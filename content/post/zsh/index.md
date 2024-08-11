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
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
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

![Neofetch](zsh.png)

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

alias editzsh='vim ~/.zshrc' #Editign .zshrc from anywhere
alias vimrc='vim ~/.vimrc' #Editign .vimrc from anywhere



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
# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi



export LUAVER_DIR="$HOME/.luaver"
[ -s "$LUAVER_DIR/luaver" ] && . "$LUAVER_DIR/luaver"



# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH

# Path to your oh-my-zsh installation.
export ZSH="$HOME/.oh-my-zsh"
PATH=$PATH:~/.local/bin

# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes


ZSH_THEME="powerlevel10k/powerlevel10k"
# Uncomment one of the following lines to change the auto-update behavior
# zstyle ':omz:update' mode disabled  # disable automatic updates
# zstyle ':omz:update' mode auto      # update automatically without asking
# zstyle ':omz:update' mode reminder  # just remind me to update when it's time

# Uncomment the following line to change how often to auto-update (in days).
# zstyle ':omz:update' frequency 13

# Uncomment the following line if pasting URLs and other text is messed up.
 DISABLE_MAGIC_FUNCTIONS="true"

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# You can also set it to another string to have that shown instead of the default red dots.
# e.g. COMPLETION_WAITING_DOTS="%F{yellow}waiting...%f"
# Caution: this setting can cause issues with multiline prompts in zsh < 5.7.1 (see #5765)
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git zsh-syntax-highlighting zsh-autosuggestions web-search)

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='mvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch x86_64"
#
# Set personal aliases, overriding those provided by oh-my-zsh libs,
# plugins, and themes. Aliases can be placed here, though oh-my-zsh
# users are encouraged to define aliases within the ZSH_CUSTOM folder.
# For a full list of active aliases, run alias.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"
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

alias editzsh='vim ~/.zshrc' #Editign .zshrc from anywhere
alias vimrc='vim ~/.vimrc' #Editign .vimrc from anywhere

# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
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
# <<< conda initialize <<<

# To customize prompt, run p10k configure or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh
HISTSIZE=10000


```