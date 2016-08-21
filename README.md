# Introduction

My dotfiles, managed by git and [GNU Stow](https://www.gnu.org/software/stow/).

This article explains the idea:

* http://brandon.invergo.net/news/2012-05-26-using-gnu-stow-to-manage-your-dotfiles.html

# Setup

To configure stow to push file to the user home directory:

```
cat <<EOF > .stowrc
--target=$HOME
EOF
```

Then you can enable configuration files using `stow package`.

Some packages require configuration before stowing,
these are listed below.

## git setup

To use different names for work and home,
the git configuration includes `~/.gitconfig.local`.
This was done using:

    git config --global include.path '~/.gitconfig.local'

To customize local settings, one can use
`git config --file ~/.gitconfig.local`, e.g:

```
git config --file ~/.gitconfig.local user.name "Firstname Lastname"
git config --file ~/.gitconfig.local user.email "firstname.lastname@company.com"
```

See also:

* http://agateau.com/2015/splitting-your-gitconfig/
