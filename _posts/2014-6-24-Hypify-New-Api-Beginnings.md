---
layout: posts
published: true
title: Hypify - Integrating new Spotify web API
tags:
  - Spotify
  - Web
  - API
  - Hypify
category: Blog
---

Starting to make the push to migrate to the new Spotify Web API on my Hypify Chrome extension.  Changing the lookups were trivial.  
A few properties have changed but no biggie.  I began working on login and auth last night, but it gave me a little more trouble.  
Granted I was watching <a href="http://www.imdb.com/title/tt1641384/?ref_=fn_al_tt_1">Young Justice</a> at the same time, but more on that later.
I wasn't really sure how to host my redirect URI from a chrome extension.  In the end I settled on letting github do the work, so my spotify redirects
will be coming here haha.  Now I need to work on 'persistent' auth tokens and doing some more js manipulations to HypeM's page.  Then, the fun will
begin when I can actually start adding tracks to user playlists!