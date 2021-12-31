---
layout: post
title:  "Adding My Own Logo"
date:   2021-05-17 21:14:31 -0600
---
# Updating My Site

### Adding Pictures
Next step in my website adventure, make it more than just a simple boring site.
I don't know exactly what I want my site to look like at this point, but I know
I want some more color and a logo. I don't think I will go crazy overboard, but
I also don't want it to look like a site from the 90's. There are plenty of 
tutorials out there, I just need to find one (or two) to follow and get moving 
with making this more interesting.

For future readers my original site at this point looked like this:

![original site](../../../images/2021-05-17/OriginalSiteMay2021.png)

> Side Note:  Adding Pictures and Links to a Markdown Based Post
> 
> Links:
> `[link](http://kramdown.gettalong.org)`
> 
> Pictures: 
> `![gras](img/image.jpg)`
> this path is the relative path to the image file after jekyll has "compiled"
> (what is the correct word for this?) the site into the _site folder.

> Side Note:  How to Screen Snippet on a Mac
> 
> Hold down command + shift + 4, it creates a little crosshairs that can be
> clicked and dragged to take a snippet of the screen.
{: .sideNote }

It's time to add in my logo. When I first decided to do this project I knew I 
was going to want a logo and a fun name. I spent a couple of days brainstorming
ideas and finally stuck with The Curious Fairy and The Curious Blog.  First and 
foremost I am here to learn and share what I learn. Most of the time it will be 
tech related like this, but as things go on, I'm not sure it will stay that way 
I tend to look up all sorts of things, and I am sure some of them will end up 
here.

### Adding My Logo

This was simple and turned into something a bit more difficult as I tried to 
troubleshoot my problem.  Adding in the image of my log was a quick google search
away, and a small code snippet into a new main.scss file:

~~~
---
# main.scss needs the front matter, but only main, I think
---

@import "minima";

.site-title::before {
	content: url("../relative/pathTo/image.png");
	display: inline-block;
	position: relative;
	width: 37px;
	top: 5px;
}
~~~

This successfully added my logo, but left the title still there.

![LogoWithName](../../../images/2021-05-17/LogoWithName.png)

This was not what I wanted. I stared at the scss file a bit and new that my 
image was being put before something with the class `site-title` now all I 
had to do was figure out how jekyll and the minima theme assembled the html 
so I could override it somehow.  I initially hit up my favorite search engine,
I landed on another semi helpful stack overflow page which led me to the
[minima theme's documentation](https://github.com/jekyll/minima).  Why did
I not think to start there? That would have been the obvious thing to do. 
After reading through the very thorough readme, I realized I just needed to 
find the right file in the theme's structure and put it into my own project's
structure and change it. (I just read that again, and it's clear as mud)

Minima has a specific file structure that lives in a gem folder.  I needed to
find the correct html file that held a tag with `class="site-title` so I could
have it not hold the site title as I no longer needed it. After some time of 
searching and learning how the html worked together, I found it! The site title
lives in the header.html file, which in thinking about it, makes perfect sense.
At this point I was able to update the line from
~~~
<a class="site-title" rel="author" href="{{ "/" | relative_url }}">{{ site.title | escape }}</a>
~~~
to
~~~
<a class="site-title" rel="author" href="{{ "/" | relative_url }}"></a>
~~~
which gave me the logo without the name.

![LogoWithOutName](../../../images/2021-05-17/LogoWithOutName.png)

Exactly what I wanted it to look like.  However, at this point I was no longer
sure this was how it should be done.  Is inserting an image via scss that way
I should go?  I went to all this trouble to override the file to get rid of 
the name, should I just further override the file so the picture is there 
natively?

After reading and looking at numerous options, I can go either way.  I opted to
leave it as a pseudo element using the `::before` and `content` tags in the css. 
I may change my mind as I move forward with other changes to the site, but in the 
mean time this satisfies my need.