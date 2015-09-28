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

Simply run this script when:

    1. You update your local dotfiles (e.g. in your `$HOME` directory)
    2. You update your remote dotfiles repository on another machine

By default it is designed to be non-destructive (e.g. if you simply hit "ENTER",
it will not make changes to your filesystem / repository).

## Configuring

By default, the file `$HOME/.dotfiles` is used as a configuration file. You
may get warnings about unsafe contents if there are characters that might be
used to execute malicious scripts. You can manually verify the configuration
file and safely load it if you trust it.

#### dotfiles\_repo

This is the remote repository you want to save your dotfiles in.

#### dotfiles\_branch

This is the branch on the remote repository that dot-manwill use. By
default (e.g. if this is left blank), dot-man will either use "osx"
or "linux" as the branch name, depending on the platform detected.

#### dotfiles\_loc

This is the local folder you want to store the dotfiles repository in. By
default this is `$HOME/dotfiles`

## Copyright

Copyright (c) 2015 Eric R. Jeschke. All rights reserved. Ginga is distributed under an open-source BSD licence. Please see the file LICENSE.txt in the top-level directory for details.
