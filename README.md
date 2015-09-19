# dotfiles-manager

## Installation

```bash
git clone git@github.com:cneill/dotfiles-manager.git
# OR
git clone https://github.com/cneill/dotfiles-manager.git
```

If you don't want to clone this to your `$HOME` directory, make sure to copy the
`.dotfiles` file there before running `dotfiles-manager`, OR modify the
`config_file` variable in `dotfiles-manager` to contain its location.

## About

This simple bash script will help you save your dotfiles to a git repository
so you can keep them up to date across machines.

Simply run this script when:

    1. You update your local dotfiles (e.g. in your `$HOME` directory)
    2. You update your remote dotfiles repository on another machine

By default it is designed to be non-destructive (i.e. if you simply hit "ENTER",
it will not make changes to your filesystem / repository).

## Configuration

By default, the file `$HOME/.dotfiles` is used as a configuration file. You
may get warnings about unsafe contents if there are characters that might be
used to execute malicious scripts. You can manually verify the configuration
file and safely load it if you trust it. This is merely a precaution since
no sanitation is done on the configuration file variables.

#### dotfiles\_repo

This is the remote repository you want to save your dotfiles in.

#### dotfiles\_branch

This is the branch on the remote repository that `dotfiles-manager` will use. By
default if this is left blank, `dotfiles-manager` will either use "osx"
or "linux" as the branch name, depending on the platform detected.

#### dotfiles\_loc

This is the local folder you want to store the dotfiles repository in. By
default this is `$HOME/dotfiles`

## Copyright

Copyright (c) 2015 Charles Neill. All rights reserved. dotfiles-manager is
distributed under the two-clause BSD licence.
