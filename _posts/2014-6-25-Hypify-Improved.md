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

Hypify is now taking advantage of the new Spotify API.  Query calls have been migrated to the new api and a new feature have been added.
After logging in to Spotify via their auth, you can now one click add a track directly to a selected Spotify playlist! You'll see that
after logging in and selecting a target playlist, all the magnifying glasses will turn into plus signs.  This feature is
the thing that I've wanted most, but I had to wait for Spotify's API team to catch up.  If you choose <i>not</i> to login, your query
action will remain the same as before.

Since the extension is purely client side, I don't get the pleasure of refresh tokens.  So, once the expire time of an hour is up, if 
you try to add to a playlist again the login dialog will pop up again.  Similarly everytime you open HypeM, you'll have to re-login with
your Spotify credentials, since the token is kind of useless to keep.

Some issues I had on the way...
Outstanding Issue:
1.  So I now have a reliable way of getting region info about the user.  Specifically in the user info call they tag each user with their country 
of origin.  Unfortunately at this point I've already filtered out tracks with non-US territories because I'd like to keep the simple query feature.
I supposed that could change in the future though.

Pains:
1.  After an hour realizing that I was sending a GET to add a track to a playlist instead of a POST #stupidme;
2.  Communications between my redirect URI and the content script.  Found that I really just needed to put my initalizers into a document ready
instead of global.

Things Hypify lacks right now:
1.  The ability to check if a track already exists on a playlist.  This just seems too heavy to implement right now.  So, you'll have to self managed.
2.  As mentioned prior, Everything is filtered by US territory, which is awful.  Also the Spotify metadata isn't even too accurate on that point.
Also I'll have to concede this point for now.

-Eric