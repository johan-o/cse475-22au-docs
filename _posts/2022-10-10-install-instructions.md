---
layout:	post
title:	Jekyll Install Instructions & Notes
date: 	2022-10-10 13:00:00 -0700
author: Johan Olsson
---

I chose Jekyll for its ease of use to host the website. Installation is easiest on Linux

# Installation Instructions
## Linux (Fedora Workstation 36)
Assuming that `zsh` is the default shell:

Run the following commands in the terminal:
```
sudo dnf install -y ruby ruby-devel openssl-devel redhat-rpm-config \
	@development-tools gcc-c++
echo '# Install Ruby Gems to ~/gems' >> ~/.zshrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.zshrc
echo 'export PATH="$HOME/gems/bin:$HOME/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

![Fedora 36 Initial Install](/cse475-22au-docs/assets/jekyll-install/fedora-init-install.png)

## Windows

Install Windows Subsystem for Linux in Administrator PowerShell `wsl --install`. Reboot and follow 
prompt.

![WSL Install](/cse475-22au-docs/assets/jekyll-install/windows-wsl.png)

![Ubuntu under WSL](/cse475-22au-docs/assets/jekyll-install/windows-wsl-install.png)
Once installed, open the Ubuntu shell, create your user, and run 

```
sudo apt-get install ruby ruby-dev build-essential zlib1g-dev
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

change directory to root of the github repo for the website, and follow on all platforms using the Ubuntu shell.

## macOS

## All Platforms
Finally, install bundler and jekyll, update and install this bundle:

```
gem install jekyll bundler
bundle update && bundle install
```

# Notes
1. Familiarize yourself with Git/Github. The branch `master` is what the website is based off,
	create and merge individual branches for each of your posts.
1. Each blog post will be written in [Markdown](https://www.markdownguide.org/basic-syntax/)
1. Images can be included in each blog post with

	`![IMAGE TITLE HERE](/cse475-22au-docs/assets/POSTNAME/PATHTOFILE.EXT)`
1. It's useful to be able to test changes locally. Run a local copy of the website with the command
	`bundle exec jekyll serve --livereload`

	This local copy will live reload all live changes you make, access at URL 
	[http://localhost:4000/cse475-22au-docs/](http://localhost:4000/cse475-22au-docs/)

	![Fedora 36 Local](/cse475-22au-docs/assets/jekyll-install/fedora-local.png)
	![Windows Local](/cse475-22au-docs/assets/jekyll-install/windows-local.png)

	Errors will be printed to terminal
