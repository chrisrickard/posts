Automating the setup and configuration of your development You free yourself from the fear of a reinstall and laugh in the face of danger. "Mwuhaha!" you say to that towering beast known as Harddrivius-Failurius. Some people report a new found swagger in their walk.


The looming upgrade of my Macbook Pro, along with the first employee starting at [inoutput](http://inoutput.io) (the software company I run with the handsome James Cole),  were the catalysts that sent me on the search for automation. I am pretty late to the game here, but happy I discovered the game at all.

Below I talk about the tools I use to automate my setup. It's probably not perfect, but I feel it's a good first draft. It's also not currently 100% automated... To install XCode command-line tools you have to click a button. Doh.



## The tools
I currently run OSX 10.9, and the automation tools I currently use (and describe below) are specific to Macs. I have a bunch of [scripts up on Github](https://github.com/chrisrickard/laptop.osx) I use to setup machines, below I will run through each component I use.


## Pre-reqs
Before installing anything else, XCode command-line tools are required. This is a simple install in Maverics, by simply throwing `xcode-select --install` into a terminal. Now unfortunately this is the part where you have to click a button to install. *Yawn*

{<1>}![XCode Command Line tools installer](https://chrisrickard.s3.amazonaws.com/img/xcode-cmd-install.png)


## OSX Configuration
> Sensible OSX defaults

It's the little things that matter. Whether you dig the "natural" scroll of the trackpad, whether you want to autohide scrollbars - or what the default directory is Finder starts up in. I have my [default OSX config](https://github.com/chrisrickard/laptop.osx/blob/master/setup) stored on Github (based on the amazing [dotfile](https://github.com/mathiasbynens/dotfiles/blob/master/.osx) by mathiasbynens).

I execute this file in the terminal, and it instantly setups up OSX the way I dig it.


## Homebrew
> Homebrew installs the stuff you need that Apple didn’t.

[Homebrew](http://brew.sh/) is an OSX based package manager (built on top of Ruby and Git) that allows you to easily install packages via the command line.
It has [a bunch](https://github.com/Homebrew/homebrew/tree/master/Library/Formula) of "formulae" (packages), and also allows you to easily brew your own.

Installing Homebrew is as easy as drinking someones homemade beer:

`ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"`

Once installed, you can simply type `brew search <packagename>` to search for a particular package, or run without the parameter to show all.
To install a package, it's as simple as `brew install <packagename>` for example, to install NodeJS you would run `brew install node`


## Homebrew Cask
> "To install, drag this icon..." no more!

[Homebrew Cask](https://github.com/phinze/homebrew-cask) was the catalyst behind me deciding to script my dev setup. A command line tool for install OSX binaries (.app's). I was always a bit jealous of Linux package managers such as apt-get, as they seemed to have everything you would need. Cask doesn't have *everything* but it certainly has a lot, and with Homebrew and Cask in your arsonry - life is better one.
Built on-top of Homebrew, Cask also has [a bunch](https://github.com/phinze/homebrew-cask/tree/master/Casks) of "casks" (apps), and once again - allows you to easily bottle your own.

To get your cask on, simply type:

`brew tap phinze/cask
brew install brew-cask`

To search (or list) packages run `brew cask search <packagename>`, or without the parameter to show all.
Similar to Homebrew, installing a package (such as Chrome) is as easy as running `brew cask install google-chrome`


## Mackup
> Keep your application settings in sync.

[Mackup](https://github.com/lra/mackup) is a utility that backs-up, syncs, and restores all your application specific settings via [Dropbox](https://www.dropbox.com/) (runs on both OSX & Linux).

It's simple and rad. It supports a [bunch of app settings](https://github.com/lra/mackup#supported-applications), which means I can easily keep my Sublime Text 2 settings, iTerm2 settings and Adium accounts backup up on Dropbox, and easily restored when required.

Installation of Mackup is as wiggedy wack as:

`brew install mackup`

Yup, that simple. The first step is to then get Mackup to backup & symlink all your config files into Dropbox, for this simply run `mackup backup`.
When you are restoring your settings (on a new box or reinstall etc.) - simply install Dropbox first, then Mackup - and run `mackup restore`. Done.


## My setup
When I need to setup a new box, I simply:

1. Run my [default OSX configuration](https://github.com/chrisrickard/laptop.osx/blob/master/setup)
2. Install XCode command-line tools with `xcode-select --install`
3. Run my [app install script](https://github.com/chrisrickard/laptop.osx/blob/master/install)
4. Run Mackup restore with `mackup restore`

And that's a wrap.

## Outro

Scripting your development machine is definitely an ever evolving beast - andf f you don't keep it up to date it loses it's value quicky.

The tools I use above are a bit of a hodge-podge solution, and I am sure there may be better (radder) ways out there. [Dotfiles](http://dotfiles.github.io/) are certainly something I need to spend time looking in to as they seem very powerful.