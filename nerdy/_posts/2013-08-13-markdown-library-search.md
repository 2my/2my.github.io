---
title: "MarkDown Library Search"
layout: "post"
permalink: "/2013/08/markdown-library-search.html"
uuid: "5020623696062838287"
guid: "tag:blogger.com,1999:blog-7706585097329252419.post-5020623696062838287"
date: "2013-08-13 08:17:00"
updated: "2013-08-13 08:17:18"
description: 
blogger:
    siteid: "7706585097329252419"
    postid: "5020623696062838287"
    comments: "0"
categories: [doc]
author: 
    name: "Tommy"
    url: "http://www.blogger.com/profile/16604372255669213767?rel=author"
    image: "http://static.flickr.com/93/279356255_fb52db20a0_o.jpg"
---


To no avail so far.

This is a sentence.[^1] and a footnote definition on its own line anywhere within the document

I would really like to use <a href="http://multimarkdown.com/">MultiMarkDown</a> because Byword and Scrivener uses it and I like the dialect. Now, if I only could find a library that lets me generate a site from MarkDown files in my project... I searched libraries on the <a href="http://markdown.github.io/">MarkDown library list</a>. But none fit the bill (in june 2013).
This <a href="http://stackoverflow.com/questions/15402512/whole-site-compilation-of-markdown-pandoc/15402977">thread on Stack Overflow</a> lists some options, mostly for PanDoc.

<a href="http://johnmacfarlane.net/pandoc/index.html">PanDoc</a> is a nice runner-up, seems to have more utilities:<br /><a href="https://github.com/jgm/pandoc/wiki/Pandoc-Extras">Pandoc-Extras</a> lists editors, libraries, scripts, generators...

<a href="http://www.blogger.com/org.pegdown%20/%20pegdown%20/%201.4.0%20https://github.com/sirthias/pegdown">PegDown</a> seemed OK, but turns out it picks extensions from different dialects.

Of the Java libraries: <a href="https://code.google.com/p/markdown4j">Markdown4j</a> will implement PanDoc extensions, <a href="http://markdownj.org/">MarkdownJ</a> seems deserted.

Maven uses <a href="https://github.com/rjeschke/txtmark">TxtMark</a>: com.github.rjeschke / txtmark / 0.10<br />Play uses <a href="http://markdown.tautua.org/">Tatua</a>: org.tautua.markdownpapers/markdownpapers-core /1.3.4 / (in play)<br />&nbsp; 

[^1]: This is a footnote.
