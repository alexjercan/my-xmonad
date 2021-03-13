# My XMonad

Build xmonad from source using my custom config file.

# Requirements

* GHCup 0.1.14
* HLS 1.0.0
* cabal 3.4.0.0
* GHC 8.10.3

You also need to add `$HOME/.cabal/bin` and `$HOME/.ghcup/bin` to the system PATH. <br>
Examples:
* export path using .bash_profile:
  - `$HOME/.bash_profile`: `export PATH="$PATH:$HOME/.cabal/bin:$HOME/.ghcup/bin"`
* export path using .ghcup/env (default method of ghcup):
  - `$HOME/.bashrc`: `[ -f "$HOME/.ghcup/env" ] && source "$HOME/.ghcup/env"`
  - `$HOME/.ghcup/env`: `export PATH="$PATH:$HOME/.cabal/bin:$HOME/.ghcup/bin"`

# Installation

```bash
$ git clone https://github.com/alexjercan/my-xmonad.git .xmonad
$ cd .xmonad
$ git submodule init
$ git submodule update
$ cabal install
```

If the instalation fails follow the instructions on and install all the required packages:
* [xmonad](https://github.com/xmonad/xmonad)
* [xmonad-testing](https://github.com/xmonad/xmonad-testing)
* [X11](https://github.com/xmonad/X11)

Use startx or some other program to start xmonad.<br>
If using startx add the following line to the `.xinitrc`: `exec xmonad`.


# Known Issues

1. xmonad-extras does not compile because of `/home/dmacias/xmonad-git/xmonad-extras/XMonad/Prompt/MPD.hs:189:6: error:` merge this pull request to xmonad-extras [#30](https://github.com/xmonad/xmonad-extras/pull/30) and continue installation
```bash
$ cd xmonad-extras
$ git remote add slotThe https://github.com/slotThe/xmonad-extras.git
$ git fetch slotThe
$ git checkout -b historyCompletion
$ git pull slotThe historyCompletion
$ cd ..
$ cabal install
```
