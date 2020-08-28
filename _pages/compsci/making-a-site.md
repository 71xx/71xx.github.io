---
layout: single
author_profile: true
permalink: /compsci/site-guide
toc: true
title: Guide to making a Static Site with Github Pages
toc_label: "Contents"
toc_icon: "fab fa-fw fa-th-list"
---

## What is Static Site and why Jekyll

A static site is a website that is generated and built before it is served up to the world on a web server, this means it is light on resources, lightning fast and very responsive. Jekyll is a static site generator written in ruby and it officially supported by GitHub Pages, you can read more about that [here](https://jekyllrb.com/). It is somewhat easy to set-up but as mentioned below, you need some knowledge with `Git` and GitHub to set this up properly.

## Prerequisites
* Some basic knowledge of the terminal and how to use git
* [Git for Windows](https://git-scm.com/download/win)
* A code / text editor, my choice is [Sublime Text 3](https://www.sublimetext.com/3)
* A GitHub Account - [Register Here](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home)
* [Ruby DevKit](https://rubyinstaller.org/)

## Creating a Repo

Firstly, head over to [GitHub](https://github.com), sign in and hit the plus button next to your avatar, or go to [github.com/new](http://github.com/new). Now name your repo, `<username>.github.io` and make sure it has a README.

![](/images/site-article/2020-08-28%2011_03_26-Create%20a%20New%20Repository.png)

### Cloning the Repo

Now that you have a repo, go ahead and clone it to your computer, for this you will need `git` installed and access to a `terminal / powershell` session. 

![](/images/site-article/repo.png)

![](/images/site-article/clone-1.png)


## Installing Jekyll

Now that we have a local copy of our repo we can begin by creating a new [Jekyll Site](https://jekyllrb.com/)

First we need to make sure that we have `ruby` installed, to do this type 

{% highlight ruby %}
ruby --version
{% endhighlight %}

This should return something that looks like this,

![](/images/site-article/ruby-v.png)

If so then we need to install, `bundler` and `jekyll`

{% highlight ruby %}
gem install bundler
gem install jekyll
{% endhighlight %}


## Installing our Theme - Minimal Mistakes

The theme we will be using is called [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) it is a flexible two column Jekyll theme with support for many different layouts and most importantly, support for GitHub Pages. To get started, we need to head over to the [GitHub Repo](https://github.com/mmistakes/minimal-mistakes) and download a `.zip` of the mater branch.

![](/images/site-article/mmistakes.png)

Now move all the files from the downloaded zip to your cloned repo folder.

![](/images/site-article/copy-files.png)

### Cleaning Up the Repo

Now that we have the necessary files, we can delete the unnecessary ones.
* .editorconfig
* .gitattributes
* .github
* /docs
* /test
* CHANGELOG.md
* minimal-mistakes-jekyll.gemspec
* README.md
* screenshot-layouts.png
* screenshot.png

![](/images/site-article/files-to-remove.png)

### Setting up the Gemfile

Now that we have all required files we need to start editing some of them, open the `Gemfile` with a text editor of your choice, then replace the contents with the following.

{% highlight ruby %}
source "https://rubygems.org"

# Hello! This is where you manage which Jekyll version is used to run.
# When you want to use a different version, change it below, save the
# file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
#
#     bundle exec jekyll serve
#
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!

# gem "github-pages", group: :jekyll_plugins

# To upgrade, run `bundle update`.

gem "jekyll"
gem "minimal-mistakes-jekyll"

# The following plugins are automatically loaded by the theme-gem:
#   gem "jekyll-paginate"
#   gem "jekyll-sitemap"
#   gem "jekyll-gist"
#   gem "jekyll-feed"
#   gem "jekyll-include-cache"
#
# If you have any other plugins, put them here!
group :jekyll_plugins do
end
{% endhighlight %}

Save the file and run `bundle install` in your terminal window to install all the required ruby gems.

![](/images/site-article/bundle-install.png)

Now we are ready to setup the site using the `_config.yml` file.

## Setting Up the Site

Open the `_config.yml` file in a text editor and change the fields to the correct and relevant information, making sure to uncomment the `remote theme` line, so it works properly with GitHub pages.

![](/images/site-article/config-1.png)

### Setting up the Author Profile

The author profile appears at the side of each post on your website and allows a reader to quickly find you on other platforms, it looks something like this.

![](/images/site-article/profile-1.png)

To set this up edit these fields in the config file.

![](/images/site-article/config-2.png)

### Setting Up the Footer 

To edit the footer, change these fields in the config file.

![](/images/site-article/config-3.png)

### Setting Defaults

Default are settings that are applied to every post or page on your site and it saves you time as it means you don't have to type this out each time you want to make a new post.

Below is what I use and recommend as defaults for posts.

{% highlight yaml %}
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      toc: true
      toc_label: "Contents"
      toc_icon: "fab fa-fw fa-th-list"
{% endhighlight %}

![](/images/site-article/config-4.png)


## Pushing the site to GitHub

Now that we have built the basics of the site we can push the files to GitHub, to do this we need to first add all the files with:

{% highlight powershell %}
git add .
{% endhighlight %}

![](/images/site-article/git-1.png)

Then we need to `commit` the files with a message that tells you what you have changed since the last commit, since this is our first commit we can just have a commit message that says, `initial commit`

{% highlight powershell %}
git commit -m "initial commit"
{% endhighlight %}

![](/images/site-article/git-2.png)

Then finally we need to push the committed changes to GitHub with `git push`, if this is your first time using git on Windows it may ask you to sign into GitHub before it can push the changes. 

{% highlight powershell %}
git push origin
{% endhighlight %}

![](/images/site-article/git-3.png)

If all went well you should now see your files in your GitHub Repo, and a small notification under the environments tab that says `github-pages` Active.

![](/images/site-article/git-4.png)

Your site is now live and you can view it by going to [username.github.io](https://71xx.github.io).


## Creating Your First Post

All the posts written for your site must either be written in `markdown` or `html` and placed inside of the markdown folder, I have a templet for writing posts available [here](https://drive.google.com/file/d/1qYmii8Nwg2FAINY6nYTi8D4h8unVPclv/view?usp=sharing), all you need to do it place it inside your `_posts` folder and it will be published automatically. Here is an example post in markdown for you to take a look at - [here](https://raw.githubusercontent.com/71xx/71xx.github.io/master/_posts/history/2020-08-26-German-Foreign-Policy.markdown). If you need help with markdown check out the [References Section](/compsci/references) and look in the Web Dev section for the markdown cheat sheet.

If you wish to view your site locally before pushing to GitHub you can run:

{% highlight powershell %}
bundle.bat exec jekyll serve
{% endhighlight %}

![](/images/site-article/jekyll-serve.png)

Once you have written a post just `git add .`, `git commit -m "message"`, `git push origin` and GitHub will publish the new post for you on your site.

## Conclusions

I hope this was at least an informative piece on how to fully set-up and use a Jekyll Site hosted on GitHub pages. If you have any further queries check out the [Minimal Mistakes Wiki](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) guide or the [Install Guide](https://mmistakes.github.io/minimal-mistakes/docs/installation/).