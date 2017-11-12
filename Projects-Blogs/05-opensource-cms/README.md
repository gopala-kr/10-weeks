

## content management systems & web services

* Wordpress
* Drupal
* joomla
* Webservices

*************************

In layman's terms, content Management Systems, or CMSs, are platforms that provide graphical interfaces for website management. This means that images, video, text, and even many elements of a website’s layout can be edited by users without the need for any coding or programming.

Broadly speaking, content management describes any system that allows people to more easily change and update content, especially on their websites. When the content (number of pages, images, etc.), and/or the number of contributors, grows large, a content management system (CMS) helps collect and create the content in ways that makes it easy to reuse. 

* A CMS allows a team of contributors to work on the same pages without conflicting (check-in/check-out and workflow control). It can schedule pages to appear and disappear at designated times, and archive the old pages with versioning and revision control. 

* Reuse of content means an item can be edited in one place and be published instantly in many places. But it also means that the different versions of the content can be formatted properly for multiple delivery channels, including the web (HTML and PDF), print, wireless handheld devices, and cell phones. 

* Smaller CMSs are for single web authors working one or a few websites. Enterprise CMSs may control hundreds of thousands of pages on hundreds of websites with many dozens of contributors. In between, there are Team CMSs for corporate departments and smaller organizations. News portal software (slash-alikes and the *nuke family) are a form of community CMS, as are weblog tools (usually for personal publishing) and Wikis (usually for teams of contributors). 

* Some CMSs edit whole web pages, others edit a content template for a page and individual content elements. Both kinds may have form-based text editing, source editing of the markup language, or WYSIWYG (what-you-see-is-what-you-get) visual editing. Smaller CMSs tend to be page-oriented and store HTML. Enterprise CMSs use content templates and usually store content elements as information chunks in XML. Some systems tag and store the information with RDF (Resource Description Framework) metadata for the Semantic Web.



<p>First, let’s take a look at the history of content management systems to understand where they come from and what challenges they were designed to solve.</p>

> ## a brief history of content management systems and WWW

<br>

![a brief history of content management systems and WWW](https://webinerds.com/app/uploads/2015/07/Comp-CMS-01.png)



> The first content management systems that were developed in the second half of the 1990’s simplified web development but still required a fairly high level of programming expertise and elbow grease. In the 90’s most websites were still being coded by hand &#8211; from the ground up, so to speak.


> It became apparent during the early days of the web that website development could benefit from ‘platforms’ or ‘frameworks’ &#8211; in other words, development environments that would give sites a jump-start so that website coders had a foundation to work from. Just as modern PHP application frameworks help web developers not to “reinvent the wheel” by providing components to implement basic services, CMSs allowed faster development of message boards and basic HTML websites and obviated the need to develop websites entirely from scratch.

> Some of the early CMSs such as b2/cafelog and Mambo (mentioned in the timeline above) became the basis for contemporary &#8211; and far more advanced &#8211; content management systems. Many others never survived their infancy.

> While early CMS solutions assumed a fair knowledge of HTML coding and programming, CMSs turned over time (to varying degrees) towards visual-based web development. We’ll explore the origins of so-called “WYSIWYG” editors in the next section.


> ### WYSIWYG Website Creation

> WYSIWYG, or “What You See Is What You Get” website building tools emerged around the World Wide Web’s sixth birthday, beginning to appear in 1996. “WYSIWYG” was originally used in reference to text editors that could display a ‘page’ on-screen that mimicked the actual paper copy that would come out of a printer. John Markoff of the <a href="http://bits.blogs.nytimes.com/2007/10/18/the-real-history-of-wysiwyg/?_r=0" target="_blank">NY Times (October 2007)</a> suggests: “The first true WYSIWYG editor was a program written for the Alto [computer] called Bravo, created in 1974 by Charles Simonyi and Butler Lampson, which would ultimately lead to the development of Microsoft Word some years later.” Office productivity software offered WYSIWYG document creation as far back as the mid-70’s. WYSIWYG website creation emerged on the scene between 1996 and 1997, though it is arguable that capability of WYSIWYG website editors was seriously lacking even into the early 2000’s. Sites like Wix.com, launched in 2006 and offering cloud-based drag-and-drop website building, emerged a full decade after the first generation of WYSIWYG web development software.


> Examples of early WYSIWYG web development tools are:


> * <a href="http://www.w3.org/Amaya/" target="_blank">Amaya</a> &#8211; W3C’s project that was begun in 1996
> * Dreamweaver &#8211; launched by Macromedia in 1997 and bought by Adobe in 2007
> * GoLive &#8211; started by GoNet Communications in 1996 and acquired by Adobe in 1999


> Each of the modern CMSs we are discussing offer WYSIWYG editing to some degree, though WordPress offers the easiest customizations for those who shy away from coding.

****************

## CMS VS web-framework

The question in our case is whether to use a ready made CMS or to create your own system using a framework. The right answer depends on the following:

* budget
* number of users you will have (long term performance concerns)
* further maintenance
* total number of details (bells and whistles) you want to provide on the site
* implementation with third party/custom APIs
* special/custom features that require high level of freedom (example: StackOverflow reward points and badgets)
* As this is a question most of us face pretty often, here are cons and pros of a ready made CMS vs a framework:

**Ready made CMS**

Pros

* faster start and development time if your project generally fits in what the CMS provides
* available modules and themes
* backed up by community, meaning that new features, bugfixes, support, tutorials etc. will be provided to you free of charge
* unified set of standards - it's easier to continue working on an existing CMS site than to take someone else's custom application (this is relative, but the point is that in a site that uses an existing CMS most of the things/setup will be familiar to you while in a custom app the previous developer had more freedom)
* security is something you do not need to worry that much as in a custom app

Cons

* if your requirements are very specific, you will need to override the default workflow of the system; in some cases this can be tricky and will make you spend more time than to write your own
* redundant code in modules/plugins
* performance - a ready made CMS will rarely be as fast as a custom made application
* not suitable for every large website (unless you fit in almost everything that the CMS provides)
* steep learning curve in some cases (Typo3, Drupal)

**Custom application**

Pros

* it's up to you to define the structure and the logic of the application
* app design is made especially for the project you are working on - so there is no redundant code
* freedom to do anything you want

Cons

* expensive - in most cases you/your client will need much more money for a custom app
* further maintenance will be harder
* changes and modifications of the structure can be very time consuming
* if you aren't using a CMF you will have to reinvent the wheel in some aspects

***************


## content management framework

<p>A <b>content management framework</b> (<b>CMF</b>) is a system that facilitates the use of reusable components or customized software for managing Web content. It shares aspects of a <a href="https://en.wikipedia.org/wiki/Web_application_framework" class="mw-redirect" title="Web application framework">Web application framework</a> and a <a href="https://en.wikipedia.org/wiki/Content_management_system" title="Content management system">content management system</a> (CMS).</p>
<p>Below is a list of notable systems that claim to be CMFs.</p>
<table class="wikitable sortable">
<tr style="background:#EFEFEF">
<th>Name</th>
<th>Technologies</th>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Apache_Jackrabbit" title="Apache Jackrabbit">Apache Jackrabbit</a></td>
<td>Java</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/AxKit" title="AxKit">AxKit</a></td>
<td><a href="https://en.wikipedia.org/wiki/Perl" title="Perl">Perl</a></td>
</tr>
<tr>
<td><a href="https://en.wikipedia.orghttps://en.wikipedia.org/wiki/GrandCentral" class="mw-redirect" title="GrandCentral">Grand Central</a></td>
<td><a href="https://en.wikipedia.org/wiki/MySQL" title="MySQL">MySQL</a> and PHP&#160;5</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Jakarta_Slide" title="Jakarta Slide">Jakarta Slide</a></td>
<td>Java</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Open_Semantic_Framework" title="Open Semantic Framework">Open Semantic Framework</a></td>
<td><a href="https://en.wikipedia.org/wiki/Drupal" title="Drupal">Drupal</a>, <a href="https://en.wikipedia.org/wiki/Web_Ontology_Language" title="Web Ontology Language">OWL</a>, <a href="https://en.wikipedia.org/wiki/PHP" title="PHP">PHP</a>, and <a href="https://en.wikipedia.org/wiki/Resource_Description_Framework" title="Resource Description Framework">RDF</a></td>
</tr>
<tr>
<td><a href="/w/index.php?title=Backpack_for_Laravel&amp;action=edit&amp;redlink=1" class="new" title="Backpack for Laravel (page does not exist)">Backpack for Laravel</a></td>
<td>MySQL, PHP 5.6+, PostgreSQL</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/RadPHP" title="RadPHP">RadPHP</a></td>
<td>MySQL, PHP 5.6+, PostgreSQL, and etc.</td>
</tr>
<tr>
<td><a href="/w/index.php?title=Strapi&amp;action=edit&amp;redlink=1" class="new" title="Strapi (page does not exist)">Strapi</a></td>
<td>Node.js, MongoDB, MySQL, PostgreSQL, and etc.</td>
</tr>
</table>



> **List of all [available CMS's](https://github.com/gopala-kr/weekend-with-github/blob/master/Projects-Blogs/05-opensource-cms/list-of-cms.md)**


Lets explore most used CMS's  **wordpress, drupal, joomla in detail..**

<h3>A Quick Comparisons</h3>
<p>Before everything else, here is a quick overview of the three platforms (based on <a href="http://www.internetlivestats.com/total-number-of-websites/">data by Internet Lives Stats</a>):</p>
<table class="default-lines" style="font-size: 0.85em;" summary="How do WP, Joomla, and Drupal stack up" width="100%">
<thead>
<tr>
<th scope="col" width="15%"></th>
<th style="text-align: center;" scope="col" align="center">WordPress</th>
<th style="text-align: center;" scope="col" align="center">Joomla</th>
<th style="text-align: center;" scope="col" align="center">Drupal</th>
</tr>
</thead>
<tbody>
<tr>
<td width="15%">Cost</td>
<td align="center">Free</td>
<td align="center">Free</td>
<td align="center">Free</td>
</tr>
<tr>
<td width="15%">Usage</td>
<td align="center">311,682 million</td>
<td align="center">26,474 million</td>
<td align="center">31,216 million</td>
</tr>
<tr>
<td width="15%">Free Themes</td>
<td align="center">4,000+</td>
<td align="center">1,000+</td>
<td align="center">2,000+</td>
</tr>
<tr>
<td width="15%">Free Plugins</td>
<td align="center">45,000+</td>
<td align="center">7,000+</td>
<td align="center">34,000+</td>
</tr>
<tr>
<td width="15%">Pros</td>
<td align="center">Customizable, easy to use, tons of learning resources, excellent community &amp; support</td>
<td align="center">Easy to learn, great help portal, can be used for social networks, updates integrate seamlessly, more built-in options</td>
<td align="center">More technically advanced, websites generally perform better, enterprise-level security</td>
</tr>
<tr>
<td width="15%">Cons</td>
<td align="center">Needs code for major visual customizations, updates may cause issues with plugins</td>
<td align="center">Modules are hard to maintain, middle-ground CMS (not as easy as WordPress, not as advanced as Drupal)</td>
<td align="center">Users need basic knowledge of HTML, PHP, and other web development languages</td>
</tr>
</tbody>
</table>
<h3>WordPress vs Joomla</h3>
<p>WordPress is considered to be the most suitable platform for beginners. Joomla, however, isn’t too far behind. It also has a smooth learning curve, a user-friendly interface, and modules that can make adding functionalities a breeze.</p>
<p>Whether you’re a new blogger or an experienced web designer, <em>both<b> </b></em>systems are great options for you.</p>
<h3>WordPress vs Drupal</h3>
<p>Without a doubt, WordPress is a lot easier to learn than Drupal. However, it is not nearly as powerful or as secure as Drupal. You don’t have to be an expert in coding to work with Drupal, but you still need a bit of experience to build something functional.</p>
<p>If you are new to blogging, then <em>WordPress<b> </b></em>is the better choice for you. But if you’re experienced with HTML, then <em>Drupal</em> will give you better scalability.</p>

*****************

## wordpress

<div class="row"><div class="col-md-6"><p><strong>Official links </strong></p>
<ul>
<li><a href="http://www.wordpress.org/" target="_blank" rel="noopener noreferrer">WordPress.org</a></li>
<li><a href="https://wordpress.org/news/" target="_blank" rel="noopener noreferrer">WordPress news</a></li>
<li><a href="https://wordpress.org/plugins/" target="_blank" rel="noopener noreferrer">WordPress plugins directory</a></li>
</ul>
<p></div><div class="col-md-6">
<p><strong>Sites powered by WordPress</strong></p>
<ul>
<li><a href="http://www.forbes.com/" target="_blank" rel="noopener noreferrer">Forbes</a></li>
<li><a href="https://techcrunch.com/" target="_blank" rel="noopener noreferrer">Tech Crunch</a></li>
<li><a href="http://www.sony.com/" target="_blank" rel="noopener noreferrer">Sony</a></li>
</ul>
<p></div></div></p>

<p>WordPress is undoubtedly the best content management system for someone who wants to set up and manage a website without having to type a single line of code. <a href="https://wordpress.com/" target="_blank">WordPress.com</a> lets anyone set up a WordPress-powered site in minutes, even offering free hosting with a URL in the format of <i>yoursitename</i>.wordpress.com. Note: wordpress.com is not to be confused with wordpress.org, which hosts downloads of WordPress software, themes, and plugins for those who wish to set up a WordPress installation on their own server or web host.</p>

From it’s humble beginnings as a simple blogging platform in 2003, WordPress has revolutionised the way websites are designed & built.

Statistics show that WordPress is the most popular CMS in the online world today. It powers 27.8% of all sites on the web; with about 50,000 new sites being created daily. However, just because it is the most popular CMS, doesn’t mean it’s the only option.


![wordpress](https://cdn.webhostingsecretrevealed.net/wp-content/uploads/2017/04/wp-usage-statistics.jpg)

***CMS usage and market shares of top 1 million sites based on stats published by BuildWith ([source](https://trends.builtwith.com/cms))***

<p><i>Recommended for: small and medium-sized companies, organizations, dedicated blogs</i></p>
<p><i>Difficulty level: no programming experience required! (but plenty of potential for experts as well!)</i></p>

> ### a brief history of wordpress

> On 27th May 2003, creators Matt Mullenweg and Mike Little launched WordPress as a development of its predecessor b2/cafelog.
B2/cafelog was a blogging platform which was written by Michel Valdrighi in PHP, for use with MySQL.

> The adoption rate of WordPress rocketed in 2004 when version 1.2 was launched, featuring the ability for users to write their own plugins and share them with the blogging community.

> A new theme system was launched in 2005 with version 1.5, and later that year version 2.0 included a new user interface for the admin area, allowing users more control over their sites and the ability to make changes more quickly.

> In 2006 , the company founded by WordPress co-founder Mullenweg Automattic), applied to trademark WordPress and the WordPress logo.
Version 2.5 was launched in 2008 with a new user interface designed by web design agency Happy Cog, followed by a usability study that led to version 2.7, which included a customisable UI.

> In 2010, ownership of the WordPress trademark and logo was transferred from Automattic, the company founded by WordPress co-founder Matt Mullenweg, to the WordPress Foundation. This meant that WordPress was no longer dependent on one company and ensured it would continue to grow.

> 2010 also saw the launch of version 3.0 – a major update which included custom post types, a new default theme and MultiSite.
Version 3.3, launched in 2011 made WordPress easier to use and more appealing to novices.

> By 2013, WordPress was widely acknowledged as the world’s most popular content management system. A flurry of updates led to version 3.8, which brought WordPress a new mobile responsive user interface and more default themes.

> As of February 2017, WordPress is used by 58.7% of all the websites whose content management system is known. This is 27.5% of the top 10 million websites

*****************************


## Technical architecture of WordPress

### WordPress Views

<h3 id="for-end-users">For End-Users</h3>
<ul>
<li><strong>Dashboard</strong></li>
<li><strong>Posts</strong><ul>
<li>All Posts</li>
<li>Add New<ul>
<li>Screen Options</li>
<li>Categories</li>
<li>Tags</li>
<li>Featured Image</li>
<li>Publish</li>
</ul>
</li>
</ul>
</li>
<li><strong>Media</strong></li>
<li><strong>Pages</strong></li>
<li><strong>Comments</strong></li>
<li><strong>Admin Bar</strong><ul>
<li>View Site</li>
<li>Add New Posts &amp; Pages</li>
<li>Edit Profile</li>
<li>Logout</li>
</ul>
</li>
</ul>
<h3 id="for-administrators">For Administrators</h3>
<ul>
<li><strong>Appearance</strong><ul>
<li>Themes</li>
<li>Widgets</li>
<li>Menus</li>
<li>Header</li>
<li>Background</li>
</ul>
</li>
<li><strong>Plugins</strong></li>
<li><strong>Users</strong></li>
<li><strong>Tools</strong> <ul>
<li>Import</li>
<li>Export</li>
<li>Categories &amp; Tags Conversion</li>
</ul>
</li>
<li><strong>Settings</strong><ul>
<li>General</li>
<li>Writing</li>
<li>Reading</li>
<li>Discussion</li>
<li>Media</li>
<li>Permalinks</li>
</ul>
</li>
</ul>

*************

### Technical Details

<ol>
<li><p><strong>Server Programming Language</strong></p>
<ol>
<li>PHP 5.2.4 - <em>Lowest supported WordPress version</em></li>
<li>PHP 5.3</li>
<li>PHP 5.4</li>
<li>PHP 5.5 </li>
<li>PHP 5.6 - <em>Lowest supported PHP version (Doh!)</em></li>
<li>PHP 7.0</li>
</ol>
</li>
<li><p><strong>Web Server</strong></p>
<ul>
<li>Apache</li>
<li>Nginx</li>
<li>LightSpeed</li>
<li>IIS</li>
<li>PHP itself</li>
<li><em>(Other?)</em></li>
</ul>
</li>
<li><p><strong>MySQL/MariaDB Database</strong></p>
<ul>
<li><strong>Content Tables</strong><ul>
<li><code>wp_posts</code></li>
<li><code>wp_postmeta</code></li>
</ul>
</li>
<li><strong>Taxonomy Tables</strong><ul>
<li><code>wp_terms</code></li>
<li><code>wp_term_taxonomy</code></li>
<li><code>wp_term_relationship</code></li>
</ul>
</li>
<li><strong>Comment Tables</strong><ul>
<li><code>wp_comments</code></li>
<li><code>wp_commentmeta</code></li>
</ul>
</li>
<li><strong>Persistent Settings Table</strong><ul>
<li><code>wp_options</code></li>
</ul>
</li>
<li><strong>Deprecated Table</strong><ul>
<li><code>wp_links</code></li>
</ul>
</li>
</ul>
</li>
<li><p><strong>WordPress Core </strong></p>
<ul>
<li>PHP Code</li>
<li>SQL Database</li>
<li>Assets<ul>
<li>JS</li>
<li>CSS</li>
<li>Images</li>
</ul>
</li>
</ul>
</li>
<li><p><strong>A Theme</strong> - <em>(a WordPress-specific concept)</em></p>
<ul>
<li>One (1) at a time</li>
<li>Provides <em>&quot;Look at Feel&quot;</em>  <ul>
<li>May provide functionality <em>(but the community frowns on it)</em></li>
</ul>
</li>
<li>HTML-centric<ul>
<li>Typically <em>HTML in PHP, CSS  + JS</em></li>
</ul>
</li>
</ul>
</li>
<li><p><strong>Plugins</strong> - <em>(a WordPress-specific concept)</em> </p>
<ul>
<li>Provides <em>&quot;Provides Add-on Functionality&quot;</em>  <ul>
<li>Sharing Icons</li>
<li>Backup</li>
<li>Caching</li>
<li>eCommerce</li>
<li>Search Engine Optimization</li>
<li>Fields for Data entry of Post data</li>
</ul>
</li>
<li>Zero (0) or more</li>
<li>Coding-centric<ul>
<li>Typically <em>PHP + JS + Generated HTML+CSS + SQL</em></li>
</ul>
</li>
</ul>
</li>
</ol>

**************

 <h3 id="file-and-directory-layout-of-wordpress">File and Directory Layout of WordPress</h3>
<p>The following are the files and directories you will interact with most often when developing for WordPress:</p>
<pre><code>/index.php
/.htacess
/wp-config.php
/wp-load.php
/wp-login.php
/wp-cron.php
/wp-settings.php
/wp-includes/
/wp-admin/
/wp-content
        |-/themes
        |-/plugins
        |-/mu-plugins
        |-/uploads
</code></pre><h2 id="indexphp"><code>/index.php</code></h2>
<p>The entry point for any page/URL on a WordPress website <em>except</em> admin console pages.</p>
<h2 id="htaccess"><code>/.htaccess</code></h2>
<p>Provides clean URLs <em><strong>if</strong></em> you are running Apache, and more advanced developers can use for other features.</p>
<h2 id="wp-configphp"><code>/wp-config.php</code></h2>
<p>Location of database login and passwords as well as some other configuration.</p>
<h2 id="wp-loadphp"><code>/wp-load.php</code></h2>
<p>File to <code>require()</code> if you want to add a standalone <code>.php</code> URL to your website, e.g. <code>http://example.com/test.php</code>.</p>
<h2 id="wp-loginphp"><code>/wp-login.php</code></h2>
<p>File that loads the admin console login page, e.g. <code>http://example.com/wp-login.php</code>.</p>
<h2 id="wp-cronphp"><code>/wp-cron.php</code></h2>
<p>File that runs any cron tasks defined by a plugin or the theme, e.g. <code>http://example.com/wp-cron.php</code>.</p>
<h2 id="wp-settingsphp"><code>/wp-settings.php</code></h2>
<p>File that bootstraps WordPress. You will never run this directly. However, once you start debugging you will trace through this file repeatedly.</p>
<h2 id="wp-includes"><code>/wp-includes/</code></h2>
<p>Directory containing <em>&quot;core&quot;</em> WordPress files used by both the admin console and the front end of the website.</p>
<h2 id="wp-admin"><code>/wp-admin/</code></h2>
<p>Directory containing <em>&quot;core&quot;</em> WordPress files used only by the admin console <em>(except for a few rare cases)</em>.</p>
<h2 id="wp-content"><code>/wp-content/</code></h2>
<p>Directory where all site builder code goes.  This is not exactly a well-named directory.</p>
<h3 id="wp-contentthemes"><code>/wp-content/themes/</code></h3>
<p>Directory where Themes are installed, including several themes installed along with WordPress core.</p>
<h3 id="wp-contentthemestheme"><code>/wp-content/themes/{theme}/</code></h3>
<p>Each Themes will have it&apos;s own subdirectory.</p>
<h3 id="wp-contentplugins"><code>/wp-content/plugins/</code></h3>
<p>Directory where Plugins are installed, including a few plugins installed along with WordPress core.</p>
<h3 id="wp-contentpluginsplugin"><code>/wp-content/plugins/{plugin}/</code></h3>
<p>Each Plugin <em><strong>should</strong></em> have it&apos;s own subdirectory, though not every plugin will <em>(including the example plugin <code>hello.php</code> which is a pet peeve for many WordPress developers!)</em></p>
<p>The plugins can be activated or deactivated by an administrator.</p>
<h3 id="wp-contentmu-plugins"><code>/wp-content/mu-plugins/</code></h3>
<p>Directory where <em>&quot;Must-Use&quot;</em> Plugins are installed. </p>
<p><em><strong>Fun Fact:</strong></em> The name <em>&quot;MU-Plugins&quot;</em> is a backronym; <em>&quot;MU&quot;</em> originally stood for <em>&quot;Multi-User&quot;</em> when WordPress had a separate multi-user version, which itself was improperly named!  <em>&quot;WordPress Multi-User&quot;</em> was the functional precursor to WordPress&apos; &quot;Multi-Site&quot; installation option in more recent versions.</p>
<h3 id="wp-contentmu-pluginsplugin"><code>/wp-content/mu-plugins/{plugin}/</code></h3>
<p>Each MU-Plugin <em><strong>should</strong></em> have it&apos;s own subdirectory. These plugins will always be loaded and can only be _&quot;deactivated&quot;_by removing them. </p>
<p>Good candidates for MU-Plugins are plugins that the site cannot correctly operate without. For every custom WordPress site there should usually be at least one custom MU-Plugin you or your team will create.</p>
<h3 id="wp-contentmu-pluginsplugin-loaderphp"><code>/wp-content/mu-plugins/plugin-loader.php</code></h3>
<p>WordPress does not load MU-Plugins automatically, you have to <code>require()</code> them. I frequently use a file named <code>plugin-loader.php</code> to include the required <code>required()</code> calls to load my MU-Plugins.</p>
<p><em><strong>Note:</strong></em> This file name is not an official WordPress filename, this is just the name I standardized on for this need. But what this file does it something you will frequently need when building client projects.</p>
<h3 id="wp-contentuploads"><code>/wp-content/uploads/</code></h3>
<p>Directory where photos and other files can be uploaded by the user. This directory should always be writable so if your theme or plugin code needs to save a file you should do so in this directory. Preferably in a sub-directory.</p>
<h3 id="wp-contentuploadsyyyymm"><code>/wp-content/uploads/{yyyy}/{mm}</code></h3>
<p>WordPress automatically generates year and month sub-directories for uploading files, unless it has been configured to work differently.</p>

***************
<h3 id="local-development-options-for-wordpress">Local Development Options for WordPress</h3>
<p>There are many options, some are better, some are easier, all have their tradeoffs.</p>
<ol>
<li><strong>Bare Metal </strong><ul>
<li>Directly install Apache, MySQL, PHP, etc. on Mac OS X</li>
<li>Laravel Valet: Just PHP7 and MySQL)</li>
</ul>
</li>
<li><strong>Packaged Sandboxes</strong><ul>
<li>MAMP and MAMP Pro</li>
<li>XAMPP</li>
</ul>
</li>
<li><strong>Virtual Machines</strong> <em>(Vagrant)</em><ul>
<li>Requires<ul>
<li>VirtualBox (free)</li>
<li>VMWare </li>
<li>Parallels</li>
</ul>
</li>
<li>Available Vagrant <ul>
<li>VVV</li>
<li>Trellis</li>
<li>VIP Quickstart</li>
<li>Scotch Box</li>
<li>Laravel Homestead</li>
<li>WPLib Box</li>
</ul>
</li>
</ul>
</li>
<li><strong>Containers</strong> <em>(Docker)</em><ul>
<li>Mostly not ready for prime time <em>(but almost)</em></li>
</ul>
</li>
<li><strong>Hybrid</strong> <ul>
<li>PressMatic - $129</li>
</ul>
</li>
</ol>

************************
## Drupal

<div class="row"><div class="col-md-6"><p><strong>Official links</strong></p>
<ul>
<li><a href="https://www.drupal.org/">Drupal.org</a></li>
<li><a href="https://www.drupal.org/planet">Drupal news</a></li>
<li><a href="https://www.drupal.org/drupal-services">Drupal services</a></li>
</ul>
<p></div><div class="col-md-6">
<p><strong>Popular Websites Powered by Drupal:</strong></p>
<ul>
<li><a href="https://www.tesla.com/">Tesla</a></li>
<li><a href="http://www.warnerbrosrecords.com/">Warner Bros. Records</a></li>
<li><a href="http://www.ox.ac.uk/">University of Oxford</a></li>
</ul>
<p></div></div></p>
<p>Experienced web developers attest that Drupal is the most powerful CMS. However, it is also the most difficult to use. Due to its flexibility, Drupal is the second most-used CMS in the world, but it is not a favorite amongst beginners.</p>


<p><i>Recommended for: business, government, education, civic engagement platforms</i></p>
<p><i>Difficulty level: some programming experience recommended</i></p>

> ### a brief history of drupal

> Originally written by Dries Buytaert as a message board, Drupal became an open source project in 2001. The name Drupal represents an English rendering of the Dutch word druppel, which means "drop" (as in a water droplet). The name came from the now-defunct Drop.org Web site, whose code slowly evolved into Drupal. Buytaert wanted to call the site "dorp" (Dutch for "village") for its community aspects, but mistyped it when checking the domain name and thought the error sounded better.

> Interest in Drupal got a significant boost in 2003 when it helped build "DeanSpace" for Howard Dean, one of the candidates in the U.S. Democratic Party's primary campaign for the 2004 U.S. presidential election. DeanSpace used open-source sharing of Drupal to support a decentralized network of approximately 50 disparate, unofficial pro-Dean websites that allowed users to communicate directly with one another as well as with the campaign. After Dean ended his campaign, members of his Web team continued to pursue their interest in developing a Web platform that could aid political activism by launching CivicSpace Labs in July 2004, "...the first company with full-time employees that was developing and distributing Drupal technology." Other companies began to also specialize in Drupal development. By 2013 the Drupal Web site listed hundreds of vendors that offered Drupal-related services.

> As of 2014 Drupal is developed by a community, and its popularity is growing rapidly. From July 2007 to June 2008 the Drupal.org site provided more than 1.4 million downloads of Drupal software, an increase of approximately 125% from the previous year.

> As of January 2017 more than 1,180,000 sites use Drupal. These include hundreds of well-known organizations, including corporations, media and publishing companies, governments, non-profits, schools, and individuals. Drupal has won several Packt Open Source CMS Awards and won the Webware 100 [clarification needed] three times in a row.

> On March 5, 2009 Buytaert announced a code freeze for Drupal 7 for September 1, 2009. Drupal 7 was released on January 5, 2011, with release parties in several countries. After that, maintenance on Drupal 5 stopped, with only Drupal 7 and Drupal 6 maintained. Drupal 7 series maintenance updates are released regularly.

> On December 1, 2012, Drupal 8 started its feature completion. About three years later, on October 7, 2015 Drupal 8 first release candidate (rc1) was announced. Drupal 8 includes new features and improvements for both users and developers, including: a revamped user interface; WYSIWYG and in-place editing; improved mobile support; added and improved key contributed modules including Views, Date, and Entity Reference; introduced a new object-oriented backend leveraging Symfony components; revamped configuration management; and improved multilingual support. Drupal 8 rc1 is the collective work of over 3,200 core contributors.

> Drupal 8.0.0 was released on November 19, 2015. A subsequent upgrade to it is also available in the form of Drupal 8.1.0 that brings numerous improvements, including CKEditor WYSIWYG enhancements, added APIs, an improved help page, and two new experimental modules. Experimental modules are meant for testing purposes, but are not yet fully supported.

<br>

![drupal](https://upload.wikimedia.org/wikipedia/commons/5/54/Drupal_release_timeline.png)

**Latest major releases**
<table class="wikitable" border="1" style="float:right; margin-left:9px; background: AliceBlue;">
<tr>
<th>Version</th>
<th>Release date</th>
</tr>
<tr>
<td>8.4.2</td>
<td>November 3, 2017</td>
</tr>
<tr>
<td>8.2.8</td>
<td>April 19, 2017</td>
</tr>
<tr>
<td>7.56</td>
<td>June 21, 2017</sup></td>
</tr>
<tr>
<td>6.38</td>
<td>February 24, 2016</td>
</tr>
<tr>
<td>5.23</td>
<td>August 11, 2010</td>
</tr>
</table>

**********************

## Drupal Technical Architecture

The architecture of Drupal contains the following layers

![Drupal technical architecture](https://www.tutorialspoint.com/drupal/images/drupal-architecture/drupal-architecture.jpg)

* **Users** − These are the users on the Drupal community. The user sends a request to a server using Drupal CMS and web browsers, search engines, etc. acts like clients.

* **Administrator** − Administrator can provide access permission to authorized users and will be able to block unauthorized access. Administrative account will be having all privileges for managing content and administering the site.

* **Drupal** − Drupal is a free and open source Content Management System (CMS) that allows organizing, managing and publishing your content and is built on PHP based environments. Drupal CMS is very flexible and powerful and can be used for building large, complex sites. It is very easy to interact with other sites and technologies using Drupal CMS. Further, you will be able to handle complex forms and workflows.

* **PHP** − Drupal uses PHP in order to work with an application which is created by a user. It takes the help of web server to fetch data from the database. PHP memory requirements depend on the modules which are used in your site. Drupal 6 requires at least 16MB, Drupal 7 requires 32MB and Drupal 8 requires 64MB.

* **Web Server** − Web server is a server where the user interacts and processes requests via HTTP (Hyper Text Transfer Protocol) and serves files that form web pages to web users. The communication between the user and the server takes place using HTTP. You can use different types of web servers such as Apache, IIS, Nginx, Lighttpd, etc.

* Database − Database stores the user information, content and other required data of the site. It is used to store the administrative information to manage the Drupal site. Drupal uses the database to extract the data and enables to store, modify and update the database.


> **more detailed architecture of [Drupal7](https://www.ent.iastate.edu/it/Intro_to_Drupal_7_Architecture.pdf)**


<p>The following detail the directories</p>
<ul><li><strong>/core</strong> - All files required by Drupal's out-of-the-box usage (core), except for files that have an explicit reason to be included in the base (/) directory.</li>
<li><strong>/libraries</strong> - All third party external libraries leveraged by Drupal, such as a WYSIWYG editor. This folder is not included by core, but used with many contributed modules.</li>
<li><strong>/modules</strong> - The directory into which all custom (created by you) and contributed (created by community) modules go.
<ul><li>Splitting this up into the sub-directories <strong>contrib</strong> and <strong>custom</strong> can make it easier to keep track of the modules. You can create subfolders for organization to match your development, storage, usage standards.</li>
</ul></li>
<li><strong>/profile</strong> - All contributed and custom installation profiles.</li>
<li><strong>/themes</strong> - All contributed and custom themes and subthemes. Please note that subthemes do require the base theme to be installed here as well.</li>
<li><strong>sites/[domain OR default]/{modules,themes}</strong> - Site specific modules and themes can be moved into these directories to avoid them showing up on every site. Identical to Drupal 7.</li>
<li><strong>sites/[domain OR default]/files</strong> - The storage of site-specific files. This includes files uploaded by users (such as images) and site configuration (<strong>active</strong> and <strong>staged</strong>). </li>
<li><strong>/vendor</strong> - Backend external libraries that Drupal core depends on (examples being Symfony, Twig).</li>
</ul><h4>Core Folder Directories</h4>
<p>In addition, the folder structure in the /core directory has changed as well.</p>
<ul><li><strong>/core/assets</strong> - Various external libraries used by core (includes jQuery, underscore, modernizer, etc.).</li>
<li><strong>/core/misc</strong> - Frontend code that Drupal core depends on.</li>
<li><strong>/core/includes</strong> - Base-level functionality that Drupal uses through other /core folders.</li>
<li><strong>/core/lib</strong> - Drupal core classes.</li>
<li><strong>/core/modules</strong> - Drupal's core modules.</li>
<li><strong>/core/profiles</strong> - Drupal's core installation profiles. These are <em>Minimal</em>, <em>Standard</em>, <em>Testing</em> and <em>Testing</em> multilingual installation profiles.</li>
<li><strong>/core/scripts</strong> - Various command line interface (CLI) scripts, mostly used by developers.</li>
<li><strong>/core/tests</strong> - Drupal core tests.</li>
<li><strong>/core/themes</strong> - Drupal core themes.</li>
</ul></div></div></div>  </div>

*************************

## Joomla

<div class="row"><div class="col-md-6"><p><strong>Official links</strong></p>
<ul>
<li><a href="http://www.joomla.com/" target="_blank" rel="noopener noreferrer">Joomla.com</a></li>
<li><a href="https://www.joomla.org/announcements.html" target="_blank" rel="noopener noreferrer">Joomla news</a></li>
<li><a href="https://extensions.joomla.org/">Joomla extensions directory</a></li>
</ul>
<p></div><div class="col-md-6">
<p><strong>Popular Websites Powered by Joomla:</strong></p>
<ul>
<li><a href="http://www.liptonicetea.com/">Lipton</a></li>
<li><a href="https://www.linux.com/">Linux</a></li>
<li><a href="http://www.harvard.edu/">Harvard University</a></li>
</ul>
<p></div></div></p>
<p>Joomla is similar to WordPress in many ways. It is also easy to use, easy to install, and can easily be expanded with the help of <em><i>modules – </i></em>the equivalent of WordPress plugins. As a result, it is the second-best options for beginners.</p>

<p><i>Recommended for: companies, institutions, online communities, complex websites </i></p>
<p><i>Difficulty level: intermediate-advanced programming/ development experience recommended</i></p>

<p><strong><strong> </strong></strong></p>
<p>At its core Joomla is designed for online communities, though as with Drupal and WordPress it can be used to do a whole lot more such as blogs and ecommerce. Joomla has a steeper learning curve than the other CMSs we have looked at so far. According to<a href="http://www.miracletutorials.com/wordpress-vs-joomla-review/" target="_blank"> this article </a>on Miracle Tutorials: “You really should get a good book on Joomla if you want to set it up fast. Otherwise you end up fiddling around and getting nowhere for days.” You definitely can’t make this statement about WordPress, and likely not about Drupal either!</p>


> ### a brief history of joomla

> Joomla! was the result of a fork of Mambo on August 17, 2005. At that time, the Mambo name was a trademark of Miro International Pvt. Ltd, who formed a non-profit foundation with the stated purpose of funding the project and protecting it from lawsuits. The Joomla development team claimed that many of the provisions of the foundation structure violated previous agreements made by the elected Mambo Steering Committee, lacked the necessary consultation with key stakeholders and included provisions that violated core open source values.

> Joomla! developers created a website called OpenSourceMatters.org (OSM) to distribute information to the software community. Project leader Andrew Eddie wrote a letter that appeared on the announcements section of the public forum at mamboserver.com. Over one thousand people joined OpenSourceMatters.org within a day, most posting words of encouragement and support. The website received the Slashdot effect as a result. Miro CEO Peter Lamont responded publicly to the development team in an article titled "The Mambo Open Source Controversy — 20 Questions With Miro". This event created controversy within the free software community about the definition of open source. Forums of other open-source projects were active with postings about the actions of both sides.

> In the two weeks following Eddie's announcement, teams were re-organized and the community continued to grow. Eben Moglen and the Software Freedom Law Center (SFLC) assisted the Joomla core team beginning in August 2005, as indicated by Moglen's blog entry from that date and a related OSM announcement. The SFLC continue to provide legal guidance to the Joomla! Project.

> On August 18, Andrew Eddie called for community input to suggest a name for the project. The core team reserved the right for the final naming decision, and chose a name not suggested by the community. On September 22, the new name, Joomla!, was announced. It is the anglicised spelling of the Swahili word jumla, meaning all together or as a whole which also has a similar meaning in at least Amharic, Arabic and Urdu. On September 26, the development team called for logo submissions from the community and invited the community to vote on the logo; the team announced the community's decision on September 29. On October 2, brand guidelines, a brand manual, and a set of logo resources were published.

**Joomla versions**

<table class="wikitable">
<tr>
<th scope="col">Version</th>
<th scope="col">Release date</th>
<th scope="col">Supported until</th>
</tr>
<tr>
<th scope="row">1.0</th>
<td><span class="sortkey" style="display:none;speak:none">2005-09-22</span><span style="white-space:nowrap">September 22, 2005</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2009-07-22</span><span style="white-space:nowrap">July 22, 2009</span></td>
</tr>
<tr>
<th scope="row">1.5 (LTS)</th>
<td><span class="sortkey" style="display:none;speak:none">2008-01-22</span><span style="white-space:nowrap">January 22, 2008</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2012-12-01</span><span style="white-space:nowrap">December 1, 2012</span></td>
</tr>
<tr>
<th scope="row">1.6</th>
<td><span class="sortkey" style="display:none;speak:none">2011-01-10</span><span style="white-space:nowrap">January 10, 2011</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2011-08-19</span><span style="white-space:nowrap">August 19, 2011</span></td>
</tr>
<tr>
<th scope="row">1.7</th>
<td><span class="sortkey" style="display:none;speak:none">2011-07-19</span><span style="white-space:nowrap">July 19, 2011</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2012-02-24</span><span style="white-space:nowrap">February 24, 2012</span></td>
</tr>
<tr>
<th scope="row">2.5 (LTS)</th>
<td><span class="sortkey" style="display:none;speak:none">2012-01-24</span><span style="white-space:nowrap">January 24, 2012</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2014-12-31</span><span style="white-space:nowrap">December 31, 2014</span></td>
</tr>
<tr>
<th scope="row">3.0</th>
<td><span class="sortkey" style="display:none;speak:none">2012-09-27</span><span style="white-space:nowrap">September 27, 2012</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2013-04-01</span><span style="white-space:nowrap">April 2013</span></td>
</tr>
<tr>
<th scope="row">3.1</th>
<td><span class="sortkey" style="display:none;speak:none">2013-04-24</span><span style="white-space:nowrap">April 24, 2013</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2013-10-01</span><span style="white-space:nowrap">October 2013</span></td>
</tr>
<tr>
<th scope="row">3.2</th>
<td><span class="sortkey" style="display:none;speak:none">2013-11-06</span><span style="white-space:nowrap">November 6, 2013</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2014-10-01</span><span style="white-space:nowrap">October 2014</span></td>
</tr>
<tr>
<th scope="row">3.3</th>
<td><span class="sortkey" style="display:none;speak:none">2014-04-30</span><span style="white-space:nowrap">April 30, 2014</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2015-02-01</span><span style="white-space:nowrap">February 2015</span></td>
</tr>
<tr>
<th scope="row">3.4</th>
<td><span class="sortkey" style="display:none;speak:none">2015-02-24</span><span style="white-space:nowrap">February 24, 2015</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2016-03-01</span><span style="white-space:nowrap">March 2016</span></td>
</tr>
<tr>
<th scope="row">3.5</th>
<td><span class="sortkey" style="display:none;speak:none">2016-03-21</span><span style="white-space:nowrap">March 21, 2016</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2016-07-01</span><span style="white-space:nowrap">July 2016</span></td>
</tr>
<tr>
<th scope="row">3.6</th>
<td><span class="sortkey" style="display:none;speak:none">2016-07-12</span><span style="white-space:nowrap">July 12, 2016</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2017-04-01</span><span style="white-space:nowrap">April 2017</span></td>
</tr>
<tr>
<th scope="row">3.7</th>
<td><span class="sortkey" style="display:none;speak:none">2017-04-25</span><span style="white-space:nowrap">April 25, 2017</span></td>
<td style="background:salmon;"><span class="sortkey" style="display:none;speak:none">2017-09-01</span><span style="white-space:nowrap">September 2017</span></td>
</tr>
<tr>
<th scope="row">3.8</th>
<td><span class="sortkey" style="display:none;speak:none">2017-09-19</span><span style="white-space:nowrap">September 19, 2017</span></td>
<td style="background:#90EE90;"></td>
</tr>
<tr>
<th scope="row">3.9 (LTS)</th>
<td><span class="sortkey" style="display:none;speak:none">2018-01-01</span><span style="white-space:nowrap">2018</span></td>
<td style="background:#87CEEB;"></td>
</tr>
<tr>
<th scope="row">4.0</th>
<td><span class="sortkey" style="display:none;speak:none">2018-01-01</span><span style="white-space:nowrap">2018</span></td>
<td style="background:#87CEEB;"></td>
</tr>
</table>


*********************

## Technical architecture of joomla

Joomla is written in PHP, it uses Object Oriented programming techniques and MVC design patterns, it uses
MySQL to store data (MS SQL version 2.5 onwards, and PostgreSQL version 3.0 onwards). Various features
which make Joomla a hit include page caching, blogs, polls, language internationalization support and RSS
feeds.

![joomla](https://docs.joomla.org/images/thumb/3/35/JoomlaArchitecture0.png/800px-JoomlaArchitecture0.png)

![Joomla is a Model-View-Controller](https://i.stack.imgur.com/PBcaV.png)

Joomla makes use of MVC design pattern. When Joomla processes a request, it analyses the URL to
determine which component will be responsible for processing the request, and hand over the control to that
component. Then as per MVC, that component pass control to the controller. 

* The controller analyses the request and determines which model and view will be used to return the results back to the user. The model encapsulates the data used by component. The data can come from a database, it can be a Joomla
database or any external database or can come via web service API running on external server. 

* The model is responsible for updating database and isolating the view and controller from the functioning about how
data is amended or modeled. The view is responsible for generating the output which is then sent over to the
browser by the component. Once the view has produced the output, the control is taken over by Joomla
framework which then loads and executes the template. The template combines the output from various
components and active modules and deliver it as a single page on browser.

Apart from this, Joomla splits the traditional MVC view into view and layout. The view pulls
the data from the model and then sends the data to layout which can then formats the data and present it to
the user.The split mechanism allows the template to be overridden in the template. These overridden layouts
are bundled with the template and give complete control to designer over all the output and any installed
third party extensions.


### What makes up Joomla?

*  Core – The core of Joomla consists of php files which provides platform functionality required to
make general work. There are also some configuration files and library files for e.g. Some of the files
may call Javascript library etc. And lastly, there is a database which contains vital information about
configuration files in Joomla and also the content which you put into Joomla.

*  Extensions – There are five types of extensions for Joomla viz.

  *  Components – Components are the largest and most complex extensions of them all, they
sometime referred to as mini applications. Mostly, they have 2 parts; a site part and an administrator
part. Each time a Joomla page is loaded, one component is called to render the main page body.

  *  Modules – These are light weight and flexible extensions used for page rendering. These are
commonly called as “boxes” as these are arranged around a component

  *  Plugins – More advanced extensions and are actually event handlers. In any execution scenario,
whether it is core, a module or a component, an event is triggered. When this happens, the plugins
registered with the application are executed. For example, a plugin can be used to filter out a bad
word.

  *  Templates – Templates are basically how your Joomla website looks. It is in essence the design of
your Joomla powered website. It can be used to change the look and feel of your website.
Components and modules are generally shown under the templates. Templates provide maximum
flexibility in regards to how you style your website.

  * Languages – It is most basic extension. It can be packaged either as a core package or an
extension package. These files contains key/value pairs, these pairs provide the translation of static
text strings within the Joomla Source code. Language packs also include an XML meta file which describes the language

### Joomla project structure

<p>Joomla! CMS templates use a structure of directories and files but they can vary from template to template</p>
<ul>
<li><b>Site</b> templates (templates that change what your website looks like) can be found in the <code>/templates</code> directory. For example, if your template is called "mytemplate", then it would be placed in the folder:</li>
</ul>
<dl>
<dd><code>&lt;path-to-Joomla!&gt;/templates/mytemplate</code></dd>
</dl>
<ul>
<li><b>Administrator</b> templates (templates that change what the administrator section of the site looks like) can be found in the <code>/administrator/templates</code> directory. For example, if your administrator template is called "myadmintemplate", then it would be placed in the folder:</li>
</ul>
<dl>
<dd><code>&lt;path-to-Joomla!&gt;/administrator/templates/myadmintemplate</code></dd>
</dl>


<p>A typical template for Joomla! will include the following directories:</p>
<ul>
<li>css - contains all the .css files</li>
<li>html - contains template override files for core output and module chrome</li>
<li>images - contains all images used by the template</li>
<li>language - contains additional language files used by the template</li>
</ul>
<p>Depending on the complexity and design of the template is may also contain:</p>
<ul>
<li>javascript - contains supporting JavaScript used by the template for added functionality</li>
</ul>
<h4><span class="mw-headline" id="Example_structure_with_files">Example structure with files</span></h4>
<p>Typical path of a template is <code>&lt;root&gt;/public_html/domain-name/template/&lt;name of your template&gt;</code> which will contain the following directories and files based on your template.</p>
<pre>
/css
/html
/images
/javascript
/language
component.php
error.php
favicon.ico
index.php
templateDetails.xml
template_preview.png
template_thumbnail.png 
</pre>

*************************

## Webservices


*****************

Finally.. in brief.. all these layers below...

<br>

![internet stack](https://upload.wikimedia.org/wikipedia/commons/3/39/Internet_Key_Layers.png)


<br>

have made this complex world..

<br>

![ineternet](https://upload.wikimedia.org/wikipedia/commons/3/3f/Internet_map_1024_-_transparent%2C_inverted.png)

<br>

its worth spending some time on below table.. 


<table class="vertical-navbox nowraplinks hlist" style="float:right;clear:right;width:22.0em;margin:0 0 1.0em 1.0em;background:#f9f9f9;border:1px solid #aaa;padding:0.2em;border-spacing:0.4em 0;text-align:center;line-height:1.4em;font-size:88%">
<tr>
<th style="padding:0.2em 0.4em 0.2em;font-size:145%;line-height:1.2em"><a href="https://en.wikipedia.org/wiki/History_of_computing" title="History of computing">History of computing</a></th>
</tr>
<tr>
<th style="padding:0.1em"><a href="https://en.wikipedia.org/wiki/Computer_hardware" title="Computer hardware">Hardware</a></th>
</tr>
<tr>
<td style="padding:0 0.1em 0.4em">
<ul>
<li><a href="https://en.wikipedia.org/wiki/History_of_computing_hardware" title="History of computing hardware">Hardware before 1960</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_computing_hardware_(1960s%E2%80%93present)" title="History of computing hardware (1960s–present)">Hardware 1960s to present</a></li>
</ul>
</td>
</tr>
<tr>
<th style="padding:0.1em"><a href="https://en.wikipedia.org/wiki/Software" title="Software">Software</a></th>
</tr>
<tr>
<td style="padding:0 0.1em 0.4em">
<ul>
<li><a href="https://en.wikipedia.org/wiki/History_of_software" title="History of software">Software</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_Unix" title="History of Unix">Unix</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_free_and_open-source_software" title="History of free and open-source software">Free software and open-source software</a></li>
</ul>
</td>
</tr>
<tr>
<th style="padding:0.1em"><a href="https://en.wikipedia.org/wiki/Computer_science" title="Computer science">Computer science</a></th>
</tr>
<tr>
<td style="padding:0 0.1em 0.4em">
<ul>
<li><a href="https://en.wikipedia.org/wiki/History_of_artificial_intelligence" title="History of artificial intelligence">Artificial intelligence</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_compiler_construction" title="History of compiler construction">Compiler construction</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_computer_science" title="History of computer science">Computer science</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_operating_systems" title="History of operating systems">Operating systems</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_programming_languages" title="History of programming languages">Programming languages</a></li>
<li><a href="https://en.wikipedia.org/wiki/List_of_pioneers_in_computer_science" title="List of pioneers in computer science">Prominent pioneers</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_software_engineering" title="History of software engineering">Software engineering</a></li>
</ul>
</td>
</tr>
<tr>
<th style="padding:0.1em">Modern concepts</th>
</tr>
<tr>
<td style="padding:0 0.1em 0.4em">
<ul>
<li><a href="https://en.wikipedia.org/wiki/History_of_general-purpose_CPUs" title="History of general-purpose CPUs">General-purpose CPUs</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_the_graphical_user_interface" title="History of the graphical user interface">Graphical user interface</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_the_Internet" title="History of the Internet">Internet</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_laptops" title="History of laptops">Laptops</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_personal_computers" title="History of personal computers">Personal computers</a></li>
<li><a href="https://en.wikipedia.org/wiki/History_of_video_games" title="History of video games">Video games</a></li>
<li><a class="mw-selflink selflink">World Wide Web</a></li>
</ul>
</td>
</tr>
<tr>
<th style="padding:0.1em"><a href="https://en.wikipedia.org/wiki/Timeline_of_computing" title="Timeline of computing">Timeline of computing</a></th>
</tr>
<tr>
<td style="padding:0 0.1em 0.4em">
<ul>
<li><a href="https://en.wikipedia.org/wiki/Timeline_of_computing_hardware_before_1950" title="Timeline of computing hardware before 1950">before 1950</a></li>
<li><a href="https://en.wikipedia.org/wiki/Timeline_of_computing_1950%E2%80%9379" title="Timeline of computing 1950–79">1950–1979</a></li>
<li><a href="https://en.wikipedia.org/wiki/Timeline_of_computing_1980%E2%80%9389" title="Timeline of computing 1980–89">1980–1989</a></li>
<li><a href="https://en.wikipedia.org/wiki/Timeline_of_computing_1990%E2%80%9399" title="Timeline of computing 1990–99">1990–1999</a></li>
<li><a href="https://en.wikipedia.org/wiki/Timeline_of_computing_2000%E2%80%9309" title="Timeline of computing 2000–09">2000–2009</a></li>
<li><a href="https://en.wikipedia.org/wiki/Timeline_of_computing_2010%E2%80%9319" title="Timeline of computing 2010–19">2010–2019</a></li>
<li><a href="https://en.wikipedia.org/wiki/Category:Computing_timelines" title="Category:Computing timelines"><i>more timelines</i> ...</a></li>
</ul>
</td>
</tr>
<tr>
<td style="padding:0.3em 0.4em 0.3em;font-weight:bold">
</td>
</tr>
<tr>
<td style="text-align:right;font-size:115%">
<div class="plainlinks hlist navbar mini">
</div>
</td>
</tr>
</table>


and this is never gonna stop... with time.

<br>

![A rotating globe in GIF](https://upload.wikimedia.org/wikipedia/commons/2/2c/Rotating_earth_%28large%29.gif)

<br>


*********************
*************************
*******************************
