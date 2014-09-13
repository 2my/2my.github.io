---
title: "MarkDown Library Search"
categories: [doc]
layout: "post"
date: "2013-08-13 08:17:00"
updated: "2013-08-13 08:17:18"
blogger:
    siteid: "7706585097329252419"
    postid: "5020623696062838287"
---

To no avail so far.

I would really like to use [MultiMarkDown][MultiMarkDown] because Byword and Scrivener uses it and I like the dialect. Now, if I only could find a library that lets me generate a site from MarkDown files in my project... I searched libraries on the [Markdown Community Page][markdown] library list. None fit the bill in june 2013.

This <a href="http://stackoverflow.com/questions/15402512/whole-site-compilation-of-markdown-pandoc/15402977">thread on Stack Overflow</a> lists some options, mostly for PanDoc.

<a href="http://johnmacfarlane.net/pandoc/index.html">PanDoc</a> is a nice runner-up, seems to have more utilities:

<a href="https://github.com/jgm/pandoc/wiki/Pandoc-Extras">Pandoc-Extras</a> lists editors, libraries, scripts, generators...

<a href="http://www.blogger.com/org.pegdown%20/%20pegdown%20/%201.4.0%20https://github.com/sirthias/pegdown">PegDown</a> seemed OK, but turns out it picks extensions from different dialects.

Of the Java libraries: <a href="https://code.google.com/p/markdown4j">Markdown4j</a> will implement PanDoc extensions, <a href="http://markdownj.org/">MarkdownJ</a> seems deserted.

Maven uses <a href="https://github.com/rjeschke/txtmark">TxtMark</a>: com.github.rjeschke / txtmark / 0.10

Play uses <a href="http://markdown.tautua.org/">Tatua</a>: org.tautua.markdownpapers/markdownpapers-core /1.3.4 / (in play)


  [MultiMarkDown]: http://multimarkdown.com/  "MultiMarkDown site"
  [markdown]: http://markdown.github.io/
