---
title: "Regexp for logging of method calls"
categories: [testing]
layout: "post"
date: "2008-12-15 15:16:00"
updated: "2009-11-16 10:30:26"
blogger:
    siteid: "7706585097329252419"
    postid: "1879759498528346276"
---

<span style="font-size:130%;">BeanShell macros</span> (May be run in jEdit)

Copy and paste auto-generated method signature, and run this macro

<pre>

// rid of tabs, newlines and double spaces

strippSpace( String text ) {

 text    = text.replaceAll( "\\t" , " " );

 text    = text.replaceAll( "\\n?" , "" );

 do {

     text    = text.replaceAll( "  " , " " );

 } while ( text.indexOf( "  " ) > -1 );

 return text;

}

// tidy up method call

cleanCall( String text ) {

 text    = text.replaceAll( "\\(\\s*" , "(\n\t" );

 text    = text.replaceAll( ",\\s*" , ",\n\t" );

 text    = text.replaceAll( "\\s*\\)\\s*" , "\n)" );

 return text;

}

convertMethodSignature2SuperCall( String text ){

 // 2 strings before )

 text    = text.replaceAll( "\\w*\\W?(\\w*)\\W*\\)\\W*" , "$1 );" );

 // 2 strings before comma

 text    = text.replaceAll( "\\w*\\W?(\\w*)\\W*,\\W*" , "$1, " );

 // 3 strings before (

 text    = text.replaceAll( "\\A\\s*\\w*\\s?void\\s?(\\w*)\\s*\\(" , "super.$1(" );

 text    = text.replaceAll( "\\A\\s*\\w*\\s?\\w*\\s?(\\w*)\\s*\\(" , "return super.$1(" );

 return text;

}

convertMethodSignature2SillyReturn( String text ){

 // 2 strings before )

 text    = text.replaceAll( "\\w*\\W?(\\w*)\\W*\\)\\W*" , "$1 );" );

 // 2 strings before comma

 text    = text.replaceAll( "\\w*\\W?(\\w*)\\W*,\\W*" , "$1, " );

 // 3 strings before (

 text    = text.replaceAll( "\\A\\s*\\w*\\s?void\\s?(\\w*)\\s*\\(" , "" );

 text    = text.replaceAll( "\\A\\s*\\w*\\s?(\\w*)\\s?(\\w*)\\s*\\(" , "return new $1();" );

 return text;

}

convertMethodSignature2LogStatement( String text ){

 // 2 strings before )

 text    = text.replaceAll( "\\w*\\W?(\\w*)\\W*\\)\\W*" , "\n\t\tSEMAFOR_CALL \"$1\" SEMAFOR_COMMA $1 )\n\t);" );

 // 2 strings before comma

 text    = text.replaceAll( "\\w*\\W?(\\w*)\\W*,\\W*" , "\n\t\tSEMAFOR_CALL \"$1\" SEMAFOR_COMMA $1 )," );

 // 3 strings before parenthesis

 text    = text.replaceAll( "\\A\\s*\\w*\\s?\\w*\\s?(\\w*)\\(" , "\tSEMAFOR_CALL \"$1\" ," );

 // semafors

 text    = text.replaceAll( "SEMAFOR_COMMA" , "," );

 text    = text.replaceAll( "SEMAFOR_CALL" , "toXml(" );

 return text;

}

String text = Macros.input(view,"Method call:");

if(text == null || "".equals(text))

 return;

String text    = strippSpace( text );

String superCall    = convertMethodSignature2SuperCall( text );

String logCall    = convertMethodSignature2LogStatement( text );

String call    = cleanCall( text );

String res    = call + "{\n" + logCall + "\n\t" + superCall + "\n}";

Registers.setRegister('HistoryModel.getModel("clipboard").addItem(res);

view.getStatus().setMessageAndClear("OK - result on clipboard");

</pre>

<span style="font-size:130%;">Logging methods</span>

<pre>

public static String toXml( String name, Object value ) {

// FixMe: escape xml special characters

if ( value == null )

   value    = "";

return "\t<" + name + ">" + value.toString() + "<!--" + name + "-->";

}

/**  */

public static String toXml( String method, String... items ) {

String msg    = "";

if ( items != null &amp;&amp; 0 < msg    = "<">" + msg + "<!--" + method + "-->";

System.out.println( msg );

return msg;

},res);

HistoryModel.getModel("clipboard").addItem(res);

view.getStatus().setMessageAndClear("OK - result on clipboard");

<span style="font-size:130%;">Logging methods</span>

public static String toXml( String name, Object value ) {

// FixMe: escape xml special characters

if ( value == null )

   value    = "";

return "\t<" + name + ">" + value.toString() + "<!--" + name + "-->";

}

/**  */
public static String toXml( String method, String... items ) {
String msg    = "";
if ( items != null &amp;&amp; 0 < msg    = "<">" + msg + "<!--" + method + "-->";
System.out.println( msg );
return msg;
}
</pre>
