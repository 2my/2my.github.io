---
title: "Mac (dev) trick: svn"
categories: [mac]
layout: "posts"
date: "2008-03-07 22:15:00"
updated: "2008-03-08 19:48:15"
blogger:
    siteid: "36955474"
    postid: "1984039954556244459"
---

Subversion is included with XCode and documented in XCodeUserGuide. Excerpt:

	1 svnadmin create /Volumes/LACIE/svnrep
	2 svn import -m "prosjekt for jobbsøk" /Users/tommy/Documents/Projects/archive/mycontacts file:///Volumes/LACIE/svnrep/mycontacts
	3 svn checkout file:///Volumes/LACIE/svnrep/mycontacts mycontacts

Added project "HobbyCode" as well, poms do not work yet - need to mkdir target...
