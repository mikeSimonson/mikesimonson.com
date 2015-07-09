---
title: Sculpin error: Didn't find at least one of this type
subtitle: 
icons:
    - warning
    - bug
image:
    featured: 'jackson/196x196.png'
    class: centered
tags:
    - error
    - post-it
    - php
    - sculpin
---

While building this Website I encountered an issue which was rather trivial but that took a while too uncover.

# Symptoms #

My Sculpin website was perfect when I builded it in dev mode.
But everytime I tried to build the prod environnement, I would see this message in the console output. 

```css
Didnt find at least one of this type : posts
```

It was rather confusing for me as I added that error message to be able to debug some more complex website that I built with Sculpin.
Namely a webiste that had multiple content types added to it.

But it isn't the case for this blog (yet).

It happears that I hit a rather unusual corner case.
As I built this website starting from the [official sculpin blog skeleton](https://github.com/sculpin/sculpin-blog-skeleton), I kept most of the frontmatter from demo posts.
In the demo posts frontmatter, I missed the option that indicated that the content was a draft.

And all my trouble came from there.

#Fix#

Simply setting that option to false or removing it did solve my problem.

```css
draft: false
```
