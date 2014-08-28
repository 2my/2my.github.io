---
title: "Struts2: Quick and easy Wizard"
layout: "post"
permalink: "/2009/05/struts2-quick-and-easy-wizard.html"
uuid: "6122336853172714143"
guid: "tag:blogger.com,1999:blog-7706585097329252419.post-6122336853172714143"
date: "2009-05-14 11:34:00"
updated: "2009-05-14 12:06:57"
description: 
blogger:
    siteid: "7706585097329252419"
    postid: "6122336853172714143"
    comments: "0"
categories: 
author: 
    name: "Tommy"
    url: "http://www.blogger.com/profile/16604372255669213767?rel=author"
    image: "http://static.flickr.com/93/279356255_fb52db20a0_o.jpg"
---

<div class="css-full-post-content js-full-post-content">
<p>Use a wizard to fill in data piecewise. Spring web-flow (plugin) is recommended. An alternative is to use scope and ModelDriven interceptors together and have them use the same object. Here's the idea coded:</p><br /><br /><pre><br />public class SomeAction extends ActionSupport implements ModelDriven&lt;somemodel> {<br />    private SomeModel model;<br />    public SomeAction ( ... ) {<br />        model = new SomeModel( ... );<br />    }<br />    /** @see ModelDriven */<br />    public SomeModel getModel() {<br />        return model;<br />    }<br />    /** for scope interceptor */<br />    public SomeModel getSessionModel() {<br />        if ( ! clearSession )<br />            return model;<br />        clearSession    = false;<br />        return null;<br />    }<br />    public void setSessionModel( SomeModel newValue ) {<br />        if ( newValue == null )<br />            model.reset();<br />        else<br />            model.copyFrom( newValue );<br />    }<br /><br />}<br /></pre><br /><p>NB! we're stuck with the object returned by getModel(), so we should only change it's content, not the object reference.</p>    <p>Action setup:<br /></p><pre>&lt;action name="someAction" class="SomeAction"><br />&lt;interceptor-ref name="scope"><br />  &lt;param name="session"><span style="font-weight: bold;">sessionModel</span>&lt;/param><br />&lt;interceptor-ref name="defaultStack" /><br /><br />&lt;result name="page1">/WEB-INF/jsp/page1.jsp&lt;/result><br />&lt;result name="page2">/WEB-INF/jsp/page2.jsp&lt;/result><br /><br />&lt;/action><br /><br /></pre><br /><b>Scope-interceptor will call setSessionModel()</b> with session data before other calls to Action (getModel, execute, validate), and after execute() returns <b>get</b><b>Session</b><b>Model</b><b>()</b> is called to get a new value to put in session.
</div>