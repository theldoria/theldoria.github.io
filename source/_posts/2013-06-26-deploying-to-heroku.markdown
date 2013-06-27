---
layout: post
title: "Deploying to Heroku"
date: 2013-06-26 11:52
comments: true
categories: 
---
To add a new heroku app simply call:
    heroku create

You now should have a heroku remote. Check with:
    $ git remote -v

You can set heroku to be the default remote for push/free:
    $ git config branch.master.remote heroku

You can deploy with:
    $ git push heroku master

If you encounter the error `Permission denied (publickey).` while pushing, you may have to add your public key:
    $ heroku keys:add ~/.ssh/id_rsa.pub

