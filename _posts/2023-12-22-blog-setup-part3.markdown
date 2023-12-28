---
layout: post
title:  "Jekyll Site Setup Part 3 - Gemfile and .yml file"
author: Vanessa Arreola
date:   2023-12-22 09:00:00 -0600
categories: personal blog-setup jekyll
tags: jekyll ruby
comments: true
---

### This is part 3 of how I set up my static blog portfolio website. ###

In part 3 of this series, I'm going to cover what the gemfile is, and changes to the _config.yml file. If you haven't already, you may want to read the previous posts in this series to catch up.

**Previous Posts**
* [Part 1 - Installing Ruby]({% post_url 2023-12-12-blog-setup %})
* [Part 2 - Setup Jekyll]({% post_url 2023-12-13-blog-setup-part2 %})
* [Part 3 - Gemfile and .yml file]({% post_url 2023-12-22-blog-setup-part3 %})
* [Part 4 - Project Page]({% post_url 2023-12-28-blog-setup-part4 %})

#### **Gemfile** #### 
If you look at the root of your project directory for your newly created Jekyll site, you will see that there is a file called ***Gemfile***. If you remember from part 1, we learned that a ***Gem*** is basically a package manager. A Gemfile describes the dependencies required to run a Ruby program. Let's take a look at our gemfile. 

* At the very top, we see: ```source "https://rubygems.org"``` which is the source of all our gems.
* Gems are listed using the following basic syntax: ```gem "my_gem```
    * As an example, our file contains: ```gem "minima", "~> 2.5"``` ***"minima*** is the default theme that Jekyll comes with. The ```"~> 2.5"``` defines the gem version. 

**We have 7 options when defining the gem version:**
* ```=``` Equal To
* ```!=``` Not Equal To
* ```>``` Greater Than
* ```<``` Less Than
* ```>=``` Greater Than Or Equal To
* ```<=``` Less Than Or Equal To
* ```~>``` Pessimistically Greater Than or Equal To

Part of what I wanted to do on my site was showcase my GitHub Repositories. To do that, we will need some GitHub metadata. Let's add that now.
In your Gemfile, add the following line: 
```gem "jekyll-github-metadata"```

**Now let's look at the *_config.yml* file**
This is where we will define settings that affect our entire blog, and is written using *YAML* syntax. Let's update some of our settings.
1. Update the Title of your blog on the line ```title: ```. In my case, mine is called Vanessa Arreola and looks like: ```title: Vanessa Arreola```
2. Follow the same steps for each of the following steps: 
    1. ```description: ```Description of blog that will appear at the bottom
    2. ```baseurl: ``` if using
    3. ```url:``` base hostname
    4. ```github_username:``` your github username
    5. ```repository:``` repository of your website
    6. ```permalink: /:collection/:year-:month-:day-:title:output_ext``` permalink generation
    7. ```show_excerpts: true``` show excerpts of blog posts

**Next, let's add a plugin for the github metadata**
* Under ```plugins: ``` add ```  - "jekyll-github-metadata"```

This config file is not automatically reloaded, so we will have to restart the server process. If your server is running, ```ctrl + c```. Now restart with ```bundle exec jekyll serve --livereload```. You should see your updated blog title and description. Jekyll comes with a sample blog post, and you should see an excerpt of it on your home page if you chose true. 

And there you have it, your gemfile and yml files have been updated. Next time, I will cover how to set up your github portfolio page. 

### Helpful Resources ###
* <a href="https://jekyllrb.com/docs/configuration/options/" target="_blank">Configuration Options</a>