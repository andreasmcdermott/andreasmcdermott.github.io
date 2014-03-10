---
  layout: post
  title: Fun with Firebase
  categories: [ web ]
  tags: [ js, firebase ]
---
I've been playing around with [Firebase](http://www.firebase.com) the last couple of weeks. 
They offer a hosted document database service that allows for real time (or almost at least) syncing of data very easily.

This makes it perfect for chats and similar. I'm currently experimenting with two different projects using their service.

### A game
I'm making a small two player turn-based game that will be playable in the browser. 
Firebase seems perfect for this since it will allow me to sync data easily in almost realtime. I'll update my
blog with more information when I get a bit further.

### A web application
The second project is a web application without any need for syncing data in realtime. It might seem weird to choose
a service who's main selling point is the syncing for this, but Firebase also offers another feature that is really cool:
authorization. Firebase can handle user accounts (either by allowing users to signup using email and password, 
or by allowing user to use their Github or Twitter accounts). This means that I can create a secure web application without the
need for any server code. This is great and a lot of fun! It of course has its limitations 
since anything I would normally do on the server, except authorization, can't be done. The good thing is that if I want
to be able to send emails or anything else in the future I can just add a server that uses the same data store. Because of 
the great syncing feature it will be updated automatically when changes happen and can take action.
