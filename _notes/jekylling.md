---
layout: post
title:  "Setting up your GitHub Pages site locally with Jekyll"
date:   2017-05-30 05:18:13 -0400
categories: jekyll github-pages
---
The instructions for [Setting up your GitHub Pages site locally with Jekyll][local-jekyll] left me a bit befuddled. Here's how I did it, after a bit of trial and error:

- Create a repo named <user>.github.io and cd to it.
{% highlight shell %}
git init wfm.github.io
cd wfm.github.io
{% endhighlight %}

- Create a file named Gemfile containing:
{% highlight yaml %}
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
{% endhighlight %}

- Install the gems.
{% highlight shell %}
bundle install
{% endhighlight %}

- Generate the jekyll site files. Use --force to replace the Gemfile from step 2 with the one you will use going forward.
{% highlight shell %}
bundle exec jekyll new --force .
{% endhighlight %}

- Build and serve your new site.
{% highlight shell %}
bundle exec jekyll build
bundle exec jekyll serve
{% endhighlight %}

- Open http://127.0.0.1:4000/ in a web browser.

- In your GitHub.com account, create an empty repo named <user>.github.io.

- Connect the local repo to GitHub, commit your changes locally, and push them to GitHub.
{% highlight shell %}
git remote add origin https://github.com/wfm/wfm.github.io
git add .
git commit -m "barebones GitHub pages site with local Jekyll setup"
git push -u origin master 
{% endhighlight %}

I am new to Jekyll and GitHub, so there may be better ways to do all this (and to format this note).

[local-jekyll]: https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/
