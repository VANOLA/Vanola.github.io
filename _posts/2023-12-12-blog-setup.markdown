---
layout: post
title:  "Blog Setup Part 1"
author: Vanessa Arreola
date:   2023-12-12 
categories: personal blog-setup
tags: jekyll blogging personal ruby
featured_image: blog-laptop.png
comments: true
---

Now that I've mostly got things working, I wanted to talk a little bit about
how I did it. In a way, this helps me to cement what I've learned, and maybe 
someone else out there will find this helpful. 

This static, portfolio-blog is hosted on GitHub Pages, which is free. I debated using
something like Heroku, but ultimately decided I didn't need anything too fancy. With
Github Pages, I was able to serve my static site straight from a repository, and with 
Jekyll, I'm able to focus more on the content. 

Jekyll is a blog-aware, static site generator. The Jekyll <b><a href="https://jekyllrb.com/docs/" target="_blank">Quickstart Guide</a></b>
does a great job of explaining how to get going. 

### Requirements ###

* I'm using MacOS Sonoma
* Ruby version 2.5.0 or higher
* RubyGems
* GCC and Make

### Installation ###

In my case, I had to first install Ruby. This assumes you have Homebrew installed. 
1. Install chruby, a Ruby version manager:
 ```brew install chruby ruby-install xz``` 
2. Now install Ruby: ```ruby-install ruby 3.1.3```
3. Configure shell to use chruby:   
```echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc```
```echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc```
```echo "chruby ruby-3.1.3" >> ~/.zshrc # run 'chruby' to see actual version```
4. Install the Jekyll and bundler Gem: ```gem install jekyll bundler```
    * A gem is basically a package manager. Each gem has a gemspec, documentation, and the code.
    * The bundler will install any gems needed by the gems I have listed. 

I got stuck on stepm2 for a bit due to an error 
```
configure: error: something wrong with LDFLAGS !!! 
Configuration of ruby 3.1.3 failed!
```

I know, very descriptive. I first had to learn what LDFLAGS were. They are linker flags.
These are basically command line options the linker passes to the compiler. They're used in 
Makefiles. I just finished a Compiler Theory class a few months ago, so I knew it must have
been something I configured. I found it in my .zshrc file. After removing the 
```$ export LDFLAGS="``` line, I tried to install Ruby again. Still the same error. In terminal, 
I ran the command ```unset LDFLAGS```, restarted the shell, and tried again. This time it worked.

Later this week, I'll post Part 2, creating a new Jekyll project. 

### Helpful Resources ###
* <a href="https://simondosda.github.io/posts/2021-09-13-blog-github-pages-1-introduction.html" target="_blank">Build A Portfolio With A Blog Using GitHub Pages</a>
* <a href="https://jekyllrb.com/docs/installation/" target="_blank">Jekyll Docs Installation</a>
* <a href="https://www.moncefbelyamani.com/why-you-shouldn-t-use-the-system-ruby-to-install-gems-on-a-mac/" target="_blank">Why You Shouldn't Use the System Ruby to Install Gems on a Mac</a>
* <a href="https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/" target="_blank">Install Ruby on your Mac with a single command</a>