---
created_at: 2010-11-21
excerpt: Favbuster is a Ruby script which purges all your Twitter Favorites.
kind: article
publish: true
tags: [ruby, twitter, script]
title: "Favbuster"
---

Favbuster is a Ruby Script which "un-favorites" all the tweets you marked as favorite. While on the go I favorite tweets as some kind of bookmarking mechanism. Later at home I can check out the links of those favs or write a reply.

For me, this workflow has the nice side-benefit of heavily minimizing the time I spend with Twitter, thus eliminating another potential time sink.

The script walks you through the Twitter OAuth setup.

This is how you use it:

    ruby favbuster.rb 
    deleting the following tweets:
               igrigorik: great article on MySQL vs Postgres replication under the hood: http://bit.ly/aKqfQx
                 defunkt: "An ActiveModel-compliant persistence framework for Ruby that uses Git for versioning and remote syncing." — http://is.gd/hsNWD


Visit the [Favbuster Repository](https://github.com/sohooo/favbuster) on Github.
