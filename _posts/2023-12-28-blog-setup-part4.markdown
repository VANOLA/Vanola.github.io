---
layout: post
title:  "Jekyll Site Setup Part 4 - Project Page"
author: Vanessa Arreola
date:   2023-12-28 09:00:00 -0600
categories: personal blog-setup jekyll
tags: jekyll ruby
comments: true
---

### Part 4 of how I set up my static blog portfolio website. ###

In part 4 of this series, I'm going to show how I set up my GitHub project page.

**Previous Posts**
* [Part 1 - Installing Ruby]({% post_url 2023-12-12-blog-setup %})
* [Part 2 - Setup Jekyll]({% post_url 2023-12-13-blog-setup-part2 %})
* [Part 3 - Gemfile and .yml file]({% post_url 2023-12-22-blog-setup-part3 %})
* [Part 4 - Project Page]({% post_url 2023-12-28-blog-setup-part4 %})

Now that you have your website up and running, let's add a Projects page. It is pretty straight forward. If you remember, in part 3 we added a 
the <a href="https://github.com/jekyll/github-metadata" target="blank">**GitHub Metadata Plugin**</a> in our .yml file. This plugin makes some repository information, 
such as the name and description, available to Jekyll sites. The metadata is then available via the ```site.github``` namespace. 

Let's create our Project page. In your root directory, create a file named ***projects.markdown***. This is <a href="https://github.com/VANOLA/Vanola.github.io/blob/main/projects.markdown" target="blank">**Source Code**</a> for the project file. Let's 
start with the front matter.
```yaml
---
layout: page
title: Projects
permalink: /projects/
---
```
The nice thing about the ***page*** layout is that a link will automatically be added to our nav bar. This is configured in the header.html file under _includes.

The logic is written in Liquid templating language. Content is outputted between 2 curly braces. Logic statements are surrounded by a curly brace and percentage sign. See 
<a href="https://jekyllrb.com/docs/liquid/" target="blank">**Liquid**</a>. 

![Code:](/assets/liquid-code.png)

* Loop through our public repos. From there, I exclude any forked repos, and only include repos with topics. 
* Make the repo name / url a heading so it will stand out
* Display the topics
* Show the updated at date

**End Result**
![Result:](/assets/project.png)

A link called Projects should now be displayed in your nav bar. There you have it, a project page. In the next post, I'll cover adding
comments with disqus.