# sumeetjain does dotfiles

These are based very heavily on [Holman's dotfiles](http://github.com/holman/dotfiles/).

## dotfiles

Your dotfiles are how you personalize your system. These are mine. The very prejudiced mix: OS X, zsh, Ruby, Rails, git, homebrew, rvm, TextMate. If you match up along most of those lines, you may dig my dotfiles.

I was a little tired of having long alias files and everything strewn about (which is extremely common on other dotfiles projects, too). That led to this project being much more topic-centric. I realized I could split a lot of things up into the main areas I used (Ruby, git, system libraries, and so on), so I structured the project accordingly.

## install
I suggest switching from bash to zsh. *For Mac users: System Preferences > Accounts, right-click on 'My Account', choose Advanced Options. Change "Login shell" to /bin/zsh. Restart Terminal (quit and reopen).*

### basic installation
1. `git clone git://github.com/sumeetjain/dotfiles ~/.dotfiles`
2. `cd ~/.dotfiles`
3. `rake install`

### awesome installation
1. `ruby -e "$(curl -fsS http://gist.github.com/raw/323731/install_homebrew.rb)"` *installs [homebrew](http://github.com/mxcl/homebrew/blob/master/README.md)*
2. Restart Terminal.
2. `brew install grc` *installs grc (for colors)*
3. Fork this repository.
4. `git clone [your forked repo address] ~/.dotfiles`
5. `cd ~/.dotfiles`
6. `rake install`

The install rake task will symlink the appropriate files in `.dotfiles` to your home directory. Everything is configured and tweaked within `~/.dotfiles`, though.

The main file you'll want to change right off the bat is `zsh/zshrc.symlink`, which sets up a few paths that'll be different on your particular machine.

## topical

Everything's built around topic areas. If you're adding a new area to your forked dotfiles — say, "Java" — you can simply add a `java` directory and put files in there. Anything with an extension of `.zsh` will get automatically included into your shell. Anything with an extension of `.symlink` will get symlinked without extension into `$HOME` when you run `rake install`.

## what's inside

A lot of what's inside is just aliases: `gs` for `git status`, `gl` for `git pull --rebase --prune`, for example. You can browse the `aliases.zsh` files in each topic directory. There's also a collection of scripts in `bin` you can browse. A few notable ones:

###git
- `gpa [message]` adds everything from a dirty repository, creates a commit, and pushes it at once.

###rails
- `s` pings your system for any running Rails apps, and `deathss` will then kill all of them indiscriminately. `ss` starts up a new Rails server on the next available port- if 3000 is taken, it'll spin up your server on 3001.

###system
- `c` is an autocomplete shortcut to your projects directory. For example, `c git` and then hitting tab will autocomplete to `github`, and then it simply changes to my `github` directory.
- `check [filename]` is a quick script that tells you whether a domain is available to register.
- `smartextract [filename]` will extract about a billion different compressed/uncompressed/whatever files.

##moar custom
There are a few things I use to make my life awesome. They're not a required dependency, but if you make it happen, THEY'LL MAKE **YOU** HAPPEN.

- If you want some more colors for things like `ls`, install grc: `brew install grc`.
- If you install the excellent [rvm](http://rvm.beginrescueend.com) to manage multiple rubies, your current branch will show up in the prompt. Bonus.

## thanks

I forked [Ryan Bates](http://github.com/ryanb)' excellent [dotfiles](http://github.com/ryanb/dotfiles) for a couple years before the weight of my changes and tweaks inspired me to finally roll my own. But Ryan's dotfiles were an easy way to get into bash customization, and then to jump ship to zsh a bit later. A decent amount of the code in these dotfiles stem or are inspired from Ryan's original project.