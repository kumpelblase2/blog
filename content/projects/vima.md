---
title: "Vima"
date: 2016-08-20
---

I have a big collection of videos that aren't movies or series (educational videos for example) which I'd like to organize so I can search for specific ones, track progress or make notes. Sadly, the only kind of software that is in this space are "Media Servers". I say "sadly" because those media servers are made for movies and tv shows where there's public metadata available that a server can provide in addition to streaming the video itself. However, for videos that aren't movies or shows, this rarely exists or isn't easily queryable. Because I couldn't find a software that satisfied my requirements, I started working on Vima.

Vima's main usecase is tagging videos with certain metadata and allowing the user to utilize that metadata to find the exact video he's looking for. It additionally allows the videos to be played and assembled to a playlist to avoid having to switch between applications. It takes inspiration from Plex in some areas though the main functionality remains unmatched.

There are different kinds of metadata that can be applied to a video, such as numbers, text, list of tags or list of values. The system itself doesn't apply much metadata by itself - only if you tell it to. This is in contrast to existing software (such as Plex or Emby) which try to fill a limited set of metadata that cannot be edited. You can easily addin custom plugins that react on system events to automate populating certain metadata or reacting to the values of other metadata entries.

I've chosen to use MongoDB because the metadata is highly variable and changes depending on the users needs, which I think make a document store the prime technology for this. I don't regret chosing this, but it has its downsides. For one, it's obviously a big break from conventional relation database and the tooling seems to be lacking compared to more standard solutions. Additionally, it requires a separate setup and cannot be bundled with the software itself which makes setup more cumbersome.

In addition to using more "dynamic" database I also chose Ruby to write the software in. Ruby was attractive because of its dynamic nature, it's available support for MongoDB and Rails being a well supported web framework. It definitely fit the bill for this project but also has issues, in similar vein to Mongo. Setting up a rails app as a user isn't great; having to install dependencies, having to figure out an app-server to run it inside - or using the rails cli - is rather unpleasant.

From a feature standpoint, Vima does it's job good enough. It has rough edges and is a little clunky, but it works. I am working on a different implementation though which solves many of the problems I had (especiall concerning deployment) with Vima, which will either fail or superceed the current Vima.

You can find the source and more information in the [GitHub repository](https://github.com/kumpelblase2/vima/).
