# Python@2 Homebrew Tap

*This repo is archived and unmaintained. Use at your own risk.*
*This branch is updated to work with MacOS 12 Monterey.*

## Why does this exist?

The `python@2` was removed from `homebrew-core` in [#49796](https://github.com/Homebrew/homebrew-core/pull/49796), as Python 2.7.x is now [EOL](https://www.python.org/dev/peps/pep-0373/#id4) and should no longer be in general usage.

In order to maintain some legacy applications for my work, I have extracted the last iteration of the `python@2` formula to this repository. It has since been updated with [Python 2.7.18](https://www.python.org/downloads/release/python-2718/), the last release (ever!) for Python 2.7.

You should _not_ be using this for any new projects. This is a deprecated formula, and exists here only to facilitate running and supporting software that depends on it.

## How do I use it?

### Installation

Add the tap to homebrew:

`brew tap odignal/python2`

Install as usual, if you are on an Intel Mac:

`brew install python@2`

If you are on an M1 Mac, use the following command to install (you might need to install brew in Rosetta 2 first):

Install Rosetta 2:
`/usr/sbin/softwareupdate --install-rosetta --agree-to-license`

Install brew in Rosetta 2 (using /usr/local/homebrew as installation path):
`sudo mkdir /usr/local/homebrew
arch -x86_64 curl -L https://github.com/Homebrew/brew/tarball/master | arch -x86_64 sudo tar xz --strip 1 -C /usr/local/homebrew
sudo chown -R $(whoami) /usr/local/homebrew
echo 'alias brew_x86="arch -x86_64 /usr/local/homebrew/bin/brew"' >> $HOME/.zprofile
echo 'alias brew_arm="/opt/homebrew/bin/brew"' >> $HOME/.zprofile
source ~/.zprofile`

Install Python 2 with brew inside Rosetta 2:
`brew_x86 install python@2`

Because the binary bottles are no longer hosted by Homebrew, the formula will build from source.

### Uninstallation

To uninstall:

`brew uninstall python@2`

To remove this tap:

`brew untap odignal/python2`
