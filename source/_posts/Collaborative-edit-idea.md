---
title: 'Collaborative edit: idea'
date: 2017-04-14 17:57:31
tags:
 - UX
 - Web
---
Often a web application allows simultaneous edit of the same entity for different users.
Usual approach is to either set a lock (horrible nowadays), or to inform the one who saved the last that "Entry was modified..." and propose to reconcile,
or just silently override (low class).

I just have thought: there can be explicit collaboration with WebSockets.
 * Show a label "It is being edited by Alice" to Bob so it's not a lock and expires;
 * When Bob starts editing Alice receives a message "Bob also works on this";
 * If Alice/Bob saves the changes then Bob/Alice sees them in immediate popup (don't wait until "Save");
 * With this "Alice has saved this item. Item details:..." popup Bob must reconcile;
 * Only in the rare case that both "Save changes" requests are indeed posted at the same time span Bob will get "Oops, please reconcile" dialog.

AFAIR this is something like Google Spreadsheet does. Very nice!
