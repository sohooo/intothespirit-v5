---
created_at: 2010-11-21
kind: article
publish: true
tags: [ruby, twitter, script]
excerpt: Favbuster is a Ruby script which purges all your Twitter Favorites. The script is available on Github.
title: "Favbuster"
---

Favbuster is a Ruby Script which "un-favorites" all the tweets you marked as favorite. While on the go I favorite tweets as some kind of bookmarking mechanism. Later at home I can check out the links of those favs or write a reply.

For me, this workflow has the nice side-benefit of heavily minimizing the time I spend with Twitter, thus eliminating another potential time sink.

The script walks you through the Twitter OAuth setup.

This is how you use it:

    ruby favbuster.rb 
    deleting the following tweets:
                    khoi: How to Build a Simple Tumblr Blog with ExpressionEngine http://j.mp/erITos
                iamFinch: Bit.ly has a news feed now (à la Hacker news) http://bitlynews.com/
                      iA: Thank you Seth Godin: The inevitable decline due to clutter http://bit.ly/gL7lLZ
               czillgens: RT @miekd: Holy shit. This is just baffling. http://benthebodyguard.com/ (via @anthonyshort)
                     dhh: We got the "Why Ruby?" keynote up on a mirror now: http://bit.ly/faLCoj -- thanks to TekPub for putting it up.
               reederapp: Reeder for Mac 1.0 Draft 1 is now available at @madeatgloria http://madeatgloria.com/brewery
               maxvoltar: Currently browsing the @24ways archive http://bit.ly/fpdsI6 We as a community have come a long way, and are moving in the right direction.
               igrigorik: great article on MySQL vs Postgres replication under the hood: http://bit.ly/aKqfQx
                 defunkt: "An ActiveModel-compliant persistence framework for Ruby that uses Git for versioning and remote syncing." — http://is.gd/hsNWD


Visit the [Favbuster Repository](https://github.com/sohooo/favbuster) on Github.
