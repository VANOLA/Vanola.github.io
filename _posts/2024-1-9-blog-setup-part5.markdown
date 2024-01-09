---
layout: post
title:  "Jekyll Site Setup Part 5 - Content"
author: Vanessa Arreola
date:   2024-01-09 11:00:00 -0600
categories: personal blog-setup jekyll
tags: jekyll
comments: true
---

### Part 5 of how I set up my static blog portfolio website. ###

In part 5 of this series we're going to write some content.

**Previous Posts**
* [Part 1 - Installing Ruby]({% post_url 2023-12-12-blog-setup %})
* [Part 2 - Setup Jekyll]({% post_url 2023-12-13-blog-setup-part2 %})
* [Part 3 - Gemfile and .yml file]({% post_url 2023-12-22-blog-setup-part3 %})
* [Part 4 - Project Page]({% post_url 2023-12-28-blog-setup-part4 %})
* [Part 5 - Content]({% post_url 2024-1-9-blog-setup-part5 %})

If you've been following along in the series, you should now have your blog and project page up and running.
The next thing to add is your first blog post. Since the pages are built using markdown, this is super 
easy to do! If you don't know Markdown or just need a refresher, <a href="https://www.markdownguide.org/basic-syntax/" target="blank">this website</a> has an overview of the basic syntax.

When we create a new blog post, Jekyll will list the posts on the home page (which is the index.markdwon file) by default. Later, I'll show you how to add a new Blog page with links to posts by tags. Let's take
a look at the front matter of the index page.
```
---
layout: home
list_title: Read My Latest Posts
title: ''
---
```

The first thing is layouts, which are just templates that wrap around your content. A look at the <a href="https://github.com/jekyll/minima" target="blank">Minima Theme Github</a> will show you the different layouts available. You can override any file in the theme by creating a copy in your project directory. If you would like to override a layout, create a directory in the root called "_layouts" and copy the layout into it. Any changes you make will now show up. Let's look at the home layout. You can see that the title is displayed first. Any content we write will be injected next into the content section. Next is the title of our list_title and excerpts. 


For my site, I chose to override the layout to show a featured image along with the post excerpt. You can
add the code to the home layout just above the show excerpts block. Don't forget to surround your if and end if with  curly brace and percent symbol. I did not care for how it looked, and ended up changing it back.  
``` 
 if post.featured_image 
    <div class="featured-image">
    <img src="{{ '/assets/' | append: post.featured_image | relative_url }}" />
    </div>
 endif 
```

The next thing in the front matter is the "list_title". I chose the message "Read My Latest Posts". All that's left is for you to customize it. Any content you add will automatically go before the blog post excerpts. If you want to add an image, you can do so with the following syntax:
```
![display text](path/to/image.jpg)
```
Images are typically stored in a directory called "assets" located in the root directory. If you haven't already, go ahead and create it. Now let's create our About page. It should already be created for you. You'll notice in the front matter that the layout for the about page is "page". Any file with a layout of page will automatically be added to the Navbar at the top! Go ahead and customize your About page. 

Now on to our first blog post. All of your posts should be in the _posts directory and are written in Markdown. There should already be a post for you, you an either customize it to be your first post, or delete it and create a new one. The following naming convention must be used for blog posts:
```
YEAR-MONTH-DAY-title.markdown
```

Next, we write our front matter. I'll show you how I normally do my front matter.
```
---
layout: post
title:  "Title of my Post"
author: Vanessa Arreola
date:   2024-01-09 11:00:00 -0600 (Obviously put your current date)
categories: Add Categories Separated By A Space
tags: Add Tags Separated By A Space
---
```

It's pretty self explanatory. The blog posts will not display until the date/time has passed. Categories and Tags are optional. I used them to be able to group certain posts together. 

You should now have your home page, about page, and your first blog posts. Congratulations! In the next post of this series, I will briefly cover customizing the look of your site and adding a favicon. Design is definitely not my strongest skill, but I will share what I have learned so far. 

### Helpful Resources ###
<a href="https://www.markdownguide.org/basic-syntax/" target="blak">Markdown Syntax</a>

<a href="https://github.com/jekyll/minima" target="blank">Minima Github</a>

<a href="https://jekyllrb.com/docs/layouts/#:~:text=Layouts%20are%20templates%20that%20wrap,live%20in%20the%20_layouts%20directory." target="blank">Jekyll Layouts</a>

<a href="https://jekyllrb.com/docs/posts/" target="blank">Jekyll Posts</a>