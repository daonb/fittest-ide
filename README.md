#  A Fittest IDE

We provide a box with smart, sharp tools that keep developers happy.
The toolbox is based on:

* zsh - a popular shell
* tmux - a terminal multiplexer: lets you switch easily between several
  programs in one terminal
* neovim - The 5th incranation of 
[qed](https://twobithistory.org/2018/08/05/where-vim-came-from.html) and the
best editor bar emacs.

To these three interfaces we we add the plugins, frameworks and skins:

* [pyenv](https://github.com/pyenv/pyenv) - simple python version management
* [antibody](http://getantibody.github.io/) - zsh plugin manager
* [tpm](https://github.com/tmux-plugins/tpm) - tmux plugin manager
* [liquid prompt](https://github.ocm/nojhan/liquidprompt) - the best prompt, ever
* [alias-tips](https://github.com/djui/alias-tips) - reminding you of aliases
* [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
* [zsh-completions](https://github.com/zsh-users/zsh-completions) - for missing completions
* [tpm](https://github.com/tmux-plugins/tpm) - tmux plugin manager
* [tmux-sensible](https://github.com/tmux-plugins/tmux-sensible) - sensible settings
* [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator) 
seamless navigation between 
* [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect)
* [tmux-copycat](https://github.com/tmux-plugins/tmux-copycat)
* [tmux-open](https://github.com/tmux-plugins/tmux-open)


When you install our IDE we will backup your conf files and 
link the files under `~/.afide/config` to their proper place:

    $ ll ~/.zshrc
    lrwxrwxrwx ... /home/daonb/.zshrc -> /home/daonb/.afide/config/zshrc

## Goodies

### Commands

* `hi` - to print last 100 commands
* `vi` - for neovim, the 4th incaranation of `ed`, named after the 2nd
* `ide` - to start or connect to the tmux session

Using ^ for ctrl:

### Splitting windows:

    * ^a| - split verticlly  
    * ^a- - split verticlly  

### Pane Navigation:

    * ^a ^h - move one pane right
    * ^a ^l - move one pane left
    * ^a ^j - move one pane down
    * ^a ^k - move one pane up

### State

    * ^a ^s - Saving current windows and panes
    * ^a ^r - Restore the last saved windows and panes

### Making Changes

If you want to change something, go ahead, fork this repo  and edit one of the
files.  All the configuration files are grouped into two directories: `/config`
and '/skin'.  Run `make test` to validate your changes and reset:

* `exec zsh` when you change a zsh file
* CTRL-aI for tmux files
* `:source %` after changing your init.vim`.

,, TODO: add command `afide reset` to clean the mess above

## Installation

### Debian/Ubuntu

First get the basic tools from distro packages (as root):

    apt get update
    apt get install neovim zsh tmux

Next, install antibody, pyenv, latest python and the virtual envs required:

    curl -sfL git.io/antibody | sh -s - -b /usr/local/bin
    curl https://pyenv.run | zsh
    exec "SHELL"
    pyenv install 2.7.15
    pyenv install 3.7.3
    pyenv virtualenv 2.7.15 afide2
    pyenv activate afide2 && pip install neovim
    pyenv virtualenv 3.7.3 afide3
    pyenv activate afide3 && pip install neovim
    git clone https://github.com/the-fittest-ide/a-fittest-ide.git ~/.afide
    cd ~/.afide
    make install

Open a new `zsh` and type `ide` to enjoy the fruits of evolution.

### Unistalling
If you decide it's not for you just `afide uninstall` and we'll remove ourselvs and restore the config files. 

## Inspiration

* Dr. Bunsen: [The Text Triumvirate](https://www.drbunsen.org/the-text-triumvirate/)
* Jannis Hemanns: [The iPad Pro as main computer for programming](https://jann.is/ipad-pro-for-programming/)
* Doug Black: [Adding vim to your zsh](https://dougblack.io/words/zsh-vi-mode.html)
* Keggan Lowenstein: [Tmux and Vim - even better together](https://www.bugsnag.com/blog/tmux-and-vim)
* Michel Lopp: [The Foamy rules for rabid tools](https://randsinrepose.com/archives/the-foamy-rules-for-rabid-tools/)
* Fatih Arslan: [Using the iPad Pro as my development machine](https://arslan.io/2019/01/07/using-the-ipad-pro-as-my-development-machine/)
* [vim-awesome](https://vimawesome.com/)
* [dotfiles](http://dotfiles.github.io/)
