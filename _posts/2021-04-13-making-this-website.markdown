---
layout: post
title:  "Making this website!"
date:   2021-04-13 20:43:00 -0400
categories: jekyll 
---

Making a personal website, especially to host a portfolio of projects, is becoming increasingly common. Utilizing [GitHub Pages](https://docs.github.com/en/pages) and [Jekyll](https://jekyllrb.com/) as I have here is a wonderfully simple way of getting yourself up and running with a website with little coding necessary.

## Prerequisites

1. A GitHub account&mdash;these are free to create!
2. A text editor ([Sublime Text](https://www.sublimetext.com/) or [VS Code](https://code.visualstudio.com/) are both free and popular options supported on Windows and Mac).

_Not required (but suggested):_

3. Some familiarity with [markdown](https://www.markdownguide.org/cheat-sheet/).
4. Some experience running commands in the terminal.
5. Knowledge of how to use [Git](https://guides.github.com/activities/hello-world/) to make iterative changes to your website over time.

## Step-by-step tutorial

### Setup your version control

First, you will need to [create a repository](https://docs.github.com/en/github/getting-started-with-github/create-a-repo) for your new website, which will follow this naming pattern: `YOURGITHUBUSERNAME.github.io`, so mine for example was [`samgaudet.github.io`](https://github.com/samgaudet/samgaudet.github.io).

Next, you will want to clone this repository locally, to make it easy to make changes to your website over time. Here is roughly what you need to do, though I will not go into great detail about [using Git]() here:

* Ensure that you have [installed Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) on your computer (if you are a Mac user, this is usually installed for you already).

* Create a folder in which you would like to house your local copy of your website files&mdash;on my computer, I have a `git` folder where I keep all my local repositories.

* Navigate to this folder in terminal&mdash;this will require opening Terminal / PowerShell / CMD or some other interface where you can execute Git commands. It should look something like this:  

{% highlight bash %}
cd C:\Users\yourusername\Documents\git\
{% endhighlight %}

* [Clone the repository](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository) to your local folder:  
  
{% highlight bash %}
git clone git@github.com:samgaudet/samgaudet.github.io.git
{% endhighlight %}

* Open GitBash, Terminal, or some other means of using Git commands in that repository you have just cloned. You should see that you are on the default branch of your repository, likely either `main` or `master`.

* Checkout a new branch for your development work that we will later merge into your default branch:  
  
{% highlight bash %}
git checkout -b some_descriptive_branch_name
{% endhighlight %}

### Install Jekyll and generate your template

Feel free to follow [GitHub's own documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll) on this step.

You will need to install the following things:

* [Install Ruby](https://www.ruby-lang.org/en/documentation/installation/).
* [Install Bundler](https://bundler.io/).

After installing `Jekyll`, confirm you are in your repository's root in Terminal or PowerShell, and run:

{% highlight bash %}
jekyll new .
{% endhighlight %}

### Configuration

This site is configured via the `_config.yml` markdown file in the directory root. Config files for markdown-generated sites are common with many prolific frameworks, such as Jekyll (this one!) or Mkdocs. While a yml format can feel unfamiliar or new, it's simply a way to declare various constants, configurations, settings, and plugins for your site.

{% include note.html content="Fun fact: `YAML` simply stands for _yaml ain't markup language_&mdash;a nice, recursive name :weary:" %}

### Starting up your development server

Once everything is installed and you have setup your basic configuration, it's as simple as running:

{% highlight bash %}
bundle exec jekyll server
{% endhighlight %}

And with this command, you'll have a local, self-refreshing version of your site running on your `localhost` (or 127.0.0.1).

{% include tip.html content="Make sure you're running this command in the `docs` folder of your repo, or else you'll get an error from jekyll that it's unable to find the files it needs." %}

-test-
