---
layout: post
title: 	First Post
date: 	2022-10-05 21:33:00 -0700
---
Testing testing 1 2 3.

Moved to Jekyll for writeup. To install on Fedora Linux: 

```
sudo dnf install ruby ruby-devel openssl-devel redhat-rpm-config \
	@development-tools
echo '# Install Ruby Gems to ~/gems' >> ~/.zshrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.zshrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

gem install jekyll bundler
```

Change directory to git for this, and run

```
bundle update && bundle install
```
