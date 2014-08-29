---
title: "Struts2: Quick and easy Wizard"
categories: 
layout: "post"
date: "2009-05-14 11:34:00"
updated: "2009-05-14 12:06:57"
blogger:
    siteid: "7706585097329252419"
    postid: "6122336853172714143"
---

Use a wizard to fill in data piecewise. Spring web-flow (plugin) is recommended. An alternative is to use scope and ModelDriven interceptors together and have them use the same object. Here's the idea coded:

<pre>

public class SomeAction extends ActionSupport implements ModelDriven&lt;somemodel> {

    private SomeModel model;

    public SomeAction ( ... ) {

        model = new SomeModel( ... );

    }

    /** @see ModelDriven */

    public SomeModel getModel() {

        return model;

    }

    /** for scope interceptor */

    public SomeModel getSessionModel() {

        if ( ! clearSession )

            return model;

        clearSession    = false;

        return null;

    }

    public void setSessionModel( SomeModel newValue ) {

        if ( newValue == null )

            model.reset();

        else

            model.copyFrom( newValue );

    }

}

</pre>

<p>NB! we're stuck with the object returned by getModel(), so we should only change it's content, not the object reference.</p>    <p>Action setup:

</p><pre>&lt;action name="someAction" class="SomeAction">

&lt;interceptor-ref name="scope">

  &lt;param name="session"><span style="font-weight: bold;">sessionModel</span>&lt;/param>

&lt;interceptor-ref name="defaultStack" />

&lt;result name="page1">/WEB-INF/jsp/page1.jsp&lt;/result>

&lt;result name="page2">/WEB-INF/jsp/page2.jsp&lt;/result>

&lt;/action>

</pre>

**Scope-interceptor will call setSessionModel()** with session data before other calls to Action (getModel, execute, validate), and after execute() returns **get****Session****Model****()** is called to get a new value to put in session.
