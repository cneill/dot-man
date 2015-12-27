# dot-man (•‿•)

## About

This simple bash script will help you manage your dotfiles to a git repository
so you can keep them up to date across machines / multiple branches.

To track new dotfiles, simply add them to the dotfiles repo. From then on, changes to
the files in your home directory or in the dotfiles repo will be tracked.

## Installation

These are the paths that dot-man uses by default. Modify and update the `.dotfiles`
configuration file as needed. 

```bash
git clone git@github.com:cneill/dot-man.git $HOME/dot-man
cp $HOME/dot-man/.dotfiles $HOME  # COPY CONFIG TO $HOME DIRECTORY
$EDITOR "$HOME/.dotfiles"         # USE YOUR FAVORITE TEXT EDITOR TO EDIT CONFIG FILE
```

Make sure to copy the `.dotfiles` file to the $HOME directory before running
`dot-man`, or modify the `config_file` variable in `dot-man` first.

## Usage

```
./dot-man [-h] [-d] [-f] [-i] [-l] [-v]

Options:
    -h    Show this help message
    -d    Use best guess for platform
    -f    Force auto-load of config file (no check for unsafe values)
    -i    Ignore last run check entirely
    -l    Don't check for updates unless it's been $dotfiles_update_interval seconds since last run
    -v    Verbose: print more information
```

Run this script when:

1. You update your local dotfiles (e.g. in your `$HOME` directory)
2. You update your dotfiles repository branch on another machine
3. You spawn a new bash/zsh shell

dot-man is designed to be non-destructive (e.g. if you simply hit "ENTER",
it will not make changes to your filesystem / repository).

### Examples

#### Managing, editing, and updating a file with dot-man
[![dot-man example](http://img.youtube.com/vi/yVPGdl5cSL8/0.jpg)](https://www.youtube.com/watch?v=yVPGdl5cSL8)

#### Running dot-man on new shell (e.g. in `.bash_profile` / `.zshrc`)

dot-man can be somewhat noisy by default. If you want to run dot-man every time you start a new shell, you will likely want to specify the `-d`, `-f`, and `-l` flags.

__Example .bash_profile/.zshrc__
```bash
./$HOME/dot-man/dot-man -d -f -l # only run after $dotfiles_update_interval seconds, skip checks
alias dot-man="$HOME/dot-man/dot-man -d -f -i"  # ignore last run time, skip checks
```  

## Configuration

By default, the file `$HOME/.dotfiles` is used as a configuration file. You
may get warnings about unsafe contents if there are characters that might be
used to execute malicious scripts. You can manually verify the configuration
file and safely load it if you trust it. You can skip this check by passing
the `-f` argument.

### Variables

#### dotfiles\_repo

This is the remote repository you want to save your dotfiles in.

#### dotfiles\_branch

This is the branch on the remote repository that dot-man will use. By
default (e.g. if this is left blank), dot-man will either use "osx"
or "linux" as the branch name, depending on the platform detected.

#### dotfiles\_loc

This is the local folder you want to store the dotfiles repository in. By
default this is `$HOME/dotfiles`

#### dotfiles\_last\_run\_file

A file to save the current execution timestamp to. Defaults to
`$HOME/.dotfiles-last-run`.

#### dotfiles\_update\_interval

Time, in seconds, to wait between calling dot-man. Useful when calling dot-man
on startup in e.g. your .zshrc or .bash\_profile. Defaults to 24 hours.

#### dotfiles\_home

By default, dot-man uses `$HOME` as your home directory. If this isn't what you
want, you'll need to change this in `.dotfiles`, as well as install commands, etc.

## Copyright

Copyright (c) 2015 Charles Neill. All rights reserved. dot-man is distributed
under an open-source BSD licence.
