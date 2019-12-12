---
title: "Proxtop"
date: 2015-09-25
---

Repository: [Here](https://github.com/kumpelblase2/proxtop)

![Proxtop Logo](https://raw.githubusercontent.com/kumpelblase2/proxtop/master/static/assets/proxtop_logo_256.png)

Proxtop evolved out of my desire to be notified of new anime episodes being available instead of manually having to check for new releases by going to the website. I had already done some small server side scripts that did this for me, but I thought that if I wanted to make this available to other people, a server application isn't gonna cut it. You can see that project [here](https://github.com/kumpelblase2/proxer-watchlist-push).

So instead of a server application, proxtop had to be a client application. While I didn't (and still don't) like the idea behind electron, I wanted to get the project working and not spend weeks getting into qt so I reluctantly chose it. I could've gone with NW.js, but that relied on the idea of a single window and tossed the main process. But in my case, I actually wanted a main (background) process to do all the fetching work so it didn't make sense to go that route. Another reason for chosing electron was that I already had code that parsed the page and did the update checks in js ready because of the previous project.

At the time, there was no API from the page available so I had to do manual parsing of the returned html which was a rather mundane task and I'm happy that over time, an API got developed and deployed to the page. That however meant that I had to redesign some parts of the application to adapt to that API instead. It was around this time where I also consumed less and less anime and thus having less and less reason to continue developing it (because I didn't use it myself).

When I initially started the project I didn't know about typescript yet and initially didn't use a bundler/transpiler anyway to keep the deployment more straight forward. Because of not having any clear definitions of what structures looked like, since JS is lacking that, development also became cumbersome because the properties of an object weren't clear and had to be looked up each time. In hopes that solving that problem would re-ignite my interest I started work on migrating to typescript to combat that shortcoming. However, the initial conversion took longer than I anticipated and I lost interest given the work was boring with no direct benefit. After months I eventually finished the conversion but have yet to progress much further because the updating mechanism is hard to test and I wouldn't want to deploy an update without making sure that the mechanism still works. So that's why it's still stuck where it is right now...
