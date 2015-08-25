---
title: "Struts2: Quick and easy Wizard"
categories: 
layout: "posts"
date: "2009-05-14 11:34:00"
updated: "2009-05-14 12:06:57"
blogger:
    siteid: "7706585097329252419"
    postid: "6122336853172714143"
---

Use a wizard to fill in data piecewise. Spring web-flow (plugin) is recommended. An alternative is to use scope and ModelDriven interceptors together and have them use the same object. Here's the idea coded:

~~~~~~~~~~~~
public class SomeAction extends ActionSupport implements ModelDriven<somemodel> {
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
~~~~~~~~~~~~

NB! we're stuck with the object returned by getModel(), so we should only change it's content, not the object reference.

Action setup:

~~~~~~~~~~~~
<action name="someAction" class="SomeAction">
	<interceptor-ref name="scope">
		<param name="session">sessionModel</param>
	</interceptor-ref>
	<interceptor-ref name="defaultStack" />
	<result name="page1">/WEB-INF/jsp/page1.jsp</result>
	<result name="page2">/WEB-INF/jsp/page2.jsp</result>
</action>
~~~~~~~~~~~~

**Scope-interceptor will call setSessionModel()** with session data before other calls to Action (getModel, execute, validate), and after execute() returns **getSessionModel()** is called to get a new value to put in session.
