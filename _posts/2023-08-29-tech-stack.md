---
layout: post
title: Tech Stack (What is this?)
date: 2023-08-29 23:03 +0000
categories: [Blog, Technical]
tags: [git, jekyll, blog, tech]
author: alecmagnani
---
This site was created using a static site generator, and is hosted on Github Pages.

## Static Site Generators

A static site generator is a tool that generates static HTML web pages. In this case, posts written in markdown are used to generate the HTML pages making up this blog site.

My experience with static site generators comes from my time at Amazon. The second-to-last team I worked on was focused on internal developer experiences, and one of the products we owned was a static site generator and hosting platform.

One of the benefits of a good static site generator is that it allows non-technical users to easily create content for websites. It strikes a nice middle-ground that allows it to be easy to use while still being code-focused (or code-adjacent, at least).

If you own a documentation site, you probably want your developers to write some of that documentation, and your developers probably are more comfortable using git, CI/CD workflows, their favorite text editor than they are with Word or some built-in editor. Documentation-as-code also gives access to all the other benefits of version control and automated deployments.

## Jekyll

[Jekyll](https://jekyllrb.com) is a static site generator built in Ruby. It takes markdown and generates HTML sites. It is blog-focused, and also plays nicely with Github Pages, which made it a good choice for this site.

After making changes to the site or writing a post, it can be examined locally by running the command:

```
bundle exec jekyll serve
```

And opening [localhost:4000](localhost:4000). To publish the changes, they just need to be pushed to Github and the pre-configured Action handles building and publishing the updated site.

### Chirpy

[Chirpy](https://chirpy.cotes.page) is a theme for Jekyll that is beautiful and easy to use. Their [Chirpy starter](https://github.com/cotes2020/chirpy-starter) template makes getting started super simple.

### Jekyll-compose

[Jekyll-compose](https://github.com/jekyll/jekyll-compose) provides some additional commands to jekyll to make writing and publishing a post or page even easier. For example, the workflow for this post is is as simple as:

```
bundle exec jekyll draft "Tech stack"
vim _drafts/tech-stack.md 
bundle exec jekyll publish _drafts/tech-stack.md
git add .
git commit -m "New post: Tech stack"
git push
```

## Github Pages

[Github Pages](https://pages.github.com) provides free and simple hosting for static sites, which makes it perfect for this use-case. Github recommends using Jekyll.
