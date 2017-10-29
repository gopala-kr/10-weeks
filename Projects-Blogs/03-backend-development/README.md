

## case study : backend development
***********************
* java --> sprinframework
* php --> laravel
* ruby --> rails & sinatra
* python --> flask & django
* rust --> iron
* elixer --> phoenix
* golang web framework
****************************

In this article my main focus is  on backend web frameworks(an overview) in different languages, and their offerings, project structure,  popularity(less time-less code-better performance).

There are hundreds of frameworks out there, built to make web development easier. Every year there will be releases on new frameworks/improvements over existing ones. Below figure shows how the web frameworks have been evolved since from dot-com bubble. 

********************
**a look into brief history of web frameworks** 
----------------
<br>

![webframeworks](https://raw.githubusercontent.com/mraible/history-of-web-frameworks-timeline/master/history-of-web-frameworks-timeline.png)



****************

## MVC - design pattern

MVC is a software architectural pattern for implementing user interfaces to decouple code, which improve overall quality of software.

Model-view-controller (MVC) frameworks are a crucial part of building modern web applications. Walk into a room of web developers, and you will likely be bombarded with mentions of Ruby on Rails, Angular or Django.

More generally, MVC logic can be used to describe almost any web development process that uses a language like PHP, Ruby, Python or JavaScript.

> **Brief history of MVC**

> One of the seminal insights in the early development of graphical user interfaces, MVC became one of the first approaches to describe and implement software constructs in terms of their responsibilities.

> Trygve Reenskaug introduced MVC into Smalltalk-76 while visiting the Xerox Palo Alto Research Center (PARC) in the 1970s. In the 1980s, Jim Althoff and others implemented a version of MVC for the Smalltalk-80 class library. Only later did a 1988 article in The Journal of Object Technology (JOT) express MVC as a general concept.

> The MVC pattern has subsequently evolved, giving rise to variants such as hierarchical model–view–controller (HMVC), model–view–adapter (MVA), model–view–presenter (MVP), model–view–viewmodel (MVVM), and others that adapted MVC to different contexts.

> The use of the MVC pattern in web applications exploded in popularity after the introduction of NeXT's WebObjects in 1996, which was originally written in Objective-C (that borrowed heavily from Smalltalk) and helped enforce MVC principles. Later, the MVC pattern became popular with Java developers when WebObjects was ported to Java. Later frameworks for Java, such as Spring (released in October 2002), continued the strong bond between Java and MVC. The introduction of the frameworks Django (July 2005, for Python) and Rails (December 2005, for Ruby), both of which had a strong emphasis on rapid deployment, increased MVC's popularity outside the traditional enterprise environment in which it has long been popular. MVC web frameworks now hold large market-shares relative to non-MVC web toolkits.

> **Use in web applications**

> Although originally developed for desktop computing, MVC has been widely adopted as an architecture for World Wide Web applications in major programming languages. Several web frameworks have been created that enforce the pattern. These software frameworks vary in their interpretations, mainly in the way that the MVC responsibilities are divided between the client and server.

> Some web MVC frameworks take a thin client approach that places almost the entire model, view and controller logic on the server. This is reflected in frameworks such as Django, Rails and ASP.NET MVC. In this approach, the client sends either hyperlink requests or form submissions to the controller and then receives a complete and updated web page (or other document) from the view; the model exists entirely on the server. Other frameworks such as AngularJS, EmberJS, JavaScriptMVC and Backbone allow the MVC components to execute partly on the client.

Web MVC = MVC concept + HTML code generation + data binding

## What all the things a good web framework should offer?

* Strong data binding
* Easy component extension and customization
* Less code
* Ability to outline the look and feel
* Low learning curve
* Full control on the page
* Open source
* Commercial resources available
* Active community + third party resources

There is a better article on [framework](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/03-backend-development/framework.md).


now lets have a look at some popular frameworks in different languages(java/php/python/ruby).

*******************************
## java

>  **brief history of java**

> James Gosling, Mike Sheridan, and Patrick Naughton initiated the Java language project in June 1991. Java was originally designed for interactive television, but it was too advanced for the digital cable television industry at the time. The language was initially called Oak after an oak tree that stood outside Gosling's office. Later the project went by the name Green and was finally renamed Java, from Java coffee. Gosling designed Java with a C/C++-style syntax that system and application programmers would find familiar.

> Sun Microsystems released the first public implementation as Java 1.0 in 1995. It promised "Write Once, Run Anywhere" (WORA), providing no-cost run-times on popular platforms. Fairly secure and featuring configurable security, it allowed network- and file-access restrictions. Major web browsers soon incorporated the ability to run Java applets within web pages, and Java quickly became popular. The Java 1.0 compiler was re-written in Java by Arthur van Hoff to comply strictly with the Java 1.0 language specification. With the advent of Java 2 (released initially as J2SE 1.2 in December 1998 – 1999), new versions had multiple configurations built for different types of platforms. J2EE included technologies and APIs for enterprise applications typically run in server environments, while J2ME featured APIs optimized for mobile applications. The desktop version was renamed J2SE. In 2006, for marketing purposes, Sun renamed new J2 versions as Java EE, Java ME, and Java SE, respectively.

> In 1997, Sun Microsystems approached the ISO/IEC JTC 1 standards body and later the Ecma International to formalize Java, but it soon withdrew from the process. Java remains a de facto standard, controlled through the Java Community Process.At one time, Sun made most of its Java implementations available without charge, despite their proprietary software status. Sun generated revenue from Java through the selling of licenses for specialized products such as the Java Enterprise System.

> On November 13, 2006, Sun released much of its Java virtual machine (JVM) as free and open-source software, (FOSS), under the terms of the GNU General Public License (GPL). On May 8, 2007, Sun finished the process, making all of its JVM's core code available under free software/open-source distribution terms, aside from a small portion of code to which Sun did not hold the copyright.

> Sun's vice-president Rich Green said that Sun's ideal role with regard to Java was as an "evangelist". Following Oracle Corporation's acquisition of Sun Microsystems in 2009–10, Oracle has described itself as the "steward of Java technology with a relentless commitment to fostering a community of participation and transparency". This did not prevent Oracle from filing a lawsuit against Google shortly after that for using Java inside the Android SDK (see Google section below). Java software runs on everything from laptops to data centers, game consoles to scientific supercomputers. On April 2, 2010, James Gosling resigned from Oracle.

> In January 2016, Oracle announced that Java runtime environments based on JDK 9 will discontinue the browser plugin.

> Principles
> There were five primary goals in the creation of the Java language:

> * It must be "simple, object-oriented, and familiar".
> * It must be "robust and secure".
> * It must be "architecture-neutral and portable".
> * It must execute with "high performance".
> * It must be "interpreted, threaded, and dynamic".


> As of 2017, both Java 8 and 9 are officially supported. Major release versions of Java, along with their release dates:

> * JDK 1.0 (January 23, 1996)
> * JDK 1.1 (February 19, 1997)
> * J2SE 1.2 (December 8, 1998)
> * J2SE 1.3 (May 8, 2000)
> * J2SE 1.4 (February 6, 2002)
> * J2SE 5.0 (September 30, 2004)
> * Java SE 6 (December 11, 2006)
> * Java SE 7 (July 28, 2011)
> * Java SE 8 (March 18, 2014)
> * Java SE 9 (September 21, 2017)

> The platform was known as Java 2 Platform, Enterprise Edition or J2EE from version 1.2, until the name was changed to Java Platform, Enterprise Edition or Java EE in version 1.5. The current version is called Java EE 8.

> * J2EE 1.2 (December 12, 1999)
> * J2EE 1.3 (September 24, 2001)
> * J2EE 1.4 (November 11, 2003)
> * Java EE 5 (May 11, 2006)
> * Java EE 6 (December 10, 2009)
> * Java EE 7 (May 28, 2013, but April 5, 2013 according to spec document. June 12, 2013 was the planned kickoff date
> * Java EE 8 (August 31, 2017)
>  Java EE is currently maintained by Oracle under the Java Community Process. On September 12, 2017, Oracle Corporation announced > * that it would submit Java EE to the Eclipse Foundation. The Eclipse top-level project has been named Eclipse Enterprise for Java (EE4J).

******************

a look into java timelines
-----------------------
<br>

![java](https://image.slidesharecdn.com/javanturav2-theroadtojava-hujakoraclecroatia-brankomihaljevialeksanderradovandukovukmanovi-141130060735-conversion-gate01/95/javantura-v2-the-road-to-java-hujak-oracle-croatia-branko-mihaljevi-aleksander-radovan-duko-vukmanovi-3-638.jpg)

***********************************************************
<h3><span class="mw-headline" id="Java">List of Java Web Frameworks</span></span></h3>

<p>Source: Wikipedia</P>

<div role="note" class="hatnote navigation-not-searchable">Wiki: <a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java (programming language)</a> and <a href="https://en.wikipedia.org/wiki/Java_(software_platform)" title="Java (software platform)">Java (software platform)</a></div>

<table class="wikitable sortable" style="font-size: 90%">
<br>
<tr>
<th>Project</th>
<th>Current stable version</th>
<th>Release date</th>
<th><a href="https://en.wikipedia.org/wiki/License" title="License">License</a></th>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Apache_Click" title="Apache Click">Apache Click</a></th>
<td>2.3.0 (retired)</td>
<td>2011-03-27</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Apache_Software_License" class="mw-redirect" title="Apache Software License">Apache</a> 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Apache_OFBiz" title="Apache OFBiz">Apache OFBiz</a></th>
<td>13.07.03</td>
<td>2016-04-04</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Shale_Framework_(software)" class="mw-redirect" title="Shale Framework (software)">Apache Shale</a></th>
<td>1.0.4 (retired)</td>
<td>2007-12-19</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Apache_Sling" title="Apache Sling">Apache Sling</a></th>
<td>8</td>
<td>2015-10-16</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Apache_Struts_2" title="Apache Struts 2">Apache Struts 2</a></th>
<td>2.5.13</td>
<td>2017-09-05</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Apache_Tapestry" title="Apache Tapestry">Apache Tapestry</a></th>
<td>5.4.1</td>
<td>2016-03-16</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Apache_Wicket" title="Apache Wicket">Apache Wicket</a></th>
<td>7.9.0</td>
<td>2017-09-19</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/AppFuse" title="AppFuse">AppFuse</a></th>
<td>3.5.0</td>
<td>2015-02-20</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Brutos_Framework" title="Brutos Framework">Brutos Framework</a></th>
<td>2.0</td>
<td>2015-06-30</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Remote_Application_Platform" title="Remote Application Platform">Eclipse RAP</a></th>
<td>3.1 M4</td>
<td>2015-12-22</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Eclipse_Public_License" title="Eclipse Public License">Eclipse</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/FormEngine" title="FormEngine">FormEngine</a></th>
<td>2.0.1 (dormant)</td>
<td>2012-05-08</td>
<td style="background: #ddf; vertical-align: middle; text-align: center;" class="table-proprietary"><a href="https://en.wikipedia.org/wiki/Proprietary_software" title="Proprietary software">Proprietary</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Grails_(framework)" title="Grails (framework)">Grails</a></th>
<td>3.3.1</td>
<td>2017-09-22</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Google_Web_Toolkit" title="Google Web Toolkit">Google Web Toolkit</a></th>
<td>2.8.1</td>
<td>2017-04-24</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Hamlets" title="Hamlets">Hamlets</a></th>
<td>1.7.1 (dormant)</td>
<td>2012-06-29</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/BSD_licenses" title="BSD licenses">BSD</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/ItsNat" title="ItsNat">ItsNat</a></th>
<td>1.4</td>
<td>2015-09-18</td>
<td><a href="/wiki/GNU_Lesser_General_Public_License" title="GNU Lesser General Public License">GNU LGPL</a>, proprietary</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/JavaServer_Faces" title="JavaServer Faces">JavaServer Faces</a> (Mojarra)</th>
<td>2.2.8</td>
<td>2016-05-30</td>https://en.wikipedia.org
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Common_Development_and_Distribution_License" title="Common Development and Distribution License">CDDL</a>, <a href="https://en.wikipedia.org/wiki/GNU_General_Public_License" title="GNU General Public License">GNU GPL</a> 2, Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/JBoss_Seam" title="JBoss Seam">JBoss Seam</a></th>
<td>3.1.0 final (discontinued)</td>
<td>2012-01-13</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">GNU LGPL</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Jspx-bay" title="Jspx-bay">Jspx-bay</a></th>
<td>2.1</td>
<td>2015-12-23</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/JVx_(Framework)" title="JVx (Framework)">JVx</a></th>
<td>2.4</td>
<td>2015-12-23</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/JWt_(Java_web_toolkit)" title="JWt (Java web toolkit)">JWt</a></th>
<td>3.3.8</td>
<td>2017-08-16</td>
<td><a href="https://en.wikipedia.org/wiki/GNU_General_Public_License" title="GNU General Public License">GNU GPL</a>, proprietary</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/OpenLaszlo" title="OpenLaszlo">OpenLaszlo</a></th>
<td>4.9.0 (dormant)</td>
<td>2010-10-21</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Common_Public_License" title="Common Public License">CPL</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/OpenXava" title="OpenXava">OpenXava</a></th>
<td>5.5</td>
<td>2016-04-27</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">GNU LGPL</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Oracle_Application_Development_Framework" title="Oracle Application Development Framework">Oracle ADF</a></th>
<td>12.1.3.0</td>
<td>2014-06-26</td>
<td>Oracle Technology Network Developer License</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Play_Framework" title="Play Framework">Play</a></th>
<td>2.6.6</td>
<td>2017-10-05</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/RIFE" title="RIFE">RIFE</a></th>
<td>1.6.1 (unmaintained)</td>
<td>2007-07-14</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">CDDL, GNU LGPL</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Spark_(software)" title="Spark (software)">Spark</a></th>
<td>2.5</td>
<td>2016-05-03</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Spring_Framework" title="Spring Framework">Spring</a></th>
<td>4.3.5</td>
<td>2016-12-21</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Stripes_(framework)" title="Stripes (framework)">Stripes</a></th>
<td>1.6.0</td>
<td>2015-07-23</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Takes_(framework)" title="Takes (framework)">Takes</a></th>
<td>1.1</td>
<td>2016-06-26</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">MIT</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Vaadin" title="Vaadin">Vaadin</a></th>
<td>7.6.6</td>
<td>2016-05-12</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/VRaptor" title="VRaptor">VRaptor</a></th>
<td>4.2.0-RC4</td>
<td>2016-05-09</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache 2.0</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Wavemaker" class="mw-redirect" title="Wavemaker">Wavemaker</a></th>
<td>8.2<sup id="cite_ref-12" class="reference"><a href="#cite_note-12">[12]</a></sup></td>
<td>2016-06-07</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/WebObjects" title="WebObjects">WebObjects</a></th>
<td>5.4.3 (discontinued)</td>
<td>2008-09-15</td>
<td style="background: #ddf; vertical-align: middle; text-align: center;" class="table-proprietary"><a href="https://en.wikipedia.org/wiki/Proprietary_software" title="Proprietary software">Proprietary</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/WebWork" title="WebWork">WebWork</a></th>
<td>2.2.6 (unmaintained)</td>
<td>2007-07-21</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Ztemplates" class="mw-redirect" title="Ztemplates">ztemplates</a></th>
<td>2.4.0 (dormant)</td>
<td>2011-09-11</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">Apache</td>
</tr>
</table>


lets explore one popular java web framework in detail to understand how easier is the web development using Java.

***********************************
## Spring Framework

I have some indirect working knowledge on spring in my current project, where [SAP Hybris commerce](https://www.hybris.com/medias/sys_master/formsCollaterals/formsCollaterals/h7e/h22/8814707834910/WP-SAP-Hybris-Commerce-Architecture-and-Technology-EN.pdf) is heavily built and runs on spring framework. Spring is primarily known
for its [dependency injection (DI)](https://en.wikipedia.org/wiki/Dependency_injection) and [aspect-oriented programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming) features.

*************************

 | HackerNews        | Medium         | Reddit  |  Quora-QA  | Stack-Overflow-QA |  Awesome-gh | Online-Courses (pivotal) | Official docs|
| ------------- |:-------------:| -----:| -----:|-----:|-----:|-----:|-----:|
|  [spring-framework](https://hn.algolia.com/?query=spring%20framework&sort=byPopularity&prefix&page=0&dateRange=all&type=story)  | [spring-framework](https://medium.com/tag/spring-framework)  | [spring-framework](https://www.reddit.com/r/springsource/)  | [spring-framework](https://www.quora.com/topic/Spring-Framework-1)  |  [spring-framework](https://stackoverflow.com/questions/tagged/spring+spring-mvc)     | [awesome-java](https://github.com/akullpp/awesome-java)|* [spring-framework](https://pivotal.io/training/learning-paths)  * [spring-framework](https://www.lynda.com/search?q=spring+framework)|[spring-framework](https://docs.spring.io/spring/docs/current/spring-framework-reference/index.html)  |


****************

Spring is the most popular application development framework for enterprise Java. Millions of developers around the world use Spring Framework to create high performing, easily testable, and reusable code.

Spring framework is an open source Java platform. It was initially written by [Rod Johnson](https://en.wikipedia.org/wiki/Rod_Johnson_(programmer)) and was first released under the Apache 2.0 license in June 2003.

Spring is lightweight when it comes to size and transparency. The basic version of Spring framework is around 2MB.

The core features of the Spring Framework can be used in developing any Java application, but there are extensions for building web applications on top of the Java EE platform. Spring framework targets to make J2EE development easier to use and promotes good programming practices by enabling a POJO( Plain Old Java Object)-based programming model.

check out spring [architecture](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/03-backend-development/springframework/spring%20architecture.md)

***************************

Popularity rank of each java web frameworks computed by combining the  public data from StackOverflow, LinkedIn, GitHub, and Google search. 30% of developers using spring.

<div class="row text-center">
      		<div class="col-12">
		  		<center>
		  			<table class="zebra"> 
						 <thead>
							  <tr>
								  <th class="center">Rank</th>
								  <th class="center">Framework</th>
								  <th class="center">Popularity</th>
							  </tr>
						  </thead>
						  <tbody>
							  	<tr><td class='center'>1</td><td>Spring mvc</td><td class='center'>29.39</td></tr>
								<tr><td class='center'>2</td><td>JSF</td><td class='center'>15.19</td></tr>
								<tr><td class='center'>3</td><td>Spring Boot</td><td class='center'>11.69</td></tr>
								<tr><td class='center'>4</td><td>GWT</td><td class='center'>7.6</td></tr>
								<tr><td class='center'>5</td><td>Grails</td><td class='center'>6.73</td></tr>
								<tr><td class='center'>6</td><td>Struts</td><td class='center'>7.47</td></tr>
								<tr><td class='center'>7</td><td>Play framework</td><td class='center'>4.16</td></tr>
								<tr><td class='center'>8</td><td>Seam</td><td class='center'>1.88</td></tr>
								<tr><td class='center'>9</td><td>jax-rs</td><td class='center'>3.1</td></tr>
								<tr><td class='center'>10</td><td>Vaadin</td><td class='center'>2.45</td></tr>
								<tr><td class='center'>11</td><td>Wicket</td><td class='center'>1.92</td></tr>
								<tr><td class='center'>12</td><td>Tapestry</td><td class='center'>1.83</td></tr>
								<tr><td class='center'>13</td><td>JHipster</td><td class='center'>0.73</td></tr>
								<tr><td class='center'>14</td><td>Dropwizard</td><td class='center'>1.05</td></tr>
								<tr><td class='center'>15</td><td>Sparkjava</td><td class='center'>0.76</td></tr>
								<tr><td class='center'>16</td><td>Lagom</td><td class='center'>0.71</td></tr>
								<tr><td class='center'>17</td><td>Vert.x</td><td class='center'>0.72</td></tr>
								<tr><td class='center'>18</td><td>Ratpack</td><td class='center'>0.15</td></tr>
								<tr><td class='center'>19</td><td>Rapidoid</td><td class='center'>0</td></tr>
						  </tbody>
				  	</table>
<br>
<p>most recent data </p>
<br>
				  
<img src="https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/03-backend-development/springframework/java_web_stats.JPG" />
		  		</center>
		  		<div id="chart"></div>
	  		</div>
    	</div>

source : [zeroturnaround](https://zeroturnaround.com/webframeworksindex/)

****************
> spring official doc says:

> ## Spring Framework Overview
> Spring makes it easy to create Java enterprise applications. It provides everything you need to embrace the Java language in an enterprise environment, with support for Groovy and Kotlin as alternative languages on the JVM, and with the flexibility to create many kinds of architectures depending on an application’s needs. As of Spring Framework 5.0, Spring requires JDK 8+ (Java SE 8+) and provides out-of-the-box support for JDK 9 already.

> Spring supports a wide range of application scenarios. In a large enterprise, applications often exist for a long time and have to run on a JDK and application server whose upgrade cycle is beyond developer control. Others may run as a single jar with the server embedded, possibly in a cloud environment. Yet others may be standalone applications (such as batch or integration workloads) that do not need a server.

> Spring is open source. It has a large and active community that provides continuous feedback based on a diverse range of real-world use cases. This has helped Spring to successfully evolve over a very long time.
> ## What We Mean by "Spring"
> The term "Spring" means different things in different contexts. It can be used to refer to the Spring Framework project itself, which is where it all started. Over time, other Spring projects have been built on top of the Spring Framework. Most often, when people say "Spring", they mean the entire family of projects. This reference documentation focuses on the foundation: the Spring Framework itself.

> The Spring Framework is divided into modules. Applications can choose which modules they need. At the heart are the modules of the core container, including a configuration model and a dependency injection mechanism. Beyond that, the Spring Framework provides foundational support for different application architectures, including messaging, transactional data and persistence, and web. It also includes the Servlet-based Spring MVC web framework and, in parallel, the Spring WebFlux reactive web framework.

> A note about modules: Spring’s framework jars allow for deployment to JDK 9’s module path ("Jigsaw"). For use in Jigsaw-enabled applications, the Spring Framework 5 jars come with "Automatic-Module-Name" manifest entries which define stable language-level module names ("spring.core", "spring.context" etc) independent from jar artifact names (the jars follow the same naming pattern with "-" instead of ".", e.g. "spring-core" and "spring-context"). Of course, Spring’s framework jars keep working fine on the classpath on both JDK 8 and 9.

> ## History of Spring and the Spring Framework

> Spring came into being in 2003 as a response to the complexity of the early J2EE specifications. While some consider Java EE and Spring to be in competition, Spring is, in fact, complementary to Java EE. The Spring programming model does not embrace the Java EE platform specification; rather, it integrates with carefully selected individual specifications from the EE umbrella:

> * Servlet API (JSR 340)

> * WebSocket API (JSR 356)

> * Concurrency Utilities (JSR 236)

> * JSON Binding API (JSR 367)

> * Bean Validation (JSR 303)

> * JPA (JSR 338)

> * JMS (JSR 914)

> as well as JTA/JCA setups for transaction coordination, if necessary.

> The Spring Framework also supports the Dependency Injection (JSR 330) and Common Annotations (JSR 250) specifications, which application developers may choose to use instead of the Spring-specific mechanisms provided by the Spring Framework.

> As of Spring Framework 5.0, Spring requires the Java EE 7 level (e.g. Servlet 3.1+, JPA 2.1+) as a minimum - while at the same time providing out-of-the-box integration with newer APIs at the Java EE 8 level (e.g. Servlet 4.0, JSON Binding API) when encountered at runtime. This keeps Spring fully compatible with e.g. Tomcat 8 and 9, WebSphere 9, and JBoss EAP 7.

> Over time, the role of Java EE in application development has evolved. In the early days of Java EE and Spring, applications were created to be deployed to an application server. Today, with the help of Spring Boot, applications are created in a devops- and cloud-friendly way, with the Servlet container embedded and trivial to change. As of Spring Framework 5, a WebFlux application does not even use the Servlet API directly and can run on servers (such as Netty) that are not Servlet containers.

> Spring continues to innovate and to evolve. Beyond the Spring Framework, there are other projects, such as Spring Boot, Spring Security, Spring Data, Spring Cloud, Spring Batch, among others. It’s important to remember that each project has its own source code repository, issue tracker, and release cadence. See spring.io/projects for the complete list of Spring projects.

> ## Design Philosophy

> When you learn about a framework, it’s important to know not only what it does but what principles it follows. Here are the guiding principles of the Spring Framework:

> Provide choice at every level. Spring lets you defer design decisions as late as possible. For example, you can switch persistence providers through configuration without changing your code. The same is true for many other infrastructure concerns and integration with third-party APIs.

> Accommodate diverse perspectives. Spring embraces flexibility and is not opinionated about how things should be done. It supports a wide range of application needs with different perspectives.

> Maintain strong backward compatibility. Spring’s evolution has been carefully managed to force few breaking changes between versions. Spring supports a carefully chosen range of JDK versions and third-party libraries to facilitate maintenance of applications and libraries that depend on Spring.

> Care about API design. The Spring team puts a lot of thought and time into making APIs that are intuitive and that hold up across many versions and many years.

> Set high standards for code quality. The Spring Framework puts a strong emphasis on meaningful, current, and accurate Javadoc. It is one of very few projects that can claim clean code structure with no circular dependencies between packages.

***********

There are thousands of tutorials and blogs on spring, I think for experienced developers official doc is the best material to dive in. spring official doc has best step by step guide to understand some core concepts with code examples:

<br>

![spring doc](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/03-backend-development/springframework/spring_doc.JPG)


Sample Spring [Project Structure from official guide:](https://docs.spring.io/docs/Spring-MVC-step-by-step/)

![spring project structure](https://docs.spring.io/docs/Spring-MVC-step-by-step/images/dir-structure-endp6.png)

Some article on spring project structure:
* [spring project structure](https://www.coveros.com/spring-mvc-project-structure/) 
* [stackoverflow](https://stackoverflow.com/questions/23550273/spring-mvc-project-structure-best-practices) 
* [spring web app architecture](https://www.petrikainulainen.net/software-development/design/understanding-spring-web-application-architecture-the-classic-way/)


******************************************

## php
>  **brief history of php**

> Rasmus Lerdorf (left), who wrote the original Common Gateway Interface (CGI) component, together with Andi Gutmans (middle) and Zeev Suraski (right), who rewrote the parser that formed PHP 3.

> PHP development began in 1995 when Rasmus Lerdorf wrote several Common Gateway Interface (CGI) programs in C, which he used to maintain his personal homepage. He extended them to work with web forms and to communicate with databases, and called this implementation "Personal Home Page/Forms Interpreter" or PHP/FI.

> PHP/FI could help to build simple, dynamic web applications. To accelerate bug reporting and to improve the code, Lerdorf initially announced the release of PHP/FI as "Personal Home Page Tools (PHP Tools) version 1.0" on the Usenet discussion group comp.infosystems. www.authoring.cgi on June 8, 1995. This release already had the basic functionality that PHP has as of 2013. This included Perl-like variables, form handling, and the ability to embed HTML. The syntax resembled that of Perl but was simpler, more limited and less consistent.

> Lerdorf did not intend the early PHP to become a new programming language, but it grew organically, with Lerdorf noting in retrospect: "I don’t know how to stop it, there was never any intent to write a programming language […] I have absolutely no idea how to write a programming language, I just kept adding the next logical step on the way." A development team began to form and, after months of work and beta testing, officially released PHP/FI 2 in November 1997.

> The fact that PHP lacked an original overall design but instead developed organically has led to inconsistent naming of functions and inconsistent ordering of their parameters. In some cases, the function names were chosen to match the lower-level libraries which PHP was "wrapping", while in some very early versions of PHP the length of the function names was used internally as a hash function, so names were chosen to improve the distribution of hash values.

> **PHP 3 and 4**

> PHP 3.0 is the successor of PHP/FI 2.0. Zeev Suraski and Andi Gutmans rewrote the parser in 1997 and formed the base of PHP 3, changing the language's name to the recursive acronym PHP: Hypertext Preprocessor. Afterwards, public testing of PHP 3 began, and the official launch came in June 1998. Suraski and Gutmans then started a new rewrite of PHP's core, producing the Zend Engine in 1999.They also founded Zend Technologies in Ramat Gan, Israel.

> On May 22, 2000, PHP 4, powered by the Zend Engine 1.0, was released. As of August 2008 this branch reached version 4.4.9. PHP 4 is no longer under development nor will any security updates be released.

> **PHP 5**

> On July 13, 2004, PHP 5 was released, powered by the new Zend Engine II. PHP 5 included new features such as improved support for object-oriented programming, the PHP Data Objects (PDO) extension (which defines a lightweight and consistent interface for accessing databases), and numerous performance enhancements. In 2008 PHP 5 became the only stable version under development. Late static binding had been missing from PHP and was added in version 5.3.

> Many high-profile open-source projects ceased to support PHP 4 in new code as of February 5, 2008, because of the GoPHP5 initiative, provided by a consortium of PHP developers promoting the transition from PHP 4 to PHP 5.

> Over time, PHP interpreters became available on most existing 32-bit and 64-bit operating systems, either by building them from the PHP source code, or by using pre-built binaries. For the PHP versions 5.3 and 5.4, the only available Microsoft Windows binary distributions were 32-bit x86 builds, requiring Windows 32-bit compatibility mode while using Internet Information Services (IIS) on a 64-bit Windows platform. PHP version 5.5 made the 64-bit x86-64 builds available for Microsoft Windows.

> **PHP 6 and Unicode**

> PHP has received criticism due to lacking native Unicode support at the core language level, instead only supporting byte strings. In 2005, a project headed by Andrei Zmievski was initiated to bring native Unicode support throughout PHP, by embedding the International Components for Unicode (ICU) library, and representing text strings as UTF-16 internally.Since this would cause major changes both to the internals of the language and to user code, it was planned to release this as version 6.0 of the language, along with other major features then in development.

> However, a shortage of developers who understood the necessary changes, and performance problems arising from conversion to and from UTF-16, which is rarely used in a web context, led to delays in the project. As a result, a PHP 5.3 release was created in 2009, with many non-Unicode features back-ported from PHP 6, notably namespaces. In March 2010, the project in its current form was officially abandoned, and a PHP 5.4 release was prepared containing most remaining non-Unicode features from PHP 6, such as traits and closure re-binding. Initial hopes were that a new plan would be formed for Unicode integration, but as of 2014 none had been adopted.

> **PHP 7**

> During 2014 and 2015, a new major PHP version was developed, which was numbered PHP 7. The numbering of this version involved some debate. While the PHP 6 Unicode experiment had never been released, several articles and book titles referenced the PHP 6 name, which might have caused confusion if a new release were to reuse the name.After a vote, the name PHP 7 was chosen.

> The foundation of PHP 7 is a PHP branch that was originally dubbed PHP next generation (phpng). It was authored by Dmitry Stogov, Xinchen Hui and Nikita Popov, and aimed to optimize PHP performance by refactoring the Zend Engine to use more compact data structures with improved cache locality while retaining near-complete language compatibility. As of 14 July 2014, WordPress-based benchmarks, which served as the main benchmark suite for the phpng project, showed an almost 100% increase in performance. Changes from phpng are also expected to make it easier to improve performance in the future, as more compact data structures and other changes are seen as better suited for a successful migration to a just-in-time (JIT) compiler. Because of the significant changes, the reworked Zend Engine is called Zend Engine 3, succeeding Zend Engine 2 used in PHP 5.

> Because of major internal changes in phpng, it must receive a new major version number of PHP, rather than a minor PHP 5 release, according to PHP's release process. Major versions of PHP are allowed to break backward-compatibility of code and therefore PHP 7 presented an opportunity for other improvements beyond phpng that require backward-compatibility breaks, including wider use of exceptions, reworking variable syntax to be more consistent and complete,and the deprecation or removal of various legacy features.

> PHP 7 also introduced new language features, including return type declarations for functions,which complement the existing parameter type declarations, and support for the scalar types (integer, float, string, and boolean) in parameter and return type declarations.


*******************

## list of  php web frameworks
<p>Source: Wikipedia</P>

<div role="note" class="hatnote navigation-not-searchable">Wiki: <a href="https://en.wikipedia.org/wiki/PHP" title="PHP">PHP</a></div>
<table class="wikitable sortable" style="font-size: 90%">
<br>

<tr>
<th style="width:140pt;">Project</th>
<th>Start date</th>
<th style="width:90pt;">Current stable version</th>
<th>Release date</th>
<th><a href="https://en.wikipedia.org/wiki/Software_license" title="Software license">License</a></th>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Agavi" title="Agavi">Agavi</a></th>
<td>2005-05</td>
<td>1.0.8<sup id="cite_ref-agavi_release_15-0" class="reference"><a href="#cite_note-agavi_release-15">[15]</a></sup></td>
<td>2015-06-29</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License" title="GNU Lesser General Public License">LGPL</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/CakePHP" title="CakePHP">CakePHP</a></th>
<td>2005-08</td>
<td>3.5.0<sup id="cite_ref-cakephp_release_16-0" class="reference"><a href="#cite_note-cakephp_release-16">[16]</a></sup></td>
<td>2017-08-18<small class="plainlinks"><a class="external text" href="//en.wikipedia.org/w/index.php?title=Template:CakePHP_version&amp;action=edit">[±]</a></small></td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/MIT_License" title="MIT License">MIT</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/CodeIgniter" title="CodeIgniter">CodeIgniter</a></th>
<td>2006-02-28</td>
<td>3.1.6<sup id="cite_ref-ci_release_17-0" class="reference"><a href="#cite_note-ci_release-17">[17]</a></sup></td>
<td>2017-09-25</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">MIT</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Fat-Free_Framework" title="Fat-Free Framework">Fat-Free</a></th>
<td>2009-09</td>
<td>3.6.0<sup id="cite_ref-fatfreegit_18-0" class="reference"><a href="#cite_note-fatfreegit-18">[18]</a></sup></td>
<td>2016-11-19</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">GPLv3</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/FuelPHP" title="FuelPHP">FuelPHP</a></th>
<td>2011-08</td>
<td>1.8<sup id="cite_ref-fuel_release_19-0" class="reference"><a href="#cite_note-fuel_release-19">[19]</a></sup></td>
<td>2016-04-09</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">MIT</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Gyroscope_(software)" title="Gyroscope (software)">Gyroscope</a></th>
<td>2008-11-20</td>
<td>8.8.0</td>
<td>2016-04-17</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/BSD_licenses" title="BSD licenses">BSD</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Jamroom" title="Jamroom">Jamroom</a></th>
<td>2003-07-28</td>
<td>6.1.0<sup id="cite_ref-jamroom_release_20-0" class="reference"><a href="#cite_note-jamroom_release-20">[20]</a></sup></td>
<td>2017-08-30</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Mozilla_Public_License" title="Mozilla Public License">MPL</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Kajona" title="Kajona">Kajona</a></th>
<td>2006</td>
<td>6.2<sup id="cite_ref-kajona_release_21-0" class="reference"><a href="#cite_note-kajona_release-21">[21]</a></sup></td>
<td>2017-06-08</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License" title="GNU Lesser General Public License">LGPLv2</a></td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Kohana_(framework)" title="Kohana (framework)">Kohana</a></th>
<td>2007-07</td>
<td>3.3.5<sup id="cite_ref-kohana_release_22-0" class="reference"><a href="#cite_note-kohana_release-22">[22]</a></sup></td>
<td>2016-03-10</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/BSD_licenses" title="BSD licenses">BSD</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Laravel" title="Laravel">Laravel</a></th>
<td>2011-06-11</td>
<td>5.5.0<sup id="cite_ref-23" class="reference"><a href="#cite_note-23">[23]</a></sup></td>
<td>2017-08-30</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">MIT</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Li3_(software)" title="Li3 (software)">Li3</a> (Lithium)</th>
<td>2009-10</td>
<td>1.1.0<sup id="cite_ref-li3_release_24-0" class="reference"><a href="#cite_note-li3_release-24">[24]</a></sup></td>
<td>2017-04-23</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/BSD_licenses" title="BSD licenses">BSD</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Nette_Framework" title="Nette Framework">Nette Framework</a></th>
<td>2006-01<sup id="cite_ref-25" class="reference"><a href="#cite_note-25">[25]</a></sup></td>
<td>2.4.0<sup id="cite_ref-26" class="reference"><a href="#cite_note-26">[26]</a></sup></td>
<td>2016-05-03</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/New_BSD_License" class="mw-redirect" title="New BSD License">New BSD</a>, GPLv2, GPLv3<sup id="cite_ref-27" class="reference"><a href="#cite_note-27">[27]</a></sup></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Phalcon_(framework)" title="Phalcon (framework)">Phalcon</a></th>
<td>2012-11-14</td>
<td>3.2.3<sup id="cite_ref-phalcon_release_28-0" class="reference"><a href="#cite_note-phalcon_release-28">[28]</a></sup></td>
<td>2017-10-12</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">BSD</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Pop_PHP_Framework" title="Pop PHP Framework">Pop PHP</a></th>
<td>2012-03-19</td>
<td>3.6.1<sup id="cite_ref-29" class="reference"><a href="#cite_note-29">[29]</a></sup></td>
<td>2017-09-14</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">New BSD</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/PRADO_(framework)" title="PRADO (framework)">PRADO</a></th>
<td>2004-01</td>
<td>3.3.2<sup id="cite_ref-30" class="reference"><a href="#cite_note-30">[30]</a></sup></td>
<td>2016-08-23</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">New BSD<sup id="cite_ref-31" class="reference"><a href="#cite_note-31">[31]</a></sup></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Silex_(web_framework)" title="Silex (web framework)">Silex</a></th>
<td>2011-09</td>
<td>2.0.0<sup id="cite_ref-silex_release_32-0" class="reference"><a href="#cite_note-silex_release-32">[32]</a></sup></td>
<td>2016-05-18</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">MIT</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/SilverStripe" title="SilverStripe">SilverStripe</a></th>
<td>2007-02-03</td>
<td>3.6.1<sup id="cite_ref-silverstripe_release_33-0" class="reference"><a href="#cite_note-silverstripe_release-33">[33]</a></sup></td>
<td>2017-06-27</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">BSD</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Smart_Framework_PHP" title="Smart Framework PHP">Smart.Framework</a></th>
<td>2015-02-01</td>
<td>2.3.7.2<sup id="cite_ref-34" class="reference"><a href="#cite_note-34">[34]</a></sup></td>
<td>2016-09-27</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">BSD</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Symfony" title="Symfony">Symfony</a></th>
<td>2005-10</td>
<td>3.3.9<sup id="cite_ref-35" class="reference"><a href="#cite_note-35">[35]</a></sup></td>
<td>2017-09-11</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">MIT</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/TwistPHP" title="TwistPHP">TwistPHP</a></th>
<td>2014-07</td>
<td>3.0.5<sup id="cite_ref-twistphp_release_36-0" class="reference"><a href="#cite_note-twistphp_release-36">[36]</a></sup></td>
<td>2017-01-11</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/GNU_General_Public_License" title="GNU General Public License">GPLv3</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/TYPO3_Flow" title="TYPO3 Flow">TYPO3 Flow</a></th>
<td>2011-10</td>
<td>3.3.4<sup id="cite_ref-typo3release_37-0" class="reference"><a href="#cite_note-typo3release-37">[37]</a></sup></td>
<td>2016-09-29</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License" title="GNU Lesser General Public License">LGPLv3</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Yii" title="Yii">Yii</a></th>
<td>2008-12-03</td>
<td>2.0.12<sup id="cite_ref-38" class="reference"><a href="#cite_note-38">[38]</a></sup></td>
<td>2017-06-05</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/New_BSD_Licence" class="mw-redirect" title="New BSD Licence">New BSD</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Zend_Framework" title="Zend Framework">Zend Framework</a></th>
<td>2006-03</td>
<td>3.0.0<sup id="cite_ref-zend_release_39-0" class="reference"><a href="#cite_note-zend_release-39">[39]</a></sup></td>
<td>2016-06-28</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free">New BSD</td>
</tr>
</table>

******************
I did google trend comparison for some of the php framework popularity below are the results:
<br>

![php](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/03-backend-development/php/php-google-trends.JPG)

Lets explore laravel in detail:

(there is a cource in lynda.com in which Drew Falkman discusses about [5 MVC PHP frameworks](https://www.lynda.com/PHP-tutorials/MVC-Frameworks-Building-PHP-Web-Applications/540346-2.html), their project structure, advantages and disadvantages).

************************
## Laravel

 | HackerNews        | Medium         | Reddit  |  Quora-QA  | Stack-Overflow-QA | Awesome-gh | Online-Courses (lynda.com) | Official docs|
| ------------- |:-------------:| -----:| -----:|-----:|-----:|-----:|-----:|
|  [laravel](https://hn.algolia.com/?query=laravel&sort=byPopularity&prefix&page=0&dateRange=all&type=story)  | [laravel](https://medium.com/tag/laravel)  | [laravel](https://www.reddit.com/r/laravel/)  | [laravel](https://www.quora.com/topic/Laravel)  |  [laravel](https://stackoverflow.com/questions/tagged/laravel)   | [laravel](https://github.com/chiraggude/awesome-laravel) [awesome-php](https://github.com/ziadoz/awesome-php) [php-must-watch](https://github.com/phptodayorg/php-must-watch) | [laravel](https://www.lynda.com/Laravel-training-tutorials/2779-0.html)  |[laravel](https://laravel.com/)  |
************

### Laravel – Features

Laravel offers the following key features:

* Modularity
* Testability
* Routing
* Configuration management
* Query builder and ORM (Object Relational Mapper)
* Schema builder, migrations, and seeding
* Template engine
* E-mailing
* Authentication
* Redis
* Queues
* Event and command bus

### Laravel Application structure:

Official Doc has better explaination of [directory structure](https://laravel.com/docs/5.5/structure)

![app](https://www.tutorialspoint.com/laravel/images/root_directory.jpg)

The root directory of Laravel contains various folders and files as shown in the following figure.

Root Directory
* app − This directory contains the core code of the application.

* bootstrap − This directory contains the application bootstrapping script.

* config − This directory contains configuration files of application.

* database − This folder contains your database migration and seeds.

* public − This is the application’s document root. It starts the Laravel application. It also contains the assets of the application like JavaScript, CSS, Images, etc.

* resources − This directory contains raw assets such as the LESS & Sass files, localization and language files, and Templates that are rendered as HTML.

* storage − This directory contains App storage, like file uploads etc. Framework storage (cache), and application-generated logs.

* test − This directory contains various test cases.

* vendor − This directory contains composer dependencies.

App Directory

* This is the application directory. It contains a variety of additional directories, which are described below −

* Console − All the artisan commands are stored in this directory.

* Events − This directory stores events that your application can raise. Events may be used to alert other parts of your application that a given action has occurred, providing a great deal of flexibility and decoupling.

* Exceptions − This directory contains your application's exception handler and is also a good place to stick any exceptions thrown by your application.

* Http − This directory contains your controllers, filters, and requests.

* Jobs − This directory contains the queueable jobs for your application.

* Listeners − This directory contains the handler classes for your events. Handlers receive an event and perform logic in response to the event being fired. For example, a UserRegistered event might be handled by a SendWelcomeEmail listener.

* Policies − This directory contains various policies of the application

* Providers − This directory contains various service providers.

Articles discusses on app stucture:

* [large-scale-laravel-application](https://medium.com/@munza/large-scale-laravel-application-9d52c3d38e51)


************
## python

> **brief history of python**
> Python was conceived in the late 1980s,and its implementation began in December 1989 by Guido van Rossum at Centrum Wiskunde & Informatica (CWI) in the Netherlands as a successor to the ABC language (itself inspired by SETL) capable of exception handling and interfacing with the operating system Amoeba. Van Rossum is Python's principal author, and his continuing central role in deciding the direction of Python is reflected in the title given to him by the Python community, Benevolent Dictator For Life (BDFL).

> About the origin of Python, Van Rossum wrote in 1996:

> Over six years ago, in December 1989, I was looking for a "hobby" programming project that would keep me occupied during the week around Christmas. My office ... would be closed, but I had a home computer, and not much else on my hands. I decided to write an interpreter for the new scripting language I had been thinking about lately: a descendant of ABC that would appeal to Unix/C hackers. I chose Python as a working title for the project, being in a slightly irreverent mood (and a big fan of Monty Python's Flying Circus).	”
> Python 2.0 was released on 16 October 2000 and had many major new features, including a cycle-detecting garbage collector and support for Unicode. With this release the development process was changed and became more transparent and community-backed.

> Python 3.0 (initially described as Python 3000 or py3k), is a major, backward-incompatible release that was was released after a long period of testing on 3 December 2008. Many of its major features have been backported to the backwards-compatible Python 2.6.x and 2.7.x version series.

> The End Of Life date (EOL, sunset date) for Python 2.7 was initially set at 2015, then postponed to 2020 out of concern that a large body of existing code cannot easily be forward-ported to Python 3. In January 2017, Google announced work on a Python 2.7 to Go transcompiler, which The Register speculated was in response to Python 2.7's planned end-of-life but Google cited performance under concurrent workloads as their only motivation.

**************************

<h3><span class="mw-headline" id="Python">List of Python Web Frameworks</span></span></h3>

<p>Source: Wikipedia</P>

<div role="note" class="hatnote navigation-not-searchable">Wiki: <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python (programming language)</a> and <a href="https://en.wikipedia.org/wiki/List_of_Python_software#Web_frameworks" title="List of Python software">List of Python software §&#160;Web frameworks</a></div>
<table class="wikitable sortable" style="font-size: 90%">
<br>
<tr>
<th>Project</th>
<th>Current stable version</th>
<th>Release date</th>
<th><a href="https://en.wikipedia.org/wiki/Software_license" title="Software license">License</a></th>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Bottle_(web_framework)" title="Bottle (web framework)">Bottle</a></th>
<td>0.12.13</td>
<td>2017-01-09<sup id="cite_ref-bottle_release_40-0" class="reference"><a href="#cite_note-bottle_release-40">[40]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/MIT_license" class="mw-redirect" title="MIT license">MIT</a></td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/BlueBream" class="mw-redirect" title="BlueBream">BlueBream</a></th>
<td>1.0</td>
<td>2011-01-18</td>
<td><a href="https://en.wikipedia.org/wiki/Zope_Public_License" title="Zope Public License">ZPL</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/CherryPy" title="CherryPy">CherryPy</a></th>
<td>10.0.0</td>
<td>2017-01-20<sup id="cite_ref-cp_release_41-0" class="reference"><a href="#cite_note-cp_release-41">[41]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/BSD_licenses" title="BSD licenses">BSD</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/CubicWeb" title="CubicWeb">CubicWeb</a></th>
<td>3.22.2</td>
<td>2016-02-23<sup id="cite_ref-cubicweb_release_42-0" class="reference"><a href="#cite_note-cubicweb_release-42">[42]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License" title="GNU Lesser General Public License">LGPL</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Django_(web_framework)" title="Django (web framework)">Django</a></th>
<td>1.11.5</td>
<td>2017-09-06<sup id="cite_ref-43" class="reference"><a href="#cite_note-43">[43]</a></sup></td>
<td>BSD</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Flask_(web_framework)" title="Flask (web framework)">Flask</a></th>
<td>0.12</td>
<td>2016-12-21<sup id="cite_ref-44" class="reference"><a href="#cite_note-44">[44]</a></sup></td>
<td>BSD</td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Google_App_Engine" title="Google App Engine">Google App Engine</a></th>
<td>1.9.1</td>
<td>2017-03-29</td>
<td>LGPL, Proprietary</td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Grok_(web_framework)" title="Grok (web framework)">Grok</a></th>
<td>2.8</td>
<td>2013-02-14<sup id="cite_ref-grok_release_45-0" class="reference"><a href="#cite_note-grok_release-45">[45]</a></sup></td>
<td>ZPL</td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Nagare_(web_framework)" title="Nagare (web framework)">Nagare</a></th>
<td>0.4.1</td>
<td>2012-01-18</td>
<td>BSD</td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Pyjs" title="Pyjs">Pyjs</a></th>
<td>0.8.1a</td>
<td>2012-05-06</td>
<td><a href="https://en.wikipedia.org/wiki/Apache_License" title="Apache License">Apache</a></td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Pylons_Framework" class="mw-redirect" title="Pylons Framework">Pylons</a></th>
<td>1.0.2</td>
<td>2015-07-21</td>
<td>BSD</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Pyramid_(web_framework)" class="mw-redirect" title="Pyramid (web framework)">Pyramid</a></th>
<td>1.7</td>
<td>2016-05-19<sup id="cite_ref-pyramid-1.7-changes_46-0" class="reference"><a href="#cite_note-pyramid-1.7-changes-46">[46]</a></sup></td>
<td>BSD</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/TACTIC_(web_framework)" title="TACTIC (web framework)">TACTIC</a></th>
<td>4.4.0.v0v</td>
<td>2016-05-19<sup id="cite_ref-47" class="reference"><a href="#cite_note-47">[47]</a></sup></td>
<td>EPL</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Tornado_(web_server)" title="Tornado (web server)">Tornado</a></th>
<td>4.3</td>
<td>2015-11-06<sup id="cite_ref-48" class="reference"><a href="#cite_note-48">[48]</a></sup></td>
<td>Apache</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/TurboGears" title="TurboGears">TurboGears</a></th>
<td>2.3.10</td>
<td>2016-12-04<sup id="cite_ref-49" class="reference"><a href="#cite_note-49">[49]</a></sup></td>
<td>MIT, LGPL</td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Web2py" title="Web2py">web2py</a></th>
<td>2.14.6</td>
<td>2016-05-10<sup id="cite_ref-50" class="reference"><a href="#cite_note-50">[50]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License" title="GNU Lesser General Public License">LGPL3</a></td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Webware_for_Python" title="Webware for Python">Webware</a></th>
<td>1.1.1</td>
<td>2013-01-18</td>
<td><a href="https://en.wikipedia.org/wiki/Python_License" title="Python License">Python</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Zope_2" class="mw-redirect" title="Zope 2">Zope 2</a></th>
<td>2.13.26</td>
<td>2017-02-20<sup id="cite_ref-51" class="reference"><a href="#cite_note-51">[51]</a></sup></td>
<td>ZPL</td>
</tr>
</table>

***********

Lets explore project structure of python frameworks: Flask & Django 

*********
## flask

 | HackerNews        | Medium         | Reddit  |  Quora-QA  | Stack-Overflow-QA | Awesome-gh | Online-Courses (lynda.com) | Ofiicial docs|
| ------------- |:-------------:| -----:| -----:|-----:|-----:|-----:|-----:|
|  [flask](https://hn.algolia.com/?query=flask&sort=byPopularity&prefix&page=0&dateRange=all&type=story)  | [flask](https://medium.com/tag/flask)  | [flask](https://www.reddit.com/r/flask/) | [flask](https://www.quora.com/topic/Flask-Python-framework)  |  [flask](https://stackoverflow.com/questions/tagged/flask)    | [flask](https://github.com/humiaozuzu/awesome-flask)  | [flask](https://www.lynda.com/Flask-tutorials/11121-0.html)  |[flask](http://flask.pocoo.org/)  |


<div class="section" id="organizing-your-project">
<h2>organizing flask project<a class="headerlink" href="#organizing-your-project" title="Permalink to this headline">¶</a></h2>
<p>Flask leaves the organization of your application up to you. This is one
of the reasons I liked Flask as a beginner, but it does mean that you
have to put some thought into how to structure your code. You could put
your entire application in one file, or have it spread across multiple
packages. There are a few organizational patterns that you can follow to
make development and deployment easier.</p>
<div class="section" id="definitions">
<h3>Definitions<a class="headerlink" href="#definitions" title="Permalink to this headline">¶</a></h3>
<p>Let&#8217;s define some of the terms that we&#8217;ll run into in this chapter.</p>
<p><strong>Repository</strong> - This is the base folder where your applications sits.
This term traditionally refers to version control systems, which you
should be using. When I refer to your repository in this chapter, I&#8217;m
talking about the root directory of your project. You probably won&#8217;t
need to leave this directory when working on your application.</p>
<p><strong>Package</strong> - This refers to a Python package that contains your
application&#8217;s code. I&#8217;ll talk more about setting up your app as a
package in this chapter, but for now just know that the package is a
sub-directory of the repository.</p>
<p><strong>Module</strong> - A module is a single Python file that can be imported by
other Python files. A package is essentially multiple modules packaged
together.</p>
<div class="admonition note">
<p class="first admonition-title">Note</p>
<ul class="last simple">
<li>Read more about Python modules in <a class="reference external" href="http://docs.python.org/2/tutorial/modules.html">Python tutorial</a>.</li>
<li>That same page has a <a class="reference external" href="http://docs.python.org/2/tutorial/modules.html#packages">section on packages</a>.</li>
</ul>
</div>
</div>
<div class="section" id="organization-patterns">
<h3>Organization patterns<a class="headerlink" href="#organization-patterns" title="Permalink to this headline">¶</a></h3>
<div class="section" id="single-module">
<h4>Single module<a class="headerlink" href="#single-module" title="Permalink to this headline">¶</a></h4>
<p>A lot of the Flask examples that you&#8217;ll come across will keep all of the
code in a single file, often <em>app.py</em>. This is great for quick projects
(like the ones used for tutorials), where you just need to serve a few
routes and you&#8217;ve got less than a few hundred lines of application code.</p>
<div class="highlight-python"><table class="highlighttable"><tr><td class="linenos"><div class="linenodiv"><pre>1
2
3
4
5</pre></div></td><td class="code"><div class="highlight"><pre><span></span><span class="n">app</span><span class="o">.</span><span class="n">py</span>
<span class="n">config</span><span class="o">.</span><span class="n">py</span>
<span class="n">requirements</span><span class="o">.</span><span class="n">txt</span>
<span class="n">static</span><span class="o">/</span>
<span class="n">templates</span><span class="o">/</span>
</pre></div>
</td></tr></table></div>
<p>Application logic would sit in <em>app.py</em> for the example in Listing~.</p>
</div>
<div class="section" id="package">
<h4>Package<a class="headerlink" href="#package" title="Permalink to this headline">¶</a></h4>
<p>When you&#8217;re working on a project that&#8217;s a little more complex, a single
module can get messy. You&#8217;ll need to define classes for models and
forms, and they&#8217;ll get mixed in with the code for your routes and
configuration. All of this can frustrate development. To solve this
problem, we can factor out the different components of our app into a
group of inter-connected modules — a package.</p>
<div class="highlight-python"><table class="highlighttable"><tr><td class="linenos"><div class="linenodiv"><pre> 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12</pre></div></td><td class="code"><div class="highlight"><pre><span></span><span class="n">config</span><span class="o">.</span><span class="n">py</span>
<span class="n">requirements</span><span class="o">.</span><span class="n">txt</span>
<span class="n">run</span><span class="o">.</span><span class="n">py</span>
<span class="n">instance</span><span class="o">/</span>
    <span class="n">config</span><span class="o">.</span><span class="n">py</span>
<span class="n">yourapp</span><span class="o">/</span>
    <span class="fm">__init__</span><span class="o">.</span><span class="n">py</span>
    <span class="n">views</span><span class="o">.</span><span class="n">py</span>
    <span class="n">models</span><span class="o">.</span><span class="n">py</span>
    <span class="n">forms</span><span class="o">.</span><span class="n">py</span>
    <span class="n">static</span><span class="o">/</span>
    <span class="n">templates</span><span class="o">/</span>
</pre></div>
</td></tr></table></div>
<p>The structure shown in this listing allows you to group the different
components of your application in a logical way. The class definitions
for models are together in <em>models.py</em>, the route definitions are in
<em>views.py</em> and forms are defined in <em>forms.py</em> (we have a whole chapter
for forms later).</p>
<p>This table provides a basic rundown of the components you&#8217;ll find in most
Flask applications. You&#8217;ll probably end up with a lot of other files in
your repository, but these are common to most Flask applications.</p>
<table border="1" class="docutils">
<colgroup>
<col width="28%" />
<col width="72%" />
</colgroup>
<tbody valign="top">
<tr class="row-odd"><td>run.py</td>
<td>This is the file that is invoked to start up a development
server. It gets a copy of the app from your package and runs
it. This won&#8217;t be used in production, but it will see a lot
of mileage in development.</td>
</tr>
<tr class="row-even"><td>requirements.txt</td>
<td>This file lists all of the Python packages that your app
depends on. You may have separate files for production and
development dependencies.</td>
</tr>
<tr class="row-odd"><td>config.py</td>
<td>This file contains most of the configuration variables that
your app needs.</td>
</tr>
<tr class="row-even"><td>/instance/config.py</td>
<td>This file contains configuration variables that shouldn&#8217;t
be in version control. This includes things like API keys
and database URIs containing passwords. This also contains
variables that are specific to this particular instance of
your application. For example, you might have <code class="docutils literal"><span class="pre">DEBUG</span> <span class="pre">=</span> <span class="pre">False</span></code>
in config.py, but set <code class="docutils literal"><span class="pre">DEBUG</span> <span class="pre">=</span> <span class="pre">True</span></code> in instance/config.py on
your local machine for development. Since this file will be
read in after config.py, it will override it and set
<code class="docutils literal"><span class="pre">DEBUG</span> <span class="pre">=</span> <span class="pre">True</span></code>.</td>
</tr>
<tr class="row-odd"><td>/yourapp/</td>
<td>This is the package that contains your application.</td>
</tr>
<tr class="row-even"><td>/yourapp/__init__.py</td>
<td>This file initializes your application and brings together
all of the various components.</td>
</tr>
<tr class="row-odd"><td>/yourapp/views.py</td>
<td>This is where the routes are defined. It may be split into
a package of its own (<em>yourapp/views/</em>) with related
views grouped together into modules.</td>
</tr>
<tr class="row-even"><td>/yourapp/models.py</td>
<td>This is where you define the models of your application.
This may be split into several modules in the same way as
views.py.</td>
</tr>
<tr class="row-odd"><td>/yourapp/static/</td>
<td>This directory contains the public CSS, JavaScript, images and
other files that you want to make public via your app. It
is accessible from yourapp.com/static/ by default.</td>
</tr>
<tr class="row-even"><td>/yourapp/templates/</td>
<td>This is where you&#8217;ll put the Jinja2 templates for your app.</td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="blueprints">
<h4>Blueprints<a class="headerlink" href="#blueprints" title="Permalink to this headline">¶</a></h4>
<p>At some point you may find that you have a lot of related routes. If
you&#8217;re like me, your first thought will be to split <em>views.py</em> into a
package and group those views into modules. When you&#8217;re at this point,
it may be time to factor your application into blueprints.</p>
<p>Blueprints are essentially components of your app defined in a somewhat
self-contained manner. They act as apps within your application. You
might have different blueprints for the admin panel, the front-end and
the user dashboard. This lets you group views, static files and
templates by components, while letting you share models, forms and other
aspects of your application between these components. We&#8217;ll talk about
using Blueprints to organize your application soon.</p>
</div>
</div>
<div class="section" id="summary">
<h3>Summary<a class="headerlink" href="#summary" title="Permalink to this headline">¶</a></h3>
<ul class="simple">
<li>Using a single module for your application is good for quick
projects.</li>
<li>Using a package for your application is good for projects with views,
models, forms and other components.</li>
<li>Blueprints are a great way to organize projects with several distinct
components.</li>
</ul>
</div>

********************

## django

 | HackerNews        | Medium         | Reddit  |  Quora-QA  | Stack-Overflow-QA | Awesome-gh | Online-Courses (lynda.com) | Official docs|
| ------------- |:-------------:| -----:| -----:|-----:|-----:|-----:|-----:|
|  [django](https://hn.algolia.com/?query=django&sort=byPopularity&prefix&page=0&dateRange=all&type=story)  | [django](https://medium.com/tag/django) | [django](https://www.reddit.com/r/django/)  | [django](https://www.quora.com/topic/Django-web-framework) |  [django](https://stackoverflow.com/questions/tagged/django)    | [django](https://github.com/rosarior/awesome-django), [awesome-python](https://github.com/vinta/awesome-python)  | [django](https://www.lynda.com/Django-tutorials/8494-0.html),   |[django](https://www.djangoproject.com/)  |



<div class="section" id="project-structure">
<span id="label-project-structure"></span><h3>Project Structure<a class="headerlink" href="#project-structure" title="Permalink to this headline">¶</a></h3>
<p>The <em>normal</em> Django workflow, as it is described <a class="reference external" href="https://docs.djangoproject.com/en/1.8/intro/tutorial01/#creating-a-project">in the official Django
tutorial</a>
starts a project with the command:</p>
<div class="highlight-python"><div class="highlight"><pre>$ django-admin startproject [projectname]
</pre></div>
</div>
<p>Your project will look like this:</p>
<div class="highlight-python"><div class="highlight"><pre>[projectname]/
├── [projectname]/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py
</pre></div>
</div>
<p>However, the <tt class="docutils literal"><span class="pre">startproject</span></tt>-command takes an optional argument <tt class="docutils literal"><span class="pre">template</span></tt>
which can be used to specify a project template to be used for project
creation (see <a class="reference external" href="https://docs.djangoproject.com/en/1.8/ref/django-admin/#startproject-projectname-destination">Django documentation</a>).</p>
<p>The <tt class="docutils literal"><span class="pre">template</span></tt>-argument works with paths on your local machine, but also
supports URLs. So you can easily fetch this skeleton from <strong>GitHub</strong> using this
command:</p>
<div class="highlight-python"><div class="highlight"><pre>$ django-admin startproject --template=https://github.com/Mischback/django-project-skeleton/archive/development.zip [projectname]
</pre></div>
</div>
<p>Your project will look like this:</p>
<div class="highlight-python"><div class="highlight"><pre>[projectname]/                  &lt;- project root
├── [projectname]/              &lt;- Django root
│   ├── __init__.py
│   ├── settings/
│   │   ├── common.py
│   │   ├── dev.py
│   │   ├── djangodefault.py
│   │   ├── __init__.py
│   │   └── production.py
│   ├── urls.py
│   └── wsgi.py
├── apps/
│   └── __init__.py
├── configs/
│   ├── apache2_vhost.sample
│   └── README
├── doc/
│   ├── Makefile
│   └── source/
│       └── *snap*
├── manage.py
├── README.rst
├── run/
│   ├── media/
│   │   └── README
│   ├── README
│   └── static/
│       └── README
├── static/
│   └── README
└── templates/
    └── README
</pre></div>
</div>
<div class="section" id="django-root">
<h2>Django Root<a class="headerlink" href="#django-root" title="Permalink to this headline">¶</a></h2>
<div class="highlight-python"><div class="highlight"><pre>[projectname]/                  &lt;- project root
├── [projectname]/              &lt;- Django root
│   ├── __init__.py
│   ├── settings/
│   │   ├── common.py
│   │   ├── dev.py
│   │   ├── djangodefault.py
│   │   ├── __init__.py
│   │   └── production.py
│   ├── urls.py
│   └── wsgi.py
└── *snap*
</pre></div>
</div>
<p>The Django root directory will be named according to the project name you
specified in <tt class="docutils literal"><span class="pre">django-admin</span> <span class="pre">startproject</span> <span class="pre">[projectname]</span></tt>. This directory is the
project&#8217;s connection with Django.</p>
<dl class="docutils">
<dt><tt class="docutils literal"><span class="pre">[projectname]/settings/</span></tt></dt>
<dd>Instead of a plain <em>settings</em>-file, the configuration is split into several
files in this Python module. For an in-depth documentation of these
settings see <a class="reference internal" href="settings.html#label-project-settings"><em>Settings</em></a>.</dd>
<dt><tt class="docutils literal"><span class="pre">[projectname]/urls.py</span></tt></dt>
<dd>The root URL configuration of the project. The only configured set of urls
is the admin-application. For background information see <a class="reference external" href="http://www.djangobook.com/en/2.0/chapter03.html">The Django Book
Chapter 3</a> and <a class="reference external" href="http://www.djangobook.com/en/2.0/chapter08.html">The
Django Book Chapter 8</a>.</dd>
<dt><tt class="docutils literal"><span class="pre">[projectname]/wsgi.py</span></tt></dt>
<dd>Deploying Django makes use of WSGI, the Pythonic way of deploying web
applications. See the <a class="reference external" href="https://docs.djangoproject.com/en/1.8/howto/deployment/wsgi/">official settings documentation on WSGI</a> for more
details. The default WSGI-application is modified to use our
<tt class="docutils literal"><span class="pre">settings</span></tt>-module.</dd>
</dl>
</div>
<div class="section" id="apps">
<h3>apps/<a class="headerlink" href="#apps" title="Permalink to this headline">¶</a></h3>
<div class="highlight-python"><div class="highlight"><pre>[projectname]/                  &lt;- project root
├── *snap*
├── apps/
│   └── __init__.py
└── *snap*
</pre></div>
</div>
<p>This directory is used for custom applications. You can safely remove this
directory, if you do not plan to develop custom applications. Most of a
Django project&#8217;s apps will be installed into the Python path and not be kept
in your project root.</p>
</div>
<div class="section" id="configs">
<h3>configs/<a class="headerlink" href="#configs" title="Permalink to this headline">¶</a></h3>
<p>This directory contains configuration files for deployment. Now only a
configuration file for deployment with <strong>Apache2</strong> and <strong>mod_wsgi</strong> is
provided.</p>
<div class="highlight-python"><div class="highlight"><pre>[projectname]/                  &lt;- project root
├── *snap*
├── configs/
│   ├── apache2_vhost.sample
│   └── README
└── *snap*
</pre></div>
</div>
<p><strong>Please note:</strong> It is strongly advised to keep your actual server
configuration private. Therefore a <tt class="docutils literal"><span class="pre">.gitignore</span></tt>-file is provided, which will
only include files ending with the suffix <tt class="docutils literal"><span class="pre">.sample</span></tt> into <em>Git</em>.</p>
<p>For a brief overview of the <tt class="docutils literal"><span class="pre">configs/apach2_vhost.sample</span></tt> refer to
<a class="reference internal" href="apache2_vhost.html#label-apache2-vhost"><em>Apache2 Virtual Host Configuration</em></a>.</p>
</div>
<div class="section" id="doc">
<h2>doc/<a class="headerlink" href="#doc" title="Permalink to this headline">¶</a></h2>
<div class="highlight-python"><div class="highlight"><pre>[projectname]/                  &lt;- project root
├── *snap*
├── doc/
│   ├── Makefile
│   └── source/
│       └── *snap*
└── *snap*
</pre></div>
</div>
<p>This directory contains the source files for this documentation.</p>
<p>You can safely remove this directory, if you just want to use the skeleton for
your own project.</p>
</div>
<div class="section" id="run">
<h3>run/<a class="headerlink" href="#run" title="Permalink to this headline">¶</a></h3>
<div class="highlight-python"><div class="highlight"><pre>[projectname]/                  &lt;- project root
├── *snap*
├── run/
│   ├── media/
│   │   └── README
│   ├── README
│   └── static/
│       └── README
└── *snap*
</pre></div>
</div>
<p>This directory contains necessary files for running Django. All these files
may contain sensible or useless information, so you will not want to keep this
files in version control. A <tt class="docutils literal"><span class="pre">.gitignore</span></tt>-file is prepared.</p>
<p>This directory will contain the SQLite database file (if you keep the provided
<tt class="docutils literal"><span class="pre">dev</span></tt>-settings) and the <em>SECRET_KEY</em> of Django. For a detailled explanation
see <a class="reference internal" href="settings.html#label-project-settings"><em>Settings</em></a>.</p>
<dl class="docutils">
<dt><tt class="docutils literal"><span class="pre">run/media/</span></tt></dt>
<dd>Django uses a special folder to store user-provided files (uploads). In the
settings-module of this skeleton this directory is set as <tt class="docutils literal"><span class="pre">MEDIA_ROOT</span></tt>.</dd>
<dt><tt class="docutils literal"><span class="pre">run/static/</span></tt></dt>
<dd>Similar to media files, all static assets (i.e. stylesheets, javascript
files, images) are served from a special directory.</dd>
</dl>
</div>
<div class="section" id="static-and-templates">
<h3>static/ and templates/<a class="headerlink" href="#static-and-templates" title="Permalink to this headline">¶</a></h3>
<div class="highlight-python"><div class="highlight"><pre>[projectname]/                  &lt;- project root
├── *snap*
├── static/
│   └── README
└── templates/
    └── README
</pre></div>
</div>
<p>These directories are used for project wide files, meaning project wide static
assets and templates.</p>
<dl class="docutils">
<dt><tt class="docutils literal"><span class="pre">static/</span></tt></dt>
<dd>This directory is used to provide our project wide static assets. Please
refer to <a class="reference external" href="https://docs.djangoproject.com/en/1.8/howto/static-files/#configuring-static-files">the Django documentation</a>
for more details. <a class="reference internal" href="settings.html#label-project-settings"><em>Settings</em></a> documents the
<tt class="docutils literal"><span class="pre">STATICFILES_DIRS</span></tt>-setting.</dd>
<dt><tt class="docutils literal"><span class="pre">templates/</span></tt></dt>
<dd>This directory is used to provide our project wide templates.
<a class="reference internal" href="settings.html#label-project-settings"><em>Settings</em></a> documents the <tt class="docutils literal"><span class="pre">TEMPLATE_DIRS</span></tt>-setting.</dd>
</dl>
</div>

*********************************
## Ruby
<h3><span class="mw-headline" id="Early_concept">Early concept</span></span></h3>
<p>Ruby was conceived on February 24, 1993. In a 1999 post to the <i>ruby-talk</i> mailing list, Ruby author Yukihiro Matsumoto describes some of his early ideas about the language:<sup id="cite_ref-12" class="reference"><a href="#cite_note-12">[12]</a></sup></p>
<blockquote class="templatequote">
<p>I was talking with my colleague about the possibility of an object-oriented scripting language. I knew Perl (Perl4, not Perl5), but I didn't like it really, because it had the smell of a <a href="https://en.wikipedia.org/wiki/Toy_language" class="mw-redirect" title="Toy language">toy language</a> (it still has). The object-oriented language seemed very promising. I knew <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a> then. But I didn't like it, because I didn't think it was a true object-oriented language&#160;— OO features appeared to be add-on to the language. As a language maniac and OO fan for 15 years, I really wanted a genuine object-oriented, easy-to-use scripting language. I looked for but couldn't find one. So I decided to make it.</p>
</blockquote>
<p>Matsumoto describes the design of Ruby as being like a simple <a href="https://en.wikipedia.org/wiki/Lisp_(programming_language)" title="Lisp (programming language)">Lisp</a> language at its core, with an object system like that of Smalltalk, blocks inspired by <a href="https://en.wikipedia.org/wiki/Higher-order_function" title="Higher-order function">higher-order functions</a>, and practical utility like that of Perl.<sup id="cite_ref-13" class="reference"><a href="#cite_note-13">[13]</a></sup></p>
<h3><span id="The_name_&quot;Ruby&quot;"></span></span></h3>
<p>The name "Ruby" originated during an online chat session between Matsumoto and Keiju Ishitsuka on February 24, 1993, before any code had been written for the language.<sup id="cite_ref-rubyconf-history-of-ruby_14-0" class="reference"><a href="#cite_note-rubyconf-history-of-ruby-14">[14]</a></sup> Initially two names were proposed: "<a href="https://en.wikipedia.org/wiki/Coral" title="Coral">Coral</a>" and "<a href="https://en.wikipedia.org/wiki/Ruby" title="Ruby">Ruby</a>". Matsumoto chose the latter in a later e-mail to Ishitsuka.<sup id="cite_ref-15" class="reference"><a href="#cite_note-15">[15]</a></sup> Matsumoto later noted a factor in choosing the name "Ruby"&#160;– it was the <a href="https://en.wikipedia.org/wiki/Birthstone" title="Birthstone">birthstone</a> of one of his colleagues.<sup id="cite_ref-16" class="reference"><a href="#cite_note-16">[16]</a></sup><sup id="cite_ref-17" class="reference"><a href="#cite_note-17">[17]</a></sup></p>
<h3><span class="mw-headline" id="First_publication">First publication</span></span></h3>
<p>The first public release of Ruby 0.95 was announced on Japanese domestic <a href="https://en.wikipedia.org/wiki/Newsgroup" class="mw-redirect" title="Newsgroup">newsgroups</a> on December 21, 1995.<sup id="cite_ref-18" class="reference"><a href="#cite_note-18">[18]</a></sup><sup id="cite_ref-19" class="reference"><a href="#cite_note-19">[19]</a></sup> Subsequently, three more versions of Ruby were released in two days.<sup id="cite_ref-rubyconf-history-of-ruby_14-1" class="reference"><a href="#cite_note-rubyconf-history-of-ruby-14">[14]</a></sup> The release coincided with the launch of the <a href="https://en.wikipedia.org/wiki/Japanese_language" title="Japanese language">Japanese-language</a> <i>ruby-list</i> mailing list, which was the first mailing list for the new language.</p>
<p>Already present at this stage of development were many of the features familiar in later releases of Ruby, including <a href="https://en.wikipedia.org/wiki/Object-oriented_programming" title="Object-oriented programming">object-oriented</a> design, <a href="https://en.wikipedia.org/wiki/Class_(computer_science)" class="mw-redirect" title="Class (computer science)">classes</a> with inheritance, <a href="https://en.wikipedia.org/wiki/Mixin" title="Mixin">mixins</a>, <a href="https://en.wikipedia.org/wiki/Iterator" title="Iterator">iterators</a>, <a href="https://en.wikipedia.org/wiki/Closure_(computer_science)" class="mw-redirect" title="Closure (computer science)">closures</a>, <a href="https://en.wikipedia.org/wiki/Exception_handling" title="Exception handling">exception handling</a> and <a href="https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)" title="Garbage collection (computer science)">garbage collection</a>.<sup id="cite_ref-20" class="reference"><a href="#cite_note-20">[20]</a></sup></p>
<h3><span class="mw-headline" id="Early_releases">Early releases</span></span></h3>
<p>Following the release of Ruby 0.95 in 1995, several stable versions of Ruby were released in the following years:</p>
<ul>
<li>Ruby 1.0: December 25, 1996<sup id="cite_ref-rubyconf-history-of-ruby_14-2" class="reference"><a href="#cite_note-rubyconf-history-of-ruby-14">[14]</a></sup></li>
<li>Ruby 1.2: December 1998</li>
<li>Ruby 1.4: August 1999</li>
<li>Ruby 1.6: September 2000</li>
</ul>
<p>In 1997, the first article about Ruby was published on the Web. In the same year, Matsumoto was hired by netlab.jp to work on Ruby as a full-time developer.<sup id="cite_ref-rubyconf-history-of-ruby_14-3" class="reference"><a href="#cite_note-rubyconf-history-of-ruby-14">[14]</a></sup></p>
<p>In 1998, the Ruby Application Archive was launched by Matsumoto, along with a simple English-language homepage for Ruby.<sup id="cite_ref-rubyconf-history-of-ruby_14-4" class="reference"><a href="#cite_note-rubyconf-history-of-ruby-14">[14]</a></sup></p>
<p>In 1999, the first English language mailing list <i>ruby-talk</i> began, which signaled a growing interest in the language outside Japan.<sup id="cite_ref-linuxdevcenter_21-0" class="reference"><a href="#cite_note-linuxdevcenter-21">[21]</a></sup> In this same year, Matsumoto and Keiju Ishitsuka wrote the first book on Ruby, <i>The Object-oriented Scripting Language Ruby</i> (オブジェクト指向スクリプト言語 Ruby), which was published in Japan in October 1999. It would be followed in the early 2000s by around 20 books on Ruby published in Japanese.<sup id="cite_ref-rubyconf-history-of-ruby_14-5" class="reference"><a href="#cite_note-rubyconf-history-of-ruby-14">[14]</a></sup></p>
<p>By 2000, Ruby was more popular than Python in Japan.<sup id="cite_ref-22" class="reference"><a href="#cite_note-22">[22]</a></sup> In September 2000, the first English language book <i><a href="https://en.wikipedia.org/wiki/Programming_Ruby" title="Programming Ruby">Programming Ruby</a></i> was printed, which was later freely released to the public, further widening the adoption of Ruby amongst English speakers. In early 2002, the English-language <i>ruby-talk</i> mailing list was receiving more messages than the Japanese-language <i>ruby-list</i>, demonstrating Ruby's increasing popularity in the English-speaking world.</p>
<h3><span class="mw-headline" id="Ruby_1.8">Ruby 1.8</span></span></h3>
<p>Ruby 1.8 was initially released in August 2003, was stable for a long time, and was retired June 2013.<sup id="cite_ref-1.8.7-retirement_23-0" class="reference"><a href="#cite_note-1.8.7-retirement-23">[23]</a></sup> Although deprecated, there is still code based on it. Ruby 1.8 is only partially compatible with Ruby 1.9.</p>
<p>Ruby 1.8 has been the subject of several industry standards. The language specifications for Ruby were developed by the Open Standards Promotion Center of the Information-Technology Promotion Agency (a <a href="https://en.wikipedia.org/wiki/Government_of_Japan" title="Government of Japan">Japanese government</a> agency) for submission to the <a href="https://en.wikipedia.org/wiki/Japanese_Industrial_Standards_Committee" title="Japanese Industrial Standards Committee">Japanese Industrial Standards Committee</a> (JISC) and then to the <a href="https://en.wikipedia.org/wiki/International_Organization_for_Standardization" title="International Organization for Standardization">International Organization for Standardization</a> (ISO). It was accepted as a Japanese Industrial Standard (JIS X 3017) in 2011<sup id="cite_ref-24" class="reference"><a href="#cite_note-24">[24]</a></sup> and an international standard (<a href="/w/index.php?title=ISO/IEC_30170&amp;action=edit&amp;redlink=1" class="new" title="ISO/IEC 30170 (page does not exist)">ISO/IEC 30170</a>) in 2012.<sup id="cite_ref-25" class="reference"><a href="#cite_note-25">[25]</a></sup><sup id="cite_ref-26" class="reference"><a href="#cite_note-26">[26]</a></sup></p>
<p>Around 2005, interest in the Ruby language surged in tandem with <a href="https://en.wikipedia.org/wiki/Ruby_on_Rails" title="Ruby on Rails">Ruby on Rails</a>, a <a href="https://en.wikipedia.org/wiki/Web_framework" title="Web framework">web framework</a> written in Ruby. Rails is frequently credited with increasing awareness of Ruby.<sup id="cite_ref-27" class="reference"><a href="#cite_note-27">[27]</a></sup></p>
<h3><span class="mw-headline" id="Ruby_1.9">Ruby 1.9</span></span></h3>
<p>Ruby 1.9 was released in December 2007. Effective with Ruby 1.9.3, released October 31, 2011,<sup id="cite_ref-28" class="reference"><a href="#cite_note-28">[28]</a></sup> Ruby switched from being dual-licensed under the Ruby License and the GPL to being dual-licensed under the Ruby License and the two-clause BSD license.<sup id="cite_ref-29" class="reference"><a href="#cite_note-29">[29]</a></sup> Adoption of 1.9 was slowed by changes from 1.8 that required many popular third party <a href="#Repositories_and_libraries">gems</a> to be rewritten.</p>
<p>Ruby 1.9 introduces many significant changes over the 1.8 series.<sup id="cite_ref-30" class="reference"><a href="#cite_note-30">[30]</a></sup> Examples:</p>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Local_variable" title="Local variable">block local</a> variables (variables that are local to the <a href="https://en.wikipedia.org/wiki/Block_(programming)" title="Block (programming)">block</a> in which they are declared)</li>
<li>an additional <a href="https://en.wikipedia.org/wiki/Anonymous_function" title="Anonymous function">lambda</a> syntax: <code class="mw-highlight" id="" style="" dir="ltr"><span class="n">f</span> <span class="o">=</span> <span class="o">-&gt;</span><span class="p">(</span><span class="n">a</span><span class="p">,</span><span class="n">b</span><span class="p">)</span> <span class="p">{</span> <span class="nb">puts</span> <span class="n">a</span> <span class="o">+</span> <span class="n">b</span> <span class="p">}</span></code></li>
<li>per-string <a href="https://en.wikipedia.org/wiki/Character_encoding" title="Character encoding">character encodings</a> are supported</li>
<li>new socket API (<a href="https://en.wikipedia.org/wiki/IPv6" title="IPv6">IPv6</a> support)</li>
<li><code>require_relative</code> import security</li>
</ul>
<p>Ruby 1.9 has been obsolete since February 23, 2015,<sup id="cite_ref-31" class="reference"><a href="#cite_note-31">[31]</a></sup> and it will no longer receive bug and security fixes. Users are advised to upgrade to a more recent version.</p>
<h3><span class="mw-headline" id="Ruby_2.0">Ruby 2.0</span></span></h3>
<p>Ruby 2.0 added several new features, including:</p>
<ul>
<li>method keyword arguments,</li>
<li>a new method, <code>Module#prepend</code>, for extending a class,</li>
<li>a new literal for creating an array of symbols,</li>
<li>new API for the <a href="https://en.wikipedia.org/wiki/Lazy_evaluation" title="Lazy evaluation">lazy evaluation</a> of Enumerables, and</li>
<li>a new convention of using #to_h to convert objects to Hashes.<sup id="cite_ref-32" class="reference"><a href="#cite_note-32">[32]</a></sup></li>
</ul>
<p>Ruby 2.0 is intended to be fully backward compatible with Ruby 1.9.3. As of the official 2.0.0 release on February 24, 2013, there were only five known (minor) incompatibilities.<sup id="cite_ref-2-0-release-incompatibilities_33-0" class="reference"><a href="#cite_note-2-0-release-incompatibilities-33">[33]</a></sup></p>
<p>It has been obsolete since February 22, 2016,<sup id="cite_ref-34" class="reference"><a href="#cite_note-34">[34]</a></sup> and it will no longer receive bug and security fixes. Users are advised to upgrade to a more recent version.</p>
<h3><span class="mw-headline" id="Ruby_2.1">Ruby 2.1</span></span></h3>
<p>Ruby 2.1.0 was released on Christmas Day in 2013.<sup id="cite_ref-2-1-0-release_35-0" class="reference"><a href="#cite_note-2-1-0-release-35">[35]</a></sup> The release includes speed-ups, bugfixes, and library updates.</p>
<p>Starting with 2.1.0, Ruby's versioning policy is more like <a href="https://en.wikipedia.org/wiki/Semantic_versioning" class="mw-redirect" title="Semantic versioning">semantic versioning</a>.<sup id="cite_ref-semantic-versioning_36-0" class="reference"><a href="#cite_note-semantic-versioning-36">[36]</a></sup> Although similar, Ruby's versioning policy is not compatible with semantic versioning:</p>
<table class="wikitable">
<tr>
<th>Ruby</th>
<th>Semantic versioning</th>
</tr>
<tr>
<td><b>MAJOR</b>: Increased when incompatible change which can’t be released in MINOR. Reserved for special events.</td>
<td><b>MAJOR</b>: Increased when you make incompatible API changes.</td>
</tr>
<tr>
<td><b>MINOR</b>: increased every Christmas, <i>may be</i> API incompatible.</td>
<td><b>MINOR</b>: increased when you add functionality in a <i>backwards-compatible</i> manner.</td>
</tr>
<tr>
<td><b>TEENY</b>: security or bug fix which maintains API compatibility. May be increased more than 10 (such as 2.1.11), and will be released every 2–3 months.</td>
<td><b>PATCH</b>: increased when you make backwards-compatible bug fixes.</td>
</tr>
<tr>
<td><b>PATCH</b>: number of commits since last MINOR release (will be reset at 0 when releasing MINOR).</td>
<td>-</td>
</tr>
</table>
<p>Semantic versioning also provides additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format, not available at Ruby.</p>
<p>Ruby 2.1 has been obsolete since April 1, 2017,<sup id="cite_ref-37" class="reference"><a href="#cite_note-37">[37]</a></sup> and it will no longer receive bug and security fixes. Users are advised to upgrade to a more recent version.</p>
<h3><span class="mw-headline" id="Ruby_2.2">Ruby 2.2</span></span></h3>
<p>Ruby 2.2.0 was released on Christmas Day in 2014.<sup id="cite_ref-2-2-0-release_38-0" class="reference"><a href="#cite_note-2-2-0-release-38">[38]</a></sup> The release includes speed-ups, bugfixes, and library updates and removes some deprecated APIs. Most notably, Ruby 2.2.0 introduces changes to memory handling&#160;–  an incremental garbage collector, support for garbage collection of symbols and the option to compile directly against jemalloc. It also contains experimental support for using <a href="https://en.wikipedia.org/wiki/Vfork" class="mw-redirect" title="Vfork">vfork</a>(2) with system() and spawn(), and added support for the <a href="https://en.wikipedia.org/wiki/Unicode" title="Unicode">Unicode</a> 7.0 specification.</p>
<p>Features that were made obsolete or removed include callcc, the DL library, Digest::HMAC, lib/rational.rb, lib/complex.rb, GServer, Logger::Application as well as various C API functions.<sup id="cite_ref-obsolete-or-gone-in-2.2_39-0" class="reference"><a href="#cite_note-obsolete-or-gone-in-2.2-39">[39]</a></sup></p>
<dl>
<dt>PowerPC64 performance</dt>
<dd>Since version 2.2.1,<sup id="cite_ref-40" class="reference"><a href="#cite_note-40">[40]</a></sup> Ruby MRI performance on <a href="https://en.wikipedia.org/wiki/Ppc64" title="Ppc64">PowerPC64</a> was improved.<sup id="cite_ref-41" class="reference"><a href="#cite_note-41">[41]</a></sup><sup id="cite_ref-42" class="reference"><a href="#cite_note-42">[42]</a></sup><sup id="cite_ref-43" class="reference"><a href="#cite_note-43">[43]</a></sup></dd>
</dl>
<h3><span class="mw-headline" id="Ruby_2.3">Ruby 2.3</span></span></h3>
<p>Ruby 2.3.0 was released on Christmas Day in 2015. A few notable changes include:</p>
<ul>
<li>The ability to mark all string literals as frozen by default with a consequently large performance increase in string operations.<sup id="cite_ref-44" class="reference"><a href="#cite_note-44">[44]</a></sup></li>
<li>Hash comparison to allow direct checking of key/value pairs instead of just keys.</li>
<li>A new <a href="https://en.wikipedia.org/wiki/Safe_navigation_operator" title="Safe navigation operator">safe navigation operator</a> <code>&amp;.</code> that can ease nil handling (e.g. instead of <code class="mw-highlight" id="" style="" dir="ltr"><span class="k">if</span> <span class="n">obj</span> <span class="o">&amp;&amp;</span> <span class="n">obj</span><span class="o">.</span><span class="n">foo</span> <span class="o">&amp;&amp;</span> <span class="n">obj</span><span class="o">.</span><span class="n">foo</span><span class="o">.</span><span class="n">bar</span></code>, we can use <code>if obj&amp;.foo&amp;.bar</code>).</li>
<li>The <i>did_you_mean</i> gem is now bundled by default and required on startup to automatically suggest similar name matches on a <i>NameError</i> or <i>NoMethodError</i>.</li>
<li><i>Hash#dig</i> and <i>Array#dig</i> to easily extract deeply nested values (e.g. given <code class="mw-highlight" id="" style="" dir="ltr"><span class="n">profile</span> <span class="o">=</span> <span class="p">{</span> <span class="ss">social</span><span class="p">:</span> <span class="p">{</span> <span class="ss">wikipedia</span><span class="p">:</span> <span class="p">{</span> <span class="nb">name</span><span class="p">:</span> <span class="s1">'Foo Baz'</span> <span class="p">}</span> <span class="p">}</span> <span class="p">}</span></code>, the value <i>Foo Baz</i> can now be retrieved by <code>profile.dig(:social,&#160;:wikipedia,&#160;:name)</code>).</li>
<li><code>.grep_v(regexp)</code> which will match all negative examples of a given regular expression in addition to other new features.</li>
</ul>
<p>The 2.3 branch also includes many performance improvements, updates, and bugfixes including changes to Proc#call, Socket and IO use of exception keywords, Thread#name handling, default passive Net::FTP connections, and Rake being removed from stdlib.<sup id="cite_ref-Ruby_2.3.0_NEWS_45-0" class="reference"><a href="#cite_note-Ruby_2.3.0_NEWS-45">[45]</a></sup></p>
<h3><span class="mw-headline" id="Ruby_2.4">Ruby 2.4</span></span></h3>
<p>Ruby 2.4.0 was released on Christmas Day in 2016. A few notable changes include:</p>
<ul>
<li>Binding#irb: Start a REPL session similar to binding.pry</li>
<li>Unify <i>Fixnum</i> and <i>Bignum</i> into <i>Integer</i> class</li>
<li>String supports Unicode case mappings, not just ASCII</li>
<li>a new method, Regexp#match?, which is a faster boolean version of Regexp#match</li>
<li>Thread deadlock detection now shows threads with their backtrace and dependency</li>
</ul>
<p>The 2.4 branch also includes performance improvements to hash table, Array#max, Array#min, and instance variable access.<sup id="cite_ref-:0_46-0" class="reference"><a href="#cite_note-:0-46">[46]</a></sup></p>
<p>Ruby's popularity has been declining since 2014<sup id="cite_ref-47" class="reference"><a href="#cite_note-47">[47]</a></sup> , a slip that may be permanent in the face of increasing competition.<sup id="cite_ref-48" class="reference"><a href="#cite_note-48">[48]</a></sup></p>

*************************


<h3><span class="mw-headline" id="Ruby">List of Ruby Web Frameworks</span></span></h3>

<p>Source: Wikipedia</P>

<div role="note" class="hatnote navigation-not-searchable">Wiki: <a href="https://en.wikipedia.org/wiki/Ruby_(programming_language)" title="Ruby (programming language)">Ruby (programming language)</a></div>
<table class="wikitable sortable" style="font-size: 90%">
<br>
<tr>
<th>Project</th>
<th>Current stable version</th>
<th>Release date</th>
<th><a href="https://en.wikipedia.org/wiki/Software_license" title="Software license">License</a></th>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Camping_(microframework)" title="Camping (microframework)">Camping</a></th>
<td>2.1</td>
<td>2010-08-20</td>
<td><a href="https://en.wikipedia.org/wiki/MIT_License" title="MIT License">MIT</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Padrino_(web_framework)" title="Padrino (web framework)">Padrino</a></th>
<td>0.13.2</td>
<td>2016-05-09<sup id="cite_ref-changes_52-0" class="reference"><a href="#cite_note-changes-52">[52]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/MIT_License" title="MIT License">MIT</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Ruby_on_Rails" title="Ruby on Rails">Ruby on Rails</a></th>
<td>5.1.1</td>
<td>2017-05-12<sup id="cite_ref-53" class="reference"><a href="#cite_note-53">[53]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/MIT_License" title="MIT License">MIT</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh"><a href="https://en.wikipedia.org/wiki/Sinatra_(software)" title="Sinatra (software)">Sinatra</a></th>
<td>2.0.0</td>
<td>2017-05-07<sup id="cite_ref-54" class="reference"><a href="#cite_note-54">[54]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/MIT_License" title="MIT License">MIT</a></td>
</tr>
<tr>
<th style="background: #ececec; color: black; font-weight: bold; vertical-align: middle; text-align: left;" class="table-rh">Hanami</th>
<td>1.0.0</td>
<td>2017-04-06<sup id="cite_ref-55" class="reference"><a href="#cite_note-55">[55]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/MIT_License" title="MIT License">MIT</a></td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/Merb" title="Merb">Merb</a></th>
<td>1.1.3</td>
<td>2010-07-10</td>
<td><a href="https://en.wikipedia.org/wiki/MIT_License" title="MIT License">MIT</a></td>
</tr>
<tr>
<th style="background: #edf; color: black; vertical-align: middle; text-align: left; font-weight: bolder;" class="rh heading table-rh"><a href="https://en.wikipedia.org/wiki/PureMVC" title="PureMVC">PureMVC</a></th>
<td>2.0.4</td>
<td>2008-08-14</td>
<td><a href="https://en.wikipedia.org/wiki/Creative_Commons_license" title="Creative Commons license">CC</a> +Attribution</td>
</tr>
</table>

Lets explore ruby frameworks rails and sinatra

*************************
## Rails

 | HackerNews       | Medium         | Reddit  |  Quora-QA  | Stack-Overflow-QA | Awesome-gh | Online-Courses (lynda.com) | Official docs|
| ------------- |:-------------:| -----:| -----:|-----:|-----:|-----:|-----:|
|  [Rails](https://hn.algolia.com/?query=rails&sort=byPopularity&prefix&page=0&dateRange=all&type=story)   | [Rails](https://medium.com/tag/ruby-on-rails)  |  [Rails](https://www.reddit.com/r/rails/)    | [Rails](https://stackoverflow.com/questions/tagged/ruby-on-rails) | [Rails](https://www.quora.com/topic/Ruby-on-Rails-web-framework) | [Rails](https://github.com/markets/awesome-ruby), [rails-gem](https://github.com/hothero/awesome-rails-gem) | [Rails](https://www.lynda.com/Ruby-on-Rails-training-tutorials/304-0.html)  |[Rails](http://rubyonrails.org/)  |

## Ruby on rails project structure

<p>To create a new Rails app, all we have to do is run the following command:</p>
<pre><code>rails new sample_app
</code></pre>
<p>The above command generates the directory structure that we&rsquo;re discussing today. It <em>might</em> change if you are using an older version of Rails. This article is based on the latest Rails version which, as of this writing, is <code>4.2.4</code>. You can find the version installed in your system by typing this in the console</p>
<pre><code>rails version
=&gt; Rails 4.2.4
</code></pre>
<p>The directory structure,</p>
<pre><code>.
|-- app
|   |-- assets
|   |   |-- images
|   |   |-- javascripts
|   |   |   `-- application.js
|   |   `-- stylesheets
|   |       `-- application.css
|   |-- controllers
|   |   |-- application_controller.rb
|   |   `-- concerns
|   |-- helpers
|   |   `-- application_helper.rb
|   |-- mailers
|   |-- models
|   |   `-- concerns
|   `-- views
|       `-- layouts
|           `-- application.html.erb
|-- bin
|   |-- bundle
|   |-- rails
|   |-- rake
|   |-- setup
|   `-- spring
|-- config
|   |-- application.rb
|   |-- boot.rb
|   |-- database.yml
|   |-- environment.rb
|   |-- environments
|   |   |-- development.rb
|   |   |-- production.rb
|   |   `-- test.rb
|   |-- initializers
|   |   |-- assets.rb
|   |   |-- backtrace_silencers.rb
|   |   |-- cookies_serializer.rb
|   |   |-- filter_parameter_logging.rb
|   |   |-- inflections.rb
|   |   |-- mime_types.rb
|   |   |-- session_store.rb
|   |   `-- wrap_parameters.rb
|   |-- locales
|   |   `-- en.yml
|   |-- routes.rb
|   `-- secrets.yml
|-- config.ru
|-- db
|   `-- seeds.rb
|-- Gemfile
|-- Gemfile.lock
|-- lib
|   |-- assets
|   `-- tasks
|-- log
|-- public
|   |-- 404.html
|   |-- 422.html
|   |-- 500.html
|   |-- favicon.ico
|   `-- robots.txt
|-- Rakefile
|-- README.rdoc
|-- test
|   |-- controllers
|   |-- fixtures
|   |-- helpers
|   |-- integration
|   |-- mailers
|   |-- models
|   `-- test_helper.rb
|-- tmp
|   `-- cache
|       `-- assets
`-- vendor
`-- assets
    |-- javascripts
    `-- stylesheets
</code></pre>
<p>We will go through each directory, one by one, now.</p>
<h3>app</h3>
<p>This is the core directory of your entire app and most of the application-specific code will go into this directory. As you may know, Rails is an MVC framework, which means the application is separated into parts per its purpose in the Model, View, or Controller. These three sections goes inside this directory.</p>
<h3>app/assets</h3>
<p>This contains the static files required for the application&rsquo;s front-end grouped into folders based on their type. The javascript files and stylesheets (CSS) in these folders should be application specific since the external library files would go into another directory (<code>vendor</code>) which we will look at in a bit.</p>
<h3>app/assets/images</h3>
<p>All the images required for the application should go into this directory. The images here are available in views through nifty helpers like <code>image_tag("img_name.png")</code> so that you don&rsquo;t have to specify the relative or absolute path for images.</p>
<h3>app/assets/javascripts</h3>
<p>The javascript files go here. There is a convention to create the JS files for each controller. For example, for <code>books_controller.rb</code>, the JS functions for this controller&rsquo;s views would be <code>books.js</code>.</p>
<h4>app/assets/javascripts/application.js</h4>
<p>The pre-created <code>application.js</code> is a manifest for the entire application&rsquo;s javascript requirements. Rails uses the <a href="https://guides.rubyonrails.org/asset_pipeline.html">asset pipeline</a> for compiling and serving up assets. This means the <code>application.js</code> is the file where you reference the application specific JS files, which are unified and minified before sending it to the views.</p>
<p>Try as much as possible to not create javascript functions in this file.</p>
<h3>app/assets/stylesheets</h3>
<p>Similar to <code>/javascripts</code>, the CSS files go here. The naming convention is also the same as the javascript assets.</p>
<h4>app/assets/stylesheets/application.css</h4>
<p>This file is a manifest for the stylesheets in the application. Similar to <code>application.js</code>, the referenced files are served up as a single stylesheet to the view.</p>
<h3>app/controllers</h3>
<p>This is where all the controller files go. Controllers are responsible for orchestrating the model and views. The naming convention for the file is the pluralized model name + &ldquo;_controller&rdquo;. For example, the controller for the <code>Book</code> model is <code>books_controller.rb</code>, which is called &ldquo;snake case&rdquo;. Also, the controller class will be CamelCase which is <code>BooksController</code>.</p>
<p>The script to generate a controller is:</p>
<pre><code>rails generate controller controller_name action1 action2
</code></pre>
<h3>app/controllers/application_controller.rb</h3>
<p>This is the main controller from which all other controllers inherit. The methods on <code>ApplicationController</code> are available to other controllers as well. This controller inherits from the <code>ActionController::Base</code> module, which has set of methods to work with in controllers.</p>
<h3>app/controllers/concerns</h3>
<p><code>Concerns</code> are modules that can be used across controllers. This is helpful to DRY up your code by implementing reusable functionality inside the directory. The naming convention is <code>module_name.rb</code>.</p>
<h3>app/helpers</h3>
<p>This is where all the helper functions for views reside. There are already a few pre-created helpers available, like the one we reference above (<code>image_tag</code>) for referring to images in views. You can create your own functions in a controller specific helper file, which will be automatically created when you use Rails generators to create the controller. The naming convention is <code>controller_name_helper.rb</code>.</p>
<h3>app/helpers/application_helper.rb</h3>
<p>This is the root helper. Similar to <code>application_controller.rb</code>, functions written here will be available in all the helpers, by default, and in all the views.</p>
<h3>app/mailers</h3>
<p>The <code>mailers</code> directory contains the mail (as in &ldquo;email&rdquo;) specific functions for the application. Mailers are similar to controllers and they will have their view files in <code>app/views/mailer_name/</code>. To generate a mailer you can run the following command</p>
<pre><code>rails generate mailer MailerName
</code></pre>
<p>The first time you generate a mailer, <code>application_mailer.rb</code> is automatically created for you. This will inherit from the <code>ActionMailer::Base</code> and sets the default <code>from</code> address as well as the <code>layout</code> for your mailer views. Subsequent mailers will inherit from <code>ApplicationMailer</code>.</p>
<p>The naming convention is similar to controllers: <code>modelname_mailer.rb</code>. You can read more about mailers <a href="http://guides.rubyonrails.org/v2.3.8/action_mailer_basics.html">here</a>.</p>
<h3>app/models</h3>
<p>All model files live in the <code>app/models</code> directory. Models act as object-relational mappers to the database tables that hold the data. The naming convention is simply <code>modelname.rb</code>. The model name is, by convention, the singular form of the underlying table that represents the model in the database. So, the <code>Book</code> model will be mapped on top of the <code>books</code> table in the database. You can learn more about Rails models in <a href="http://guides.rubyonrails.org/active_model_basics.html">here</a>.</p>
<h3>app/models/concerns</h3>
<p>Model concerns are similar to Controller concerns, containing methods that might be used in multiple model files. This greatly helps with organizing the code.</p>
<h3>app/views</h3>
<p>The third part of the MVC architecture are the views. The files related to the views go into this directory. The files are a combination of HTML and Ruby (called Embedded Ruby or Erb) and are organized based on the controller to which they correspond. There is a view file for each controller action. For example, the <code>BooksController#index</code> action would have it&rsquo;s corresponding view as</p>
<pre><code>app/views/books/index.html.erb
</code></pre>
<p>This is another of Rails&rsquo; conventions, and can be broken. In other words, you can explicitly render any view manually.</p>
<h3>app/views/layouts</h3>
<p>This folder holds the layout for all your view files, which they inherit. Files created in here are available across all the view files.</p>
<p>You can create multiple layouts scoped to parts of application. For example, if we want to create a separate layout for administrative views vs user views, we can achieve it by creating a layout filed named after the controller name. For all <code>AdminController</code> views, create a layout file called <code>admin.html.erb</code> which will then act as the layout for the admin views, as well as any controller that inherits from <code>AdminController</code>.</p>
<p>You can also create partial views here that might be used across controllers.</p>
<h4>app/views/layouts/application.html.erb</h4>
<p>This will be default file created automatically, which will act as the layout for actions in <code>ApplicationController</code> and any other contoller that inherits from <code>ApplicationController</code>.</p>
<h3>bin</h3>
<p>This directory contains Binstubs for the Rails application. Binstubs are nothing but wrappers to run the gem executables scoped to your application. This can be used in place of <code>bundle exec &lt;command&gt;</code>. The default available Binstubs are <code>bundle</code>, <code>rails</code>, <code>rake</code>, <code>setup</code>, and <code>spring</code>. Any of these binstubs can be executed by:</p>
<pre><code>bin/&lt;executable&gt;
</code></pre>
<h3>config</h3>
<p>As the name suggests this contains all the application&rsquo;s configuration files. The database connection and application behavior can be altered by the files inside this directory.</p>
<h3>config/application.rb</h3>
<p>This contains the main configuration for the application, such as the timezone to use, language, and many  other settings. The full list could be found <a href="http://guides.rubyonrails.org/configuring.html">here</a>. Also, note the configurations specified here is for all environments (development, test, and production). Environment specific configurations will go into other files, which we&rsquo;ll see below.</p>
<h3>config/boot.rb</h3>
<p><code>boot.rb</code>, as you might imagine, &ldquo;boots&rdquo; up the Rails application. Rails apps keep gem dependencies in a file called <code>Gemfile</code> in the root of the project. The <code>Gemfile</code> contains all the dependencies required for the application to run. <code>boot.rb</code> verifies that there is actually a <code>Gemfile</code> present and will store the path to this file in an environment variable called <code>BUNDLE_GEMFILE</code> for later use. <code>boot.rb</code> also requires <code>'bundler/setup'</code> which will fetch and build the gems mentioned in the <code>Gemfile</code> using Bundler.</p>
<h3>config/database.yml</h3>
<p>This file holds all the database configuration the application needs. Here, different configurations can be set for different environments.</p>
<h3>config/environment.rb</h3>
<p>This file requires <code>application.rb</code> to initialize the Rails application.</p>
<h3>config/routes.rb</h3>
<p>This is where all the routes of the application are defined. There are different semantics for declaring the routes, examples of which can be found in this file.</p>
<h3>config/secrets.yml</h3>
<p>Newly added in Rails 4.1, this gives you a place to store application secrets. The secrets defined here are available throughout the application using <code>Rails.application.secrets.&lt;secret_name&gt;</code>. You can read more about <code>secrets.yml</code> from the <a href="http://edgeguides.rubyonrails.org/4_1_release_notes.html#config-secrets-yml">release notes</a>.</p>
<h3>config/environments</h3>
<p>As I mentioned above, this folder contains the environment-specific configuration files for the development, test, and production environments. Configurations in <code>application.rb</code> are available in all environments, whereas you can separate out different configurations for the different environments by adding settings to the environment named files inside this directory. Default environment files available are, <code>development.rb</code>, <code>production.rb</code>, <code>test.rb</code>, but you can add others, if needed.</p>
<h3>config/initializers</h3>
<p>This directory contains the list of files that need to be run during the Rails initialization process. Any <code>*.rb</code> file you create here will run during the initialization automatically. For example, constants that you declare in here will then be available throughout your app. The initializer file is triggered from the call in <code>config/environment.rb</code> to <code>Rails.application.initialize!</code>.</p>
<p>There are core initializers, which I&rsquo;ll cover here, but you can add any Ruby file you like. In fact, many Rails gems require an initializer to complete the setup of that gem for your Rails app.</p>
<h4>config/initializers/assets.rb</h4>
<p>This contains configuration for the asset pipeline. It will have only one default configuration already defined, <code>Rails.application.config.assets.version</code>, which is the version for your assets bundle. You can also specify configurations such as adding additional assets path or other items to precompile.</p>
<h4>config/initializers/backtrace_silencers.rb</h4>
<p>You can add backtrace_silencers and filters that might be applicable for your app here. Backtrace filters are nothing but filters that helps to refine the stacktrace when an error occurs. Silencers, on the other hand, let&rsquo;s you silence all the stacktraces from specified gems.</p>
<h4>config/initializers/cookie_serializer.rb</h4>
<p>There is not a whole lot of configuration happening here. It contains specifications for the app&rsquo;s cookie serialization. You can read more about cookie handling in Rails from <a href="http://api.rubyonrails.org/classes/ActionDispatch/Cookies.html">here</a>.</p>
<h4>config/initializers/filter_parameter_logging.rb</h4>
<p>You can add parameters here that might contain sensitive information and that you don&rsquo;t want to display in your logs. By default, the &ldquo;password&rdquo; parameter will be filtered.</p>
<h4>config/initializers/inflections.rb</h4>
<p>You can add/override the inflections (singularizations and pluralizations) for any language in here. You can learn more about the inflections API <a href="http://api.rubyonrails.org/classes/ActiveSupport/Inflector.html">here</a>.</p>
<h4>config/initializers/mime_type.rb</h4>
<p>Add MIME (Multi-purpose Internet Mail Extensions) configurations for your application here to handle different types of files you may want to use. The list of options available in Mime API can be found <a href="http://api.rubyonrails.org/classes/Mime/Type.html">here</a>.</p>
<h4>config/initializers/session_store.rb</h4>
<p>This file contains the underlying session store to use in your app to store sessions. The default is <code>:cookie_store</code>, meaning sessions are stored in browser cookies, but you can change it to one of four options. The options and more about the session store are available <a href="http://guides.rubyonrails.org/action_controller_overview.html#session">here</a>.</p>
<h4>config/initializers/wrap_parameters.rb</h4>
<p>As the name implies, it contains settings for wrapping your parameters. By default, all the parameters are wrapped into a nested hash so that it&rsquo;s available without a root. You can override this or add your custom settings here.</p>
<h3>config/locales</h3>
<p>This has the list of YAML file for each language that holds the keys and values to translate bits of the app. You can learn about internationalization (i18n) and the settings from <a href="http://guides.rubyonrails.org/i18n.html">here</a>.</p>
<h3>db</h3>
<p>All the database related files go inside this folder. The configuration, schema, and migration files can be found here, along with any seed files.</p>
<h3>db/seeds.rb</h3>
<p>This file is used to prefill, or &ldquo;seed&rdquo;, database with required records. You can use normal ActiveRecord methods for record insertion.</p>
<div class="widget maestro maestro-content-type-html " id="maestro-652"><span data-sumome-listbuilder-embed-id="a5047315669ea28f9652485dfd816e21a7b7d3873736b516d897111b300bf50b"></span><script>ga('SitePointPlugin:observeImpressions', 'maestro-652')</script></div><h2>Gemfile</h2>
<p>The <code>Gemfile</code> is the place where all your app&rsquo;s gem dependencies are declared. This file is mandatory, as it includes the Rails core gems, among other gems. You can learn all about Bundler and Gemfiles at the <a href="http://bundler.io">Bundler web site</a>.</p>
<h3>Gemfile.lock</h3>
<p><code>Gemfile.lock</code> holds the gem dependency tree, including all versions, for the app. This file is generated by <code>bundle install</code> on the above <code>Gemfile</code>. It, in effect, locks your app dependencies to specific versions.</p>
<h3>lib</h3>
<p><code>lib</code> directory is where all the application specific libraries goes. Application specific libraries are re-usable generic code extracted from the application. Think of it as an application specific gem.</p>
<h3>lib/assets</h3>
<p>This file holds all the library assets, meaning those items (scripts, stylesheets, images) that are not application specific.</p>
<h3>lib/tasks</h3>
<p>The application&rsquo;s Rake tasks and other tasks can be put in this directory. Rake tasks mentioned here are required by the app&rsquo;s <code>Rakefile</code>, which we&rsquo;ll see below.</p>
<h3>log</h3>
<p>This holds all the log files. Rails automatically creates files for each environment.</p>
<h3>public</h3>
<p>The public directory contains some of the common files for web applications. By default, HTML templates for HTTP errors, such as 404, 422 and 500, are generated along with a <code>favicon</code> and a <code>robots.txt</code> file. Files that are inside this directory are available in <code>https://appname.com/filename</code> directly.</p>
<h3>Rakefile</h3>
<p>Just above, I mentioned that Rake files created inside the <code>lib/tasks</code> are available throughout the app via the Rake module. This is possible because of the Rakefile, which requires <code>application.rb</code> and invokes <code>Rails.application.load_tasks</code>. The call to <code>load_tasks</code> loads all the <code>*.rake</code> files from <code>lib/tasks</code> folder.</p>
<h3>test</h3>
<p>The folder name says it all. This holds all the test files for the app. A subdirectory is created for each component&rsquo;s test files.</p>
<h3>tmp</h3>
<p>This is the temporary directory for the app to hold files like caches. You don&rsquo;t need to worry about this directory, since it&rsquo;s fully managed by Rails itself. But there are few commands available if you want to take control of the directory, which can be found <a href="http://edgeguides.rubyonrails.org/command_line.html#tmp">here</a></p>
<h3>vendor/assets</h3>
<p>This is where the vendor files go, such as javascript libraries and CSS files, among others. Files added here will become part of the asset pipeline automatically.</p>

*******************************************


## Sinatra

 | HackerNews        | Medium         | Reddit  |  Quora-QA  | Stack-Overflow-QA | Awesome-gh | Online-Courses (lynda.com) | Official docs|
| ------------- |:-------------:| -----:| -----:|-----:|-----:|-----:|-----:|
|  [Sinatra](https://hn.algolia.com/?query=sinatra&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story)  | [Sinatra](https://medium.com/tag/sinatra)  | [Sinatra](https://www.quora.com/topic/Sinatra-software)  | [Sinatra](https://www.reddit.com/r/sinatra/) | [Sinatra](https://stackoverflow.com/questions/tagged/sinatra)  |  [Sinatra](https://github.com/coopermaa/awesome-sinatra)   | [Sinatra](https://www.lynda.com/Sinatra-tutorials/11954-0.html)  | [Sinatra](http://www.sinatrarb.com/)    |


### Sinatra Project structure:

<h3 id="what-does-a-sinatra-mvc-file-structure-look-like?">What does a Sinatra MVC File Structure Look Like?</h3>

<p>Take a look at the file structure in this directory. It&#39;s okay if it feels overwhelming at first. We&#39;re going to walk through the different files and folders and discuss what their responsibilities are.</p>
<pre class="highlight shell"><code>├── Gemfile
├── README.md
├── app
│   ├── controllers
│   │   └── application_controller.rb
│   ├── models
│   │   └── model.rb
│   └── views
│       └── index.erb
├── config
│   └── environment.rb
├── config.ru
├── public
│   └── stylesheets
└── spec
    ├── controllers
    ├── features
    ├── models
    └── spec_helper.rb
</code></pre>
<h3 id="gemfile"><code>Gemfile</code></h3>

<p>This holds a list of all the gems needed to run the application. The bundler gem provides us access to a terminal command: <code>bundle install</code>. Bundler will look in the Gemfile and install any gems, as well as any gem dependencies for this application.</p>

<p>Go ahead and enter this command in terminal. It will create a <code>Gemfile.lock</code> file for you, which is just a documentation of what versions of the gem you have installed and should use. The lock word is actually because it makes sure that only one thing is running bundle install at a time.</p>

<h3 id="app-directory"><code>app</code> directory</h3>

<p>This folder holds our MVC directories - <code>models</code>, <code>views</code>, and <code>controllers</code>. We spend most of our time coding in this directory.</p>

<h4 id="models-directory"><code>models</code> directory</h4>

<p>This directory holds the logic behind our application. Typically, these files represent either a component of your application, such as a User, Post, or Comment, or a unit of work. Each file in models typically contains a different class. For example, <code>dog.rb</code> would contain a class called <code>Dog</code>. As you might have guessed, models represent the &quot;M&quot; components of the MVC paradigm.</p>

<p>Models represent the data and object logic of our application.</p>

<p>Create a new file in the models directory to create a dog class. This class should have name, breed, and age attributes which can be set on initialization. You should be able to read and write to these attributes. This class should also keep track of each instance of dog created, as well as a class method <code>all</code> to return an array of those instances.</p>

<h4 id="controllers-directory"><code>controllers</code> directory</h4>

<p>The controllers, such as <code>application_controller.rb</code>, are where the application configurations, routes, and controller actions are implemented. There is typically a class, which in this case we will call <code>ApplicationController</code>, that represents an instance of your application when the server is up and running. The <code>application_controller.rb</code> file represents the &quot;C&quot; components of the MVC paradigm.</p>

<p>(In some simple applications –– including several labs and code-alongs in this track –– the Application Controller will simply be called <code>app.rb</code> and will live in the root directory of the project)</p>

<p>Sometimes our other controllers will use <code>ApplicationController</code> as an inheritance point so that they inherit all the defaults and behaviors defined in our main <code>ApplicationController</code>. Other times our other controllers will simply inherit from <code>Sinatra::Base</code>.</p>

<p>Controllers represent the application logic, generally; the interface and flow of our application.</p>

<p>Let&#39;s go ahead and fill in our controller. You&#39;ll notice in <code>application_controller.rb</code>, we have an <code>ApplicationController</code> class that inherits from <code>Sinatra::Base</code>. When we start up a server, the server will spin up an instance of the <code>ApplicationController</code> class to run our app.</p>

<p>You&#39;ll also notice there is a <code>configure</code> block already in the controller. This configure block tells the controller where to look to find the views (your pages with HTML to display text in the browser.) and the public directory.</p>

<p>When a client makes a request to a server to load an application, the request is received and processed by the controller. We need to set up a controller action to accept the request and respond with the appropriate HTML.</p>

<p>We&#39;ve created a controller action that can receive and respond to a <code>GET</code> request to the root URL <code>&#39;/&#39;</code>. This <code>GET</code> request loads the <code>index.erb</code> file.</p>

<h4 id="views-directory"><code>views</code> directory</h4>

<p>This directory holds the code that will be displayed in the browser. In a Sinatra app we use <code>.erb</code> files instead of <code>.html</code> files because .erb files allow us to include regular, old HTML tags AND special erb tags which contain Ruby code. We can name them anything we like, but by convention, our file names will match up with the action that renders them. For example, a GET request to <code>/</code> typically renders a file called <code>index.erb</code>.</p>

<p>Views represent how things look and are displayed in our application. We&#39;ve created a file <code>index.erb</code> that contains some basic HTML code.</p>

<p>We&#39;ve already told the controller how to load this file in the view.</p>

<h3 id="config.ru-file"><code>config.ru</code> file</h3>

<p>A <code>config.ru</code> file is necessary when building Rack-based applications and using <code>rackup</code>/<code>shotgun</code> to start the application server (the ru stands for rackup).</p>

<p><code>config.ru</code> is first responsible for loading our application environment, code, and libraries.</p>

<p>Once all our code is loaded, <code>config.ru</code> then specifies which controllers to load as part of our application using <code>run</code> or <code>use</code>.</p>

<p>In this case, our <code>config.ru</code> file contains the line <code>run ApplicationController</code>, which creates an instance of our ApplicationController class that can respond to requests from a client.</p>

<h3 id="config-directory"><code>config</code> directory</h3>

<p>This directory holds an <code>environment.rb</code> file. We&#39;ll be using this file to connect up all the files in our application to the appropriate gems and to each other.</p>

<p>This <code>environment.rb</code> file loads Bundler and thus all the gems in our Gemfile, as well as the <code>app</code> directory`.</p>

<h3 id="public-directory"><code>public</code> directory</h3>

<p>The <code>public</code> directory holds our front-end assets. In the example above, it holds a <code>css</code> directory with a stylesheet. Javascript directories and any other front-end assets (like image files) should also be stored in <code>public</code>.</p>

<h3 id="spec-directory"><code>spec</code> directory</h3>

<p>The <code>spec</code> directory contains any tests for our applications. These tests set up any expectations for the rest of the project. These are often broken down into unit tests for models, controller tests for routes, and feature tests, which check the actual behavior for users.</p>

****************************
## Next steps:
* rust --> iron
* elixer --> phoenix
* golang web framework
* I will keep this article updated with my new findings


*****************************
*****************************

<table class="wikitable sortable">
<h2> Programming languages used in most popular websites </h2>
<tr>
 <br> 
<th scope="col"><a href="https://en.wikipedia.org/wiki/Websites" class="mw-redirect" title="Websites">Websites</a></th>
<th scope="col"><a href="https://en.wikipedia.org/wiki/Popularity" title="Popularity">Popularity</a><br />
(unique visitors per month)<sup id="cite_ref-ebz_dec2014_1-0" class="reference"><a href="#cite_note-ebz_dec2014-1">[1]</a></sup></th>
<th scope="col"><a href="https://en.wikipedia.org/wiki/Front_end_processor_(program)" class="mw-redirect" title="Front end processor (program)">Front-end</a><br />
(<a href="https://en.wikipedia.org/wiki/Client-side" title="Client-side">Client-side</a>)</th>
<th scope="col"><a href="https://en.wikipedia.org/wiki/Front_and_back_ends" title="Front and back ends">Back-end</a><br />
(<a href="https://en.wikipedia.org/wiki/Server-side" title="Server-side">Server-side</a>)</th>
<th scope="col"><a href="https://en.wikipedia.org/wiki/Database" title="Database">Database</a></th>
<th scope="col" class="unsortable">Notes</th>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Google.com" class="mw-redirect" title="Google.com">Google.com</a><sup id="cite_ref-2" class="reference"><a href="#cite_note-2">[2]</a></sup></td>
<td>1,600,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/C_(programming_language)" title="C (programming language)">C</a>, <a href="/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Go_(programming_language)" title="Go (programming language)">Go</a>,<sup id="cite_ref-3" class="reference"><a href="#cite_note-3">[3]</a></sup> <a href="/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>, <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a></td>
<td><a href="https://en.wikipedia.org/wiki/BigTable" class="mw-redirect" title="BigTable">BigTable</a>,<sup id="cite_ref-Big_Table_4-0" class="reference"><a href="#cite_note-Big_Table-4">[4]</a></sup> <a href="https://en.wikipedia.org/wiki/MariaDB" title="MariaDB">MariaDB</a><sup id="cite_ref-google_mdb_5-0" class="reference"><a href="#cite_note-google_mdb-5">[5]</a></sup></td>
<td>The most used search engine in the world</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Facebook.com" class="mw-redirect" title="Facebook.com">Facebook.com</a></td>
<td>1,100,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/Hack_(programming_language)" title="Hack (programming language)">Hack</a>, <a href="https://en.wikipedia.org/wiki/PHP" title="PHP">PHP (HHVM)</a>, <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a>, <a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>, <a href="https://en.wikipedia.org/wiki/Erlang_(programming_language)" title="Erlang (programming language)">Erlang</a>, <a href="https://en.wikipedia.org/wiki/D_(programming_language)" title="D (programming language)">D</a>,<sup id="cite_ref-6" class="reference"><a href="#cite_note-6">[6]</a></sup> <a href="https://en.wikipedia.org/wiki/Xhp" class="mw-redirect" title="Xhp">Xhp</a>,<sup id="cite_ref-7" class="reference"><a href="#cite_note-7">[7]</a></sup> <a href="https://en.wikipedia.org/wiki/Haskell_(programming_language)" title="Haskell (programming language)">Haskell</a><sup id="cite_ref-8" class="reference"><a href="#cite_note-8">[8]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/MariaDB" title="MariaDB">MariaDB</a>, <a href="https://en.wikipedia.org/wiki/MySQL" title="MySQL">MySQL</a>,<sup id="cite_ref-9" class="reference"><a href="#cite_note-9">[9]</a></sup> <a href="https://en.wikipedia.org/wiki/Apache_HBase" title="Apache HBase">HBase</a> <a href="https://en.wikipedia.org/wiki/Apache_Cassandra" title="Apache Cassandra">Cassandra</a><sup id="cite_ref-10" class="reference"><a href="#cite_note-10">[10]</a></sup></td>
<td>The most visited social networking site</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/YouTube.com" class="mw-redirect" title="YouTube.com">YouTube.com</a></td>
<td>1,100,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/C_(programming_language)" title="C (programming language)">C</a>, <a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a>, <a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>,<sup id="cite_ref-11" class="reference"><a href="#cite_note-11">[11]</a></sup> <a href="https://en.wikipedia.org/wiki/Go_(programming_language)" title="Go (programming language)">Go</a><sup id="cite_ref-12" class="reference"><a href="#cite_note-12">[12]</a></sup></td>
<td>Vitess, BigTable, <a href="https://en.wikipedia.org/wiki/MariaDB" title="MariaDB">MariaDB</a><sup id="cite_ref-google_mdb_5-1" class="reference"><a href="#cite_note-google_mdb-5">[5]</a></sup><sup id="cite_ref-13" class="reference"><a href="#cite_note-13">[13]</a></sup></td>
<td>The most visited video sharing site</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Yahoo" class="mw-redirect" title="Yahoo">Yahoo</a></td>
<td>750,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/PHP" title="PHP">PHP</a></td>
<td>MySQL, <a href="https://en.wikipedia.org/wiki/PostgreSQL" title="PostgreSQL">PostgreSQL</a>,<sup id="cite_ref-14" class="reference"><a href="#cite_note-14">[14]</a></sup> <a href="https://en.wikipedia.org/wiki/VB.NET" class="mw-redirect" title="VB.NET">VB.NET</a></td>
<td>Yahoo is presently<sup class="noprint Inline-Template" style="white-space:nowrap;">[<i><a href="https://en.wikipedia.org/wiki/Wikipedia:Manual_of_Style/Dates_and_numbers#Chronological_items" title="Wikipedia:Manual of Style/Dates and numbers"><span title="The time period mentioned near this tag is ambiguous. (July 2013)">when?</span></a></i>]</sup> transitioning to <a href="https://en.wikipedia.org/wiki/Node.js" title="Node.js">Node.js</a><sup id="cite_ref-Work_on_NodeJS_at_Yahoo_15-0" class="reference"><a href="#cite_note-Work_on_NodeJS_at_Yahoo-15">[15]</a></sup></td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Amazon.com" class="mw-redirect" title="Amazon.com">Amazon.com</a></td>
<td>500,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>, <a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Perl" title="Perl">Perl</a><sup id="cite_ref-16" class="reference"><a href="#cite_note-16">[16]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/Oracle_Database" title="Oracle Database">Oracle Database</a><sup id="cite_ref-17" class="reference"><a href="#cite_note-17">[17]</a></sup></td>
<td>Popular internet shopping site</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Wikipedia.org" class="mw-redirect" title="Wikipedia.org">Wikipedia.org</a></td>
<td>475,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/PHP" title="PHP">PHP</a>, <a href="https://en.wikipedia.org/wiki/Hack_(programming_language)" title="Hack (programming language)">Hack</a></td>
<td>MySQL<sup class="noprint Inline-Template Template-Fact" style="white-space:nowrap;">[<i><a href="https://en.wikipedia.org/wiki/Wikipedia:Citation_needed" title="Wikipedia:Citation needed"><span title="This claim needs references to reliable sources. (March 2016)">citation needed</span></a></i>]</sup>, <a href="https://en.wikipedia.org/wiki/MariaDB" title="MariaDB">MariaDB</a><sup id="cite_ref-18" class="reference"><a href="#cite_note-18">[18]</a></sup></td>
<td>"<a href="https://en.wikipedia.org/wiki/MediaWiki" title="MediaWiki">MediaWiki</a>" is programmed in <a href="https://en.wikipedia.org/wiki/PHP" title="PHP">PHP</a>, runs on <a href="https://en.wikipedia.org/wiki/HHVM" title="HHVM">HHVM</a>; free online encyclopedia</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Twitter.com" class="mw-redirect" title="Twitter.com">Twitter.com</a></td>
<td>290,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>, <a href="https://en.wikipedia.org/wiki/Scala_(programming_language)" title="Scala (programming language)">Scala</a>, <a href="https://en.wikipedia.org/wiki/Ruby_(programming_language)" title="Ruby (programming language)">Ruby</a><sup id="cite_ref-19" class="reference"><a href="#cite_note-19">[19]</a></sup></td>
<td>MySQL<sup id="cite_ref-20" class="reference"><a href="#cite_note-20">[20]</a></sup></td>
<td>280 characters social network</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Bing_(search_engine)" title="Bing (search engine)">Bing</a></td>
<td>285,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/ASP.NET" title="ASP.NET">ASP.NET</a></td>
<td>Microsoft SQL Server</td>
<td></td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/EBay.com" class="mw-redirect" title="EBay.com">eBay.com</a></td>
<td>285,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>,<sup id="cite_ref-21" class="reference"><a href="#cite_note-21">[21]</a></sup> <a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a>,<sup id="cite_ref-22" class="reference"><a href="#cite_note-22">[22]</a></sup> <a href="https://en.wikipedia.org/wiki/Scala_(programming_language)" title="Scala (programming language)">Scala</a><sup id="cite_ref-23" class="reference"><a href="#cite_note-23">[23]</a></sup></td>
<td><a href="https://en.wikipedia.org/wiki/Oracle_Database" title="Oracle Database">Oracle Database</a></td>
<td>Online auction house</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/MSN.com" class="mw-redirect" title="MSN.com">MSN.com</a></td>
<td>280,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="/wiki/ASP.NET" title="ASP.NET">ASP.NET</a></td>
<td>Microsoft SQL Server</td>
<td>An email client, for simple use. Mostly known as "messenger".</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Microsoft" title="Microsoft">Microsoft</a></td>
<td>270,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/ASP.NET" title="ASP.NET">ASP.NET</a></td>
<td><a href="https://en.wikipedia.org/wiki/Microsoft_SQL_Server" title="Microsoft SQL Server">Microsoft SQL Server</a></td>
<td>Software company</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Linkedin.com" class="mw-redirect" title="Linkedin.com">Linkedin.com</a></td>
<td>260,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>, <a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a>,<sup id="cite_ref-24" class="reference"><a href="#cite_note-24">[24]</a></sup> <a href="https://en.wikipedia.org/wiki/Scala_(programming_language)" title="Scala (programming language)">Scala</a></td>
<td><a href="https://en.wikipedia.org/wiki/Voldemort_(distributed_data_store)" title="Voldemort (distributed data store)">Voldemort</a><sup id="cite_ref-voldemort_li_25-0" class="reference"><a href="#cite_note-voldemort_li-25">[25]</a></sup></td>
<td>World's largest professional network</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Pinterest" title="Pinterest">Pinterest</a></td>
<td>250,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/Django_(web_framework)" title="Django (web framework)">Django</a>,<sup id="cite_ref-26" class="reference"><a href="#cite_note-26">[26]</a></sup> <a href="https://en.wikipedia.org/wiki/Erlang_(programming_language)" title="Erlang (programming language)">Erlang</a></td>
<td><a href="https://en.wikipedia.org/wiki/MySQL" title="MySQL">MySQL</a>, <a href="https://en.wikipedia.org/wiki/Redis" title="Redis">Redis</a> <sup id="cite_ref-bi_pint_27-0" class="reference"><a href="#cite_note-bi_pint-27">[27]</a></sup></td>
<td></td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Wordpress.com" class="mw-redirect" title="Wordpress.com">WordPress.com</a></td>
<td>240,000,000</td>
<td><a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a></td>
<td><a href="https://en.wikipedia.org/wiki/PHP" title="PHP">PHP</a>, <a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a> <sup id="cite_ref-28" class="reference"><a href="#cite_note-28">[28]</a></sup> (Node.js)</td>
<td><a href="https://en.wikipedia.org/wiki/MariaDB" title="MariaDB">MariaDB</a>, <a href="https://en.wikipedia.org/wiki/MySQL" title="MySQL">MySQL</a></td>
<td></td>
</tr>
</table>

**********************************


**a look into brief history of internet timelines**
------------------
<br>

![www](http://malonemediagroup.com/wp-content/uploads/2014/02/historyoftheinternet-timeline.png)

********************

**a look into brief history of social media** 
-----------------
<br>

![social](https://keymediasolutions.com/wp-content/uploads/2017/09/New-Media-Timeline.jpg)

************************
************************************************
************************************************
