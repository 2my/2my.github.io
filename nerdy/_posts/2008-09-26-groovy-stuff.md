---
title: "Groovy stuff"
categories: 
layout: "post"
date: "2008-09-26 12:04:00"
updated: "2008-12-01 13:21:58"
blogger:
    siteid: "7706585097329252419"
    postid: "5170221297213836715"
---

### <big>Groovy is:</big>

	* Ruby for Java developers and JVM
	* What Java should be (groovy extends Java)
	* Native Beans (auto-generated get'ers and set'ers)
	* Lots of small and big improvements to language and libraries
	* Meta-programming provides method injection, interception and supports dsl-generation  

### Or, according to <a href="http://groovy.codehaus.org/">themselves</a> (Gloss over)
is an agile and **dynamic language** for the **Java Virtual Machine**

	* Dynamic = kall til fx writeToFile() feiler først runtime =&gt; må teste all kode. Polymorfisme ikke bundet til arv
builds upon the strengths of Java but has **additional power features** inspired by languages like Python, Ruby and Smalltalk

	* Mange tilegg til collections, xml-support, db-dsl-features 
makes **modern programming features** available to Java developers with **almost-zero learning curve**

	* Closures and Meta-programming (method intercept, inject, synthesize 
supports **Domain-Specific Languages** and other compact syntax so your code becomes **easy to read and maintain**

	* Via meta-programming: **5.times { println "Hello world" }** 
makes writing shell and build scripts easy with its **powerful processing primitives**, OO abilities and an Ant DSL

	* GAnt = ant-script skrevet i Groovy (ikke xml) 
increases developer productivity by **reducing scaffolding code** when developing web, GUI, database or console applications<span style="font-weight: bold;">

</span>**simplifies testing** by supporting unit testing and mocking out-of-the-box

seamlessly **integrates with all existing Java objects and libraries**

	* Kan kalle frem og tilbake  
	* Joint compiler compiles <span style="font-weight: bold;">straight to Java bytecode</span> so you can use it anywhere you can use Java

## Hands dirty, now!
```
/**
cd C:\Pirate\my_projects\HobbyCode\Groovy\HelloEclipse
set CP=target\classes;%GROOVY_HOME%\embeddable\groovy-all-1.5.6.jar
java -cp %CP% AllCode
* @author tsk
*/

String message = "\n\n\n\n********  Velkommen! ********";
System.out.println( message )
System.out.println 'This is a "Hello World" application'

def duckTypedString = "You have already seen such Groovy stuff as:"
println duckTypedString

println(
'''klasse og main() er implisitt definert hvis ikke du gidder
Heredocs (""" eller \''')
May use " or ', whatever suits you best

Valgfritt:
* semikolon
* parentes
* datatype (duck typed)
* exception handling
'''
)

println "Ingen primitive datatyper: " + 1.getClass()
println "\n\n********  GString and non-default class / main  ********"
// java -cp %CP% org.dotme.learn.groovy.AutomaticallyCreatedAbove
public class AutomaticallyCreatedAbove {
	public static void main( String[] args ) {
		String input = "GString demo"
		if ( args ) { // Groovy truth...
			input = args[0]
			println "cmd /c groovy -h".execute().text
		}
		println "$input ${input.length()}"
	}
}

println "\n\n********  Calling Java, and back  ********"
org.dotme.learn.groovy.JavaClass javaClass = new org.dotme.learn.groovy.JavaClass();
println javaClass.message();
println "java -cp %CP% org.dotme.learn.groovy.JavaClass"
String messageToJava() {
"Hello from Groovy"
}

println "\n\n********  Metodepeker, Closure, operator overloading, automatic imports  ********"
def demoMethodPointer = AllCode.&amp;main
if ( ! args )
demoMethodPointer( "peker til main-metoden" )
File outFile  = new File( "TEXTFILE.txt" )
def println = { text -> // parameter in
outFile << a ="=">>
"""
println = System.out.&amp;println

println "\n\n********  Groovy beans  ********"
class ClassWithGeneratedGetSet {
def exposedProperty
private String privateSupressGetSet
final String readOnly

ClassWithGeneratedGetSet( String inProperty , String inReadOnly = "Tommy" ) {
exposedProperty = inProperty
readOnly = inReadOnly
}
}

ClassWithGeneratedGetSet obj = new ClassWithGeneratedGetSet( "Programming" );
println obj.getReadOnly()
println obj.exposedProperty
obj.setProperty "exposedProperty" , "Groovy recipies"
def prop = "exposedProperty"
println obj."${prop}"

println "\n\n********  Dynamically typed  ********"
println DynamicTypeTester.getSize( new DynamicType() )
println DynamicTypeTester.getSize( 1 )
println DynamicTypeTester.getSize( null )

class DynamicType {
	int size( ) {
		1
	}
}

class DynamicTypeTester {
	static int getSize( Object lst ) {
		if ( lst?.metaClass?.respondsTo( lst , 'size' ) )
			return lst.size()
		0
	}
}

println "\n\n********  Meta programming  ********"
family.injectedMethod = { entries ->
	family.putAll entries
}

family.injectedMethod( [ trickToResolveCallsToMeAndYouAbove : "methodMissing()" ] )
println family.trickToResolveCallsToMeAndYouAbove

Integer.metaClass
Integer.metaClass.ogsåIJava = { println "Kan legge til metoder i Java klasser" }
2.ogsåIJava()

def interceptedMethodObj = new MethodInterceptDemo();
interceptedMethodObj.unsuspectingVictim()
interceptedMethodObj.nonExistingMethod()

class MethodInterceptDemo implements GroovyInterceptable {
	def invokeMethod( String methodName , args ) {
		System.out.println "before call to $methodName"
		def method = MethodInterceptDemo.metaClass.getMetaMethod( methodName , args )
		method?.invoke( this , args )
		System.out.println "after call to $methodName"
	}
	def unsuspectingVictim() {
		System.out.println "in unsuspectingVictim"
	}
}

println "\n\n********  XML  ********"

/***
* Excerpted from "Programming Groovy",
* published by The Pragmatic Bookshelf.
* Copyrights apply to this code. It may not be used to create training material,
* courses, books, articles, and the like. Contact us if you are in doubt.
* We make no guarantees that this code is fit for any purpose.
* Visit http://www.pragmaticprogrammer.com/titles/vslg for more book information.
***/

URL u = getClass().getResource( 'languages.xml' )
languages = new XmlParser().parse ( u.toExternalForm() )
println "Languages and authors"
languages.each {
	println "${it.@name} authored by ${it.author[0].text()}"
}

def languagesByAuthor = { authorName ->
	languages.findAll {
		it.author[0].text() == authorName
	}.collect {
		it.@name
	}.join(', ')
}

println "Languages by Wirth:" + languagesByAuthor('Wirth')

println "\n\n********  Mange måter å loope  ********"
for(i in 0..2) { println 'ho ' }
1.upto( 3 ) { println "$it gang 1.upto( 3 )" }
3.times { println "$it gang 3.times" }
0.step(10, 2) { println "$it gang 0.step(10, 2)" }

println "\n\n********  Collections  ********"

HashSet set = [
	"merk at {} er for closures" ,
	"hei" ,
	"closure som siste parameter..."
] as HashSet

set.each( {println it} )
println set*.toUpperCase() // spread operator

ArrayList list = [ 1 , 2 ]
list <<>
println "på plass $i står $tall"
}

Map family = [
	me : "Tarzan" ,
	you : "Jane"
]

println family.get( "me" )
println family.you

```
