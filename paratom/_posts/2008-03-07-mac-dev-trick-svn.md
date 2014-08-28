---
title: "Mac (dev) trick: svn"
layout: "post"
permalink: "/2008/03/mac-dev-trick-svn.html"
uuid: "1984039954556244459"
guid: "tag:blogger.com,1999:blog-36955474.post-1984039954556244459"
date: "2008-03-07 22:15:00"
updated: "2008-03-08 19:48:15"
description: 
blogger:
    siteid: "36955474"
    postid: "1984039954556244459"
categories: 
author: 
    name: "Tommy"
    url: "http://www.blogger.com/profile/16604372255669213767?rel=author"
    image: "http://static.flickr.com/93/279356255_fb52db20a0_o.jpg"
---

<div class="css-full-post-content js-full-post-content">
Subversion is included with XCode and documented in XCodeUserGuide. Excerpt:
<ol><li>svnadmin create /Volumes/LACIE/svnrep</li><li>svn import -m "prosjekt for jobbsøk" /Users/tommy/Documents/Projects/archive/mycontacts file:///Volumes/LACIE/svnrep/mycontacts</li><li>svn checkout file:///Volumes/LACIE/svnrep/mycontacts mycontacts</li></ol>Added project "HobbyCode" as well, poms do not work yet - need to mkdir target...
</div>