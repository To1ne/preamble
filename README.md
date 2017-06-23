`preamble |priːˈamb(ə)l, ˈpriː-| - a preliminary or preparatory statement`

My current playbook to setting up a new Mac, it
uses [Ansible](http://www.ansible.com/home) because it's easy to read
and write and I hope it helps me avoid [this](http://xkcd.com/1319/).

I realise automating setting up a new machine probably isn't worth my
time,
[here's a handy graph to see why](http://xkcd.com/1205/). However,
automating setting up a new machine wasn't the real goal, it was a
headfake. By writing this I have an easy way to show others (and
future me) what applications I'm using and how I installed them. An
added bonus is the glee in feeling like I'm doing HIGH TECH
COMPUTERING by installing stuff from a text file.

### What will it do

- Install [Homebrew](http://brew.sh)
- Install several rubies (see `ruby.yml`)
- Install command line apps I use
- Install apps I use (everything I didn't get through App Store is installed using `brew cask`)
- Set some sensible OSX defaults

And more, see the `playbook.yml` for more info.

### Steps

- Install Xcode
- `git clone` this repo
- `sudo easy_install pip; sudo pip install ansible`
- `cd preamble`
- `ansible-playbook playbook.yml`

Once this is done, installing new things is as easy as changing the
`playbook.yml` and rerunning `ansible-playbook playbook.yml`.

I've also tried to add some tags, so you can target specific parts of
it (`ansible-playbook --tags=tag1,tag2`) or skip specific parts
(`ansbible-playbook --skip-tags=tag1,tag2`).

Available tags:

- `capslock`: Remaps capslock to control.
- `databases`: Install databases
- `defaults`: Sets Finder defaults
- `emacs`: Installs utils/libs used by GNU Emacs.
- `fonts`: Installs the fonts I use.
- `ios`: Installs everything related to iOS
- `mail`: Installs mail-related tools.
- `nodejs`: Installs nodejs tools.
- `osx`: Installs OS X applications, and also `capslock` and `defaults`.
- `ruby`: Install rubies.
- `utils`: Installs common command line utils.
