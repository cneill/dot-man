# dot-man

## Installation

```bash
git clone git@github.com:cneill/dot-man.git
# OR
git clone https://github.com/cneill/dot-man.git
```

If you don't want to clone this to your `$HOME` directory, make sure to copy the
`.dotfiles` file there before running `dot-man`, or modify the
`config_file` variable in `dot-man`.

## About

This simple bash script will help you save your dotfiles to a git repository
so you can keep them up to date across machines.

To track new dotfiles, simply add them to the dotfiles folder and/or repo.

Run this script when:

    1. You update your local dotfiles (e.g. in your `$HOME` directory)
    2. You update your remote dotfiles repository on another machine
    3. You spawn a new bash/zsh shell

By default it is designed to be non-destructive (e.g. if you simply hit "ENTER",
it will not make changes to your filesystem / repository).

## Configuring

By default, the file `$HOME/.dotfiles` is used as a configuration file. You
may get warnings about unsafe contents if there are characters that might be
used to execute malicious scripts. You can manually verify the configuration
file and safely load it if you trust it. You can skip this check by passing
the `-f` argument.

### Running dot-man on new shell (e.g. in .bash\_profile / .zshrc
If you want to call dot-man when you start a new shell, you can call it with the
`-check_last_run` argument. If dot-man has run more recently than specified by
the interval (`$dotfiles_update_interval` in .dotfiles), it will
exit quietly.


### Variables

#### dotfiles\_repo

This is the remote repository you want to save your dotfiles in.

#### dotfiles\_branch

This is the branch on the remote repository that dot-manwill use. By
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

## Copyright

Copyright (c) 2015 Charles Neill. All rights reserved. dot-man is distributed
under an open-source BSD licence.
