---
layout: post
title:  "How I set up the local jekyll site"
date:   2017-01-05 21:07:15 +0900
---

This is about how I first set up local jekyll site which was supposed
to be posted on github project pages.

first setp : jekyll new
-----------------------

I used `jekyll new` command for jekyll to automatically set up some
structure of jekyll pages.

```
$ jekyll new test-ghpages
```

This creates `test-ghpages` directory under current directory.
If you cd to the directory and list files you can see something like this.

```
$ ls
Gemfile       Gemfile.lock  _config.yml   _posts/       _site/        about.md      index.md
```

Modify default Gemfile and let Bundler do the job
-----------------------

If you look at Gemfile you can see something like this

```rb
# Hello! This is where you manage which Jekyll version is used to run.
# When you want to use a different version, change it below, save the
# file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
#
#     bundle exec jekyll serve
#
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!
gem "jekyll", "3.3.1"

# This is the default theme for new Jekyll sites. You may change this to anything you like.
gem "minima", "~> 2.0"

# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
# gem "github-pages", group: :jekyll_plugins
```

Because I wanted this to be used for github pages I modified a bit.
I Commented the line

```gem "jekyll", "3.3.1"```

and uncommented the line

```gem "github-pages", group: :jekyll_plugins```

and execute bundler install

```
$ bundle install
```

Caution!!
You need to remove `Gemfile.lock` beforehand.

I noticed that after this bundler install the list of gem (the result of command `gem list`) significantly increased.

I did bundler update just to make sure afterwards.

```
$ bundle update
```
