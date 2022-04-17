# current way (using stow)
See https://www.stevenrbaker.com/tech/managing-dotfiles-with-gnu-stow.html

* `sudo dnf install stow`
* `mkdir ~/git/dotfiles`
* within the new `dotfiles` directory replicate the desired folder structure
  but underneath a relevant name, e.g:
    * `dotfiles/R/.Rprofile`
    * `dotfiles/bash/.bashrc`
* `cd ~/dotfiles`
* Due to this README, need to be specific, i.e
	- `stow -v -R --target=/home/tim/ R bash kitty nano starship`; (v = verbose, R = replace current files)
    - or (without this README) `stow -v -R --target=/home/tim/ *`
* check `~/git/dotfiles` in to git.

## current directory structure

```
├── bash
│   └── .bashrc
├── kitty
│   └── .config
│       └── kitty
│           ├── current-theme.conf
│           └── kitty.conf
├── nano
│   └── .nanorc
├── R
│   └── .Rprofile
├── README.md
└── starship
    └── .config
        └── starship.toml
```

# old way
See https://news.opensuse.org/2020/03/27/Manage-dotfiles-with-Git/

## using git
* `mkdir ~/dotfiles`
* `git init --bare $HOME/dotfiles`
* Add the following to `.bashrc` and reload/source:
	- alias dotfiles='/usr/bin/git --git-dir=$HOME/dotfiles --work-tree=$HOME'
* `dotfiles config --local status.showUntrackedFiles no`
* dotfiles remote add origin git@yourgit.example.com/dotfiles.git
* dotfiles push

## move to another machine
* `git clone --bare git@github.com:tjtnew/dotfiles.git $HOME/dotfiles`
* `alias dotfiles='/usr/bin/git --git-dir=$HOME/dotfiles --work-tree=$HOME'`
* `dotfiles checkout`
