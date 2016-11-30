---
title: "Publish! (JavaZone 2012)"
categories: 
layout: "posts"
date: "2012-08-18 09:45:00"
updated: "2012-09-13 21:45:45"
blogger:
    siteid: "7706585097329252419"
    postid: "2548992803867373958"
---

Lightning talk from JavaZone 2012. As promised here are the notes, with pointers to more information.

### Links to more information
Google code hosting: <a href="http://code.google.com/p/support/wiki/GettingStarted">Getting started</a>.

<a href="http://blog.fastconnect.fr/?p=275">Example pom</a> for Google hosted projects.

<a href="https://github.com/">GitHub</a> (getting started on front page).

<a href="https://github.com/kevinsawicki/github-maven-example">Example project / pom</a> for GitHub hosted projects.

Sonatype OSS Repository Hosting Service: <a href="https://docs.sonatype.org/display/Repository/Sonatype+OSS+Maven+Repository+Usage+Guide">Usage guide</a>.

<a href="http://jroller.com/holy/entry/releasing_a_project_to_maven">Blog post</a> with more details than the above (but not up to date)

<a href="http://maven.apache.org/guides/mini/guide-central-repository-upload.html">Guide</a> from Apache.

About <a href="http://opensource.org/licenses/category">Open Source Licenses</a>.

### Script
Welcome to this talk titled Publish! It is about publishing an Open Source project.  
I will try to convince you that this is not hard to do, and that you stand to benefit from doing such a thing.  
My name is Tommy Skodje  
I work for the consultancy <a href="http://www.antares.no/">Antares</a>, we have a stand out in the hall.  
I have programmed for some years now, but only yesteryear I opensourced my first project, <a href="http://code.google.com/p/test-data-control/">test-data-control</a>. A tool for exporting / importing data from database.  
That was a good experience, and I want to share this with you.  

### First version
Now for the 9 steps I took to publish the project.


<a href="http://3.bp.blogspot.com/-4JO4G0UDVQc/UFIu5_bAFHI/AAAAAAAAAE0/zVnqlTzsSx4/s1600/jz12_publish_first.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="400" src="http://3.bp.blogspot.com/-4JO4G0UDVQc/UFIu5_bAFHI/AAAAAAAAAE0/zVnqlTzsSx4/s400/jz12_publish_first.png" width="382" /></a>

<a href="http://2.bp.blogspot.com/-YjASWjT3iw8/UFIvkexm1pI/AAAAAAAAAFA/t09-1TFahMM/s1600/google_create_project.png" imageanchor="1" style="clear: right; display: inline !important; float: right; margin-bottom: 1em; margin-left: 1em; text-align: center;"><img border="0" height="122" src="http://2.bp.blogspot.com/-YjASWjT3iw8/UFIvkexm1pI/AAAAAAAAAFA/t09-1TFahMM/s200/google_create_project.png" width="200" /></a>
I created the project on Google Code Hosting and used project information to fill in Jira ticket on Sonatype OSS Repository Hosting Service.  
<a href="http://1.bp.blogspot.com/-Dw-H0BPI0Fk/UFIvjrtc2DI/AAAAAAAAAE8/iERu27rzj04/s1600/github_create_project.png" imageanchor="1" style="clear: right; float: right; margin-bottom: 1em; margin-left: 1em; text-align: center;"><img border="0" height="155" src="http://1.bp.blogspot.com/-Dw-H0BPI0Fk/UFIvjrtc2DI/AAAAAAAAAE8/iERu27rzj04/s200/github_create_project.png" width="200" /></a>
That´s how I asked Sonatype to create Maven repositories for me.  
There was not much to the creation forms - Googles is the big one with 6 fields (you have to select vcs and license).

<a href="http://3.bp.blogspot.com/-1zGPtP1_khs/UFIwEj_YjcI/AAAAAAAAAFM/hTyhj_S_oKs/s1600/sonatype_create_ticket.png" imageanchor="1" style="clear: right; float: right; margin-bottom: 1em; margin-left: 1em; text-align: center;"><img border="0" height="180" src="http://3.bp.blogspot.com/-1zGPtP1_khs/UFIwEj_YjcI/AAAAAAAAAFM/hTyhj_S_oKs/s200/sonatype_create_ticket.png" width="200" /></a>
Jira ticket needs the same information, plus urls to the project hosting, and groupId.  
I got a reply on the ticket, asking me to change groupId.  
So I did, and the next day my ticket was resolved and I could code and deploy my project to Maven repositories on Sonatype.

With this formalities around the project were done.  

### Releasing
After a while I was ready to stage a release - I did it using normal maven release procedure, which put my artifacts into Sonatypes Nexus.  
I then logged in to Sonatypes Nexus, found my repository and pushed 4 buttons to release my staging repository.  
The first time I released I commented my Jira ticket to let them know they should verify my project and turn on Maven Central synchronization if OK.  
The next day Jira mailed me the reply and I found my artifacts in Maven Central.

### Central Sync requirements
<a href="http://4.bp.blogspot.com/-lCuCYfcr73M/UFI1z0M-NII/AAAAAAAAAFc/iu0lx4RYkRM/s1600/Screen+Shot+2012-09-13+at+9.31.55+PM.png" imageanchor="1" style="clear: right; float: right; margin-bottom: 1em; margin-left: 1em;"><img border="0" height="240" src="http://4.bp.blogspot.com/-lCuCYfcr73M/UFI1z0M-NII/AAAAAAAAAFc/iu0lx4RYkRM/s320/Screen+Shot+2012-09-13+at+9.31.55+PM.png" width="320" /></a>
Before I could stage the first release, my pom needed at least the 12 lines on the left.  
Javadoc and source artifacts has to be produced.  
Artifacts signed using GPG.  
Sonatype helps by providing oss-parent pom that defines tasks related to releasing, and they give nice instructions about how to install and set up GPG signing.  
Project does not need to be Mavenized, but it needs a pom.

### Licensing
I chose Apache v2. Applying it is easy - added LICENSE and NOTICE files on top level, and comment all source files.  
NOTICE is for honoring inclusions - now that I published I needed to track licensing of libraries and code I include.  

### Subsequent versions
<a href="http://1.bp.blogspot.com/-auw3Ue1OzxA/UFI3RN69m9I/AAAAAAAAAFk/KjTxvkKSmdg/s1600/jz12_publish_subsequent.png" imageanchor="1" style="clear: right; float: right; margin-bottom: 1em; margin-left: 1em; text-align: center;"><img border="0" height="205" src="http://1.bp.blogspot.com/-auw3Ue1OzxA/UFI3RN69m9I/AAAAAAAAAFk/KjTxvkKSmdg/s320/jz12_publish_subsequent.png" width="320" /></a>
  After the first release, it got a lot easier.

  
### I should have
Project was almost coded ready when I took out the Jira ticket.  
Then I refactored package structure and pasted in Copyright all over.  
And then a complete rewrite in Scala…  

I would have been better off starting with the formalities and no code.  I chose a poor name - what a pity - project name is final. The other stuff is mutable.  

### Why
Curiousity and ambition got me started.   
I wanted to learn more about opensourcing, and show off me and Antares.  
<a href="http://www.flickr.com/photos/72906133@N00/5861074022/" imageanchor="1" style="clear: right; float: right; margin-bottom: 1em; margin-left: 1em;"><img border="0" height="133" src="http://farm6.staticflickr.com/5160/5861074022_9920f05177_n.jpg" width="200" /></a>
But I soon realized that Open Source programming differs from inhouse-projects in many respects.  
Theres was no restrictive firewall or policies. I could cod and commit whenever I had internet. I even submitted work from my iPhone.  
Schedules and pressures were not the same either. I felt more pressure to code cleanly than quickly.

<a href="http://www.flickr.com/photos/informant/3588559152/" imageanchor="1" style="clear: left; float: left; margin-bottom: 1em; margin-right: 1em;"><img border="0" height="150" src="http://farm3.staticflickr.com/2456/3588559152_c50dbffc09_m.jpg" width="200" /></a>
And with myself at the helm I could pursue my own agenda.  
<a href="http://www.artima.com/shop/programming_in_scala_2ed" imageanchor="1" style="clear: right; float: right; margin-bottom: 1em; margin-left: 1em;"><img border="0" src="http://www.artima.com/images/pins2Cover185x240.gif" /></a>
So I ported it to Scala.  
I had just read the book and wanted some practice.  
Clients would not mind implementation details.  
That was a big job, I have done several other small stunts.  
I now want to make a command-line utility of it that interpretes an external DSL.
There was a nice article in PragPub magazine that I am keen to follow up on, and I have also read too much about DSLs that I haven´t practiced yet.

And both should be a nice fit here.  
**I rarely get to do such things otherwise.**  

<a href="http://www.flickr.com/photos/72213316@N00/4320790255/" imageanchor="1" style="clear: left; margin-bottom: 1em; margin-left: auto; margin-right: auto;"><img border="0" height="200" src="http://farm5.staticflickr.com/4030/4320790255_345f473f1a_n.jpg" width="146" title="A Young Girl Reading, Jean-Honoré Fragonard"/></a>
Normally, on daytime projects, I stop and do research when there is a need.  Now, I can read stuff from the stream that may fit nicely, or that I really would like to try.  
And I can!  
Even if the project was «done» 2 months ago…

**Having a side project facilitated deeper learning.**  
<a href="http://www.flickr.com/photos/dvanzuijlekom/7324829530/" imageanchor="1" style="clear: right; float: right; margin-bottom: 1em; margin-left: 1em;"><img border="0" height="200" src="http://3.bp.blogspot.com/-RXASQmHAF-I/UFJBk2_-ivI/AAAAAAAAAGU/hlYHQh8PCtE/s200/LightBulb.png" width="145" /></a>
I tried to practice TDD from the start.  
Many a time I gave thanks to my former self for doing that! Automated tests made it a lot easier to code a little now and then.  
And also release quick changes that I needed on my daytime project.  
**That helped TDD click with me!**  

Going public was scary.  
More than once I pondered my craftsmanship.  
I did more beautifying, simplification, refactoring and testing than earlier.  
Slowed me first, but I improved.  
One day at work I realized I could do it, efficiently and confidently.

**Publishing my work has driven me to evolve.**  

<a href="http://no.wikipedia.org/wiki/Fil:Francisco_de_Goya_y_Lucientes_008.jpg" imageanchor="1" style="clear: right; margin-bottom: 1em; margin-left: auto; margin-right: auto;"><img border="0" height="200" src="http://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Francisco_de_Goya_y_Lucientes_008.jpg/441px-Francisco_de_Goya_y_Lucientes_008.jpg" width="146" title="El Afilador, Francisco de Goya" /></a>
Being my own client has been wonderful.  
I could sharpen my own tool and skills at the same time.  
API cumbersome or lacking? I improved it. More usable with each reuse.  

<a href="http://i.istockimg.com/file_thumbview_approve/6979130/2/stock-photo-6979130-when-will-i-grow-up.jpg" imageanchor="1" style="clear: left; float: left; margin-bottom: 1em; margin-right: 1em;"><img border="0" height="200" src="http://i.istockimg.com/file_thumbview_approve/6979130/2/stock-photo-6979130-when-will-i-grow-up.jpg" width="132" /></a>
Many revisits makes this feel like growing SW.  
And I gradually learned more about design, documentation and testing.  
Also because I forget stuff between iterations, and I can see better when I start with fresh eyes.

<a href="http://www.flickr.com/photos/derekgavey/6068317482/" imageanchor="1" style="clear: right; float: right; margin-bottom: 1em; margin-left: 1em;"><img border="0" src="http://farm7.staticflickr.com/6184/6068317482_cf2b5e8bcf_m.jpg" /></a>  

### Thank you
I really enjoy the project, tinkering with it, making it better every now and then, and learning by practicing. I would like to say thank you to Sonatype, Google, GitHub and all the other hosting sites for making this so convenient. And to Øystein Pettersen at Evry for telling me where I could get synchronization to Maven Central.
