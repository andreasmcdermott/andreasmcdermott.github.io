---
layout: post
published: true
categories: web
tags: 
  - firebase
  - emberjs
  - Firelists
---

After playing with [AngularJs](http://angularjs.org) for some time I decided I wanted to try [EmberJs](http://emberjs.com) as well.

I've been wanting a good checklist app for a while (since I switched to iPhone and realized there was no app for Google Keep). So I decided to use Ember to create one. 

I've used [Firebase](http://firebase.com) previously and really liked it, so I decided to use it for the checklist as well. This also means that the checklist will update in real time which makes it perfect for sharing lists.

After about a week of on-and-off work I have gotten a result that I'm pretty happy with. There are still a few features I plan on adding (and probably bugs that need fixing and some various other improvements), but it is good enough to use at this point.

**Current features are:**
- A user can create new lists. All lists are viewable by anyone with the url.
- Users can log in using there Google/Github/Twitter account. Logged in users can bookmark lists so that they won't have to remember the url (which is otherwise the only way to get back to a list).
- A logged in user can choose to lock a list he/she created. The list can still be viewed by anyone with the url, but only the creator can edit it.

**Features I plan on adding:**
- Sorting list items.
- Paste a paragraph of text and make each line into a seperate item (the feature I liked most with Google Keep).

Because this was my first time using Ember there might also be quite a bit of code that could be improved. I will hopefully be able to improve it as I get better at Ember.

You can try it out here: [Firelists](http://firelists.github.io). If you do, please let me know what you think!