---
layout:post
title:introduction
---

Now I will give you an introduction to build my personal blog, I used ***GitPages + jeklly*** template *Not Pure Poole* method to achieve that.In this process I used ***SSH*** to transfer local files to GitHub, ***VSCode*** to compile, ***Typora*** to compile the Markdown files.

## Installation

You can choose one of the following methods to install Not Pure Poole:

Directly specify the not-pure-poole gem.

Add gem 'not-pure-poole' into your Gemfile.

Add the below lines into your _config.yml.

plugins:
  - not-pure-poole
If your site is hosted on GitHub Pages, you can use jekyll-remote-theme to import the master branch of Not Pure Poole.

Add gem 'jekyll-remote-theme' into your Gemfile.

Add the below lines into your _config.yml.

plugins:
  - jekyll-remote-theme

remote_theme: vszhub/not-pure-poole
Usage
You can read this example post to see the rendering result in this theme, and put the source aside to learn some basic usages.

## Configuration

The _config.yml file in this repository already contains some variables, you can try to override them in your repository.

Customizing Head
Not Pure Poole leaves a placeholder to allow defining custom head, in principle, you can add anything here, e.g. favicons. All you need to do is just creating a file _includes/custom-head.html and put data into it.

Creating Themes
If you want to make your own color schemes, modify the CSS variables in the _sass/_variables.scss stylesheet with a scoped data attribute or class name.

For example, below we've created the beginnings of a blue theme:

// Example blue theme
[data-theme="blue"] {
  --body-bg: var(--blue);
  --body-color: #fff;
}
Then, apply the theme by adding data-theme="blue" to the <html> element.

Customizing Navigation
You can create a file _data/navigation.yml to configure links to some pages. For example,

- title: Blog
  url: /
- title: About
  url: /about/
  Customizing Cover Image
  You can set your own cover image by modifying the cover_image variable in _config.yml, and you can also set different cover images on different pages by setting the cover_image variable on each page.

If you discover that the contrast between the cover text color and the cover background color is not enough, you can also adjust these two variables:

cover_bg_color: rgb(40, 73, 77)
cover_color: rgb(255, 255, 255)
Customizing Social Links
You can set your social links in _data/social.yml. You can custom titles, URLs, and icons (only support Font Awesome currently), for example:

- title: Email
  url: mailto://vszhub@gmail.com
  icon: fas fa-envelope
- title: Twitter
  url: https://twitter.com/vszhub
  icon: fab fa-twitter
- title: GitHub
  url: https://github.com/vszhub/not-pure-poole
  icon: fab fa-github
  Enabling Posts Archive
  Not Pure Poole supports posts archive by date, categories, and tags. For enabling that, you should put some data like below into _data/archive.yml:

- type: dates
  title: Dates
  url: /dates/
- type: categories
  title: Categories
  url: /categories/
- type: tags
  title: Tags
  url: /tags/
  After that, the navigation to these archive pages would be shown on the top of the homepage.

Then, you can create a category archive page, and set the below parameters on that page:

---
layout: archive-taxonomies
type: categories
---
Or a tag archive page:

layout: archive-taxonomies
type: tags
Or archive by dates:

layout: archive-dates
Enabling TOC
If you want to show the TOC of a page on the right side, just set toc: true on that page.

Enabling MathJax
If you want to write mathematics on a page, just set math: true on that page to enable MathJax.

Something More
Just hack into the code and see what you can get.

Development
To set up your environment to develop this theme, run bundle install.

Your theme is setup just like a normal Jekyll site! To test your theme, run bundle exec jekyll serve and open your browser at http://localhost:4000. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in _layouts, _includes, _sass and assets tracked with Git will be bundled. To add a custom