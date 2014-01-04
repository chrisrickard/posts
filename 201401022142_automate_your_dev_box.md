Freeing yourself from the fear of a reinstall is liberating. It gives you superpowers.
You laugh in the face of danger. "Mwuhaha!" you say to that towering beast known as Harddrivius-Failurius, and have a certain swagger that can only be described as "rad".


I am pretty frickin' late to the game here, I was bumbling and fumbling setting up new machines until mid 2013.
The looming upgrade of my Macbook Pro, along with the first employee starting at [inoutput](http://inoutput.io) (the software company I run with the handsome James Cole), these were the catalysts that sent me on the search for automation. Not only did I want to have my development environment scripted - but I wanted other peeps (running OSX) to be able to run, or fork my setup.


## The tools
I currently run OSX 10.9, and the automation tools I currently use (and describe below) are specific to Macs. Although I will chat about some Linux & Windows equivilents, and the current lay of the land. Generally I feel Linux friends are at a bit of an advantage here - as package management tools such as apt, yum or RPM come pre-installed - and creating a simple bash script to automate this is as easy as pie.

I have a bunch of [scripts up on Github](https://github.com/chrisrickard/laptop.osx) I use to setup machines, below I will run through each component used.


## Disclaimer
This is not currently 100% automated... I know, I know - stop going on about it. To install XCode tools you have to click a button :/

## My setup
# Pre-reqs
Before installing anything else, I require XCode Command Line Tools, this is a simple install in Maverics, byt simply throwing `xcode-select --install` into a terminal.. Now unfortunately this is the part where you have to click a button to install. Yawn.

{<1>}![XCode Command Line tools installer](https://chrisrickard.s3.amazonaws.com/img/xcode-cmd-install.png)


# Homebrew
> Homebrew installs the stuff you need that Apple didn’t.

[Homebrew](http://brew.sh/) is an OSX based package manager (built on top of Ruby and Git), that allows you to easily install packages via the command line.
It has [a bunch](https://github.com/Homebrew/homebrew/tree/master/Library/Formula) of "formulae" (packages), and also allows you to easily brew your own.

Installing Homebrew is as easy as drinking someones homemade beer:

`ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"`

Once installed, you can simply type `brew search <packagename>` to search for a particular package, or without the parameter to show all.
To install a package, it's as simple as `brew install <packagename>` for example, to install NodeJS you would run `brew install node`


# Homebrew Cask
> "To install, drag this icon..." no more!

[Homebrew Cask](https://github.com/phinze/homebrew-cask) was the catalyst behind me deciding to script my dev setup. A command line tool for install OSX binaries (.app's). I was always jealous of Linux package managers such as apt-get, as it seemed to have everything - both CLI and GUI apps, and with Homebrew and Cask in your arsonry, life is better.
Built on-top of Homebrew, Cask also has a [a bunch](https://github.com/phinze/homebrew-cask/tree/master/Casks) of "casks" (apps), and once again - allows you to easily bottle your own.

To get your cask on, simply type:

`brew tap phinze/cask
 brew install brew-cask`

To search (or list) packages run `brew cask search <packagename>`, or without the parameter to show all.
Similar to Homebrew, installing a package (such as Chrome) is as easy as running `brew cask install google-chrome`


# Mackup


# My setup

The default packages I currently install with Homebrew are coreutils (GNU coreutils), git, and vim.

`brew install coreutils git vim`


# Git


---

You're in! Nice. We've put together a little post to introduce you to the Ghost editor and get you started. Go ahead and edit this post to get going and learn how it all works!
dsadsa
## Getting Started

Writing in markdown is really easy. In the left hand panel of Ghost, you simply write as you normally would. Where appropriate, you can use *formatting* shortcuts to style your content. For example, a list:

* Item number one
* Item number two
    * A nested item
* A final item

or with numbers!

1. Remember to buy some milk
2. Drink the milk
3. Tweet that I remembered to buy the milk, and drank it

### Links

Want to link to a source? No problem. If you paste in url, like http://ghost.org - it'll automatically be linked up. But if you want to customise your anchor text, you can do that too! Here's a link to [the Ghost website](http://ghost.org). Neat.

### What about Images?

Images work too! Already know the URL of the image you want to include in your article? Simply paste it in like this to make it show up:

{<1>}![The Ghost Logo](http://tryghost.org/ghost.png)

Not sure which image you want to use yet? That's ok too. Leave yourself a descriptive placeholder and keep writing. Come back later and drag and drop the image in to upload:

{<2>}![A bowl of bananas]


### Quoting

Sometimes a link isn't enough, you want to quote someone on what they've said. It was probably very wisdomous. Is wisdomous a word? Find out in a future release when we introduce spellcheck! For now - it's definitely a word.

> Wisdomous - it's definitely a word.

### Working with Code

Got a streak of geek? We've got you covered there, too. You can write inline `<code>` blocks really easily with back ticks. Want to show off something more comprehensive? 4 spaces of indentation gets you there.

    .awesome-thing {
        display: block;
        width: 100%;
    }

### Ready for a Break?

Throw 3 or more dashes down on any new line and you've got yourself a fancy new divider. Aw yeah.

---

### Advanced Usage

There's one fantastic secret about Markdown. If you want, you can  write plain old HTML and it'll still work! Very flexible.

<input type="text" placeholder="I'm an input field!" />

That should be enough to get you started. Have fun - and let us know what you think :)