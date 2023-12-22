---
layout: post
title:  "Blog Setup Part 2"
author: Vanessa Arreola
date:   2023-12-13 11:00:00 -0600
categories: personal blog-setup
tags: jekyll blogging personal ruby
featured_image: proj-structure.png
comments: true
---

### This is part 2 of how I set up my static blog portfolio website. ###

In [Part 1]({% post_url 2023-12-12-blog-setup %}) of this series, I gave a brief overview
on why I chose to use Github pages, and how to install Ruby and Jekyll. In this post, I'm 
going to cover initiating a new Jekyll project, which is so much easier than it sounds!

### Setup ###

**Create GitHub Repo**

* Create a new Repository and name it ```<user>.github.io``` (Replace user with your username)
    * You can deploy from any repository, but the url would be ```https://<username>.github.io/<repository-name>```
* Set it to public. Optionally, you can skip the README.md
* Open your terminal, and ```cd``` into the directory you want to create the repo in
* Follow <a href="https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository" target="_blank">steps to clone a repository</a>.
    * Follow the section for cloning an empty repository if you did not create the README.md

**Choose Branch to Deploy**

* In your repo's settings, go to the "Code and automation" section in the sidebar.
![Settings](/assets/settings.png)


* Click Pages

![pages](/assets/pages.png)

* Under "Build and deployment", under "Source", select *Deploy from a Branch*.
* Select the branch you want to deploy (usualy main) from the dropdown. 

![branch](/assets/branch.png)

**Create new Jekyll Site**

1. In the repository you just created, enter: ```jekyll new "folder/repo-path"```
    * Whew, take a break, that was hard
2. Open the *Gemfile* that jekyll created. There you will find some instructions

**At this point, the GitHub Pages documentation recommends the following step:**
* "Comment the line ```gem "jekyll"``` and uncomment the line ```gem "github-pages", "~> 214", group: :jekyll_plugins``` (Or whatever <a href="https://pages.github.com/versions/" target="_blank"> dependency version</a> is the latest). Save and close."

#### **However, users often run into issues**
*See the following <a href="https://github.com/github/docs/issues/2177" target="_blank"> explanation and proposed solution</a> by user BenWhetton.*
* If you followed the steps in the last post, your bundler should already be initialized. If not, go ahead and run ```bundle init```
* Run the command ```bundle add --group=":jekyll-plugins" github-pages```
    * This will update your gemfile with the correct version of github pages without manually having to do it. 

**Now let's install our dependencies**   
* ```bundle install``` and ```bundle update``` in the terminal.
* And serve the site: ```bundle exec jekyll serve --livereload```.
* Now open up localhost:4000 and admire your site!
    * Jekyll comes with the *Minima* theme, which I'll cover in an upcoming post.

**Commit your Changes**

* In the terminal, ```git add .```, ```git commit -m "message"```, and ```git push``` your changes after saving.
* Visit ```<username>.github.io``` to see your site! It could take up to 10 minutes to refresh. 

Congratulations! Your site is up and running. In my next post, I'll cover some configurations I made to my Gemfile and _config.yml file. 

### Helpful Resources ###

* <a href="https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository" target="_blank">Create a repository</a>
* <a href="https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository" target="_blank">Cloning a repository</a>
* <a href="https://kinsta.com/blog/jekyll-static-site/" target="_blank">Jekyll Static Site</a>
* <a href="https://docs.github.com/en/github-ae@latest/pages/setting-up-a-github-pages-site-with-jekyll" target="_blank">Setting up a GitHub Pages site with Jekyll</a>
* <a href="https://github.com/github/docs/issues/2177" target="_blank">GitHub Pages Gem</a>
