+++
title = "Launch School Mac Setup"
date = 2018-04-25T18:12:53+10:00
description = "How to setup your Mac to get ready for Launch School"
weight = 20
draft = false
bref = "A few simple setup to get your development environment setup on your Mac."
toc = true
comments = true
+++

### Install [Homebrew](https://brew.sh/) 
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```


### Install Ruby using rbenv

Use Homebrew to install rbenv:
```bash
brew update && brew install rbenv ruby-build
```

Restart terminal, and install ruby: (I'm installing ruby version 2.5.0 here)
```bash
rbenv install 2.5.0
```

Next set your global Ruby version
```bash
rbenv global 2.5.0
```
  
Finally check your ruby version
```bash
ruby -v
#=> ruby 2.5.0 ...
```
<br>
Reference: https://gorails.com/setup/osx/10.12-sierra
