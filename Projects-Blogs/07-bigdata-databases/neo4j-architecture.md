<div id="book-search-results">
    <div class="search-noresults">
    
                                <section class="normal markdown-section">
                                
                                <h1 id="neo4j---a-graph-database">Neo4j - A Graph Database</h1>
<p><a href="http://neo4j.com" target="_blank"><img src="images/neo4j-logo.png" alt="Neo4j logo"></a></p>
<p><strong><a href="https://github.com/kangliangc" target="_blank">Kangliang Chen</a>, <a href="https://github.com/manojpkr" target="_blank">Manoj Krishnaraj</a>, and <a href="https://github.com/tompeeters368" target="_blank">Tom Peeters</a></strong></p>
<p><em><a href="http://tudelft.nl" target="_blank">Delft University of Technology</a></em></p>
<p><strong>Abstract</strong></p>
<p>This chapter gives a brief overview of Neo4j&apos;s architecture by focusing on three fundamental concepts: stakeholders, viewpoints, and perspectives as defined in the book by Rozanski and Woods[1]. The stakeholder analysis section details the types of influencer&apos;s who have an impact the Neo4j&apos;s architecture. The context view explains the interactions between Neo4j and its environment; the development view and deployment views describe the software development process and the runtime environment respectively. Following this, the evolution, variability, performance &amp; scaling perspectives of Neo4j are analyzed. Through these multiple viewpoints and perspectives, the software architecture of Neo4j can be easily discerned.</p>
<h2 id="table-of-contents">Table of Contents</h2>
<ul>
<li><a href="#user-content-introduction">Introduction</a></li>
<li><a href="#user-content-stakeholder-analysis">Stakeholder analysis</a></li>
<li><a href="#user-content-context-view">Context View</a></li>
<li><a href="#user-content-development-view">Development View</a></li>
<li><a href="#user-content-deployment-view">Deployment View</a></li>
<li><a href="#user-content-evolution-perspective">Evolution Perspective</a></li>
<li><a href="#user-content-variability-perspective">Variability Perspective</a></li>
<li><a href="#user-content-performance-and-scalability-perspective">Performance and Scalability Perspective</a></li>
<li><a href="#user-content-conclusion">Conclusion</a></li>
<li><a href="#user-content-bibliography">Bibliography</a></li>
</ul>
<p><div name="introduction"></div></p>
<h1 id="introduction">Introduction</h1>
<p>In the early 2000s the scalability of relational databases hit a ceiling, further increases in performance became difficult. These performance problems led to the conceptualization of graph database by its creator, Emil Eifrem, on an airplane flight. As in a graph structure, graph databases use nodes and edges to represent and store data. Semantic queries can be easily performed as the data stored in the nodes are interconnected with related nodes via edges. Neo4j is based on the above principles of a graph database. Neo4j is named after the Latin word for new (neo) and is partly inspired by the character, <em>Neo</em>, in the movie <em>Matrix</em>. The first version of graph database was deployed in 2003 and its source was made public in 2007. The important milestones in Neo4j&apos;s history are depicted in <a href="#figure-history">Figure 1</a>.</p>
<p><img src="images/history.png" alt="Timeline of important events in Neo4j&apos;s history"></p>
<p><div id="figure-history"></div>
    Figure 1: Timeline of important events in Neo4j&apos;s history</p>
<p>Neo4j is an open source, NoSQL graph management system written using Java and Scala. <a href="https://neo.com" target="_blank">Neo Technologies</a> sponsors and oversees the development of Neo4j and has a huge influence on its development roadmap. Neo4j is one of the very few ACID compliance NoSQL databases as it uses a proprietary, labeled property graph data model to represent and store data both in memory and at the storage level. </p>
<p>Some use cases for Neo4j include fraud detection, analytics, social networks, recommendations, scientific research, and routing. Since being made open source in 2007, the popularity of Neo4j has increased steadily and has been downloaded more than a million times. Well written guides, video tutorials, and online documentation makes it easy for new developers to adopt Neo4j. The following sections in this chapter will give insights into Neo4j&apos;s architecture and will help in the transition from a user to a contributor.</p>
<p><div name="stakeholder-analysis"></div></p>
<h1 id="stakeholder-analysis">Stakeholder Analysis</h1>
<p>&quot;A <em>stakeholder</em> is a person, group, or entity with an interest in or concerns about the realization of the software architecture of a system.[1]&quot; This section indentifies the important stakeholders who have a profound impact on the development of Neo4j followed by an analysis of their associated levels of power and interest.</p>
<p>The main stakeholder is <a href="http://neo.com" target="_blank">Neo Technology, Inc.</a> The organization and its employees exclusively fulfill the roles of four of the eleven classes of stakeholders defined by Rozanski and Woods[1]:- <strong>Assessors, Acquirers, Communicators, and Maintainers.</strong> The most important decisions including architectural design, roadmap, releases are authoritatively taken by <a href="http://neo4j.com/staff/" target="_blank">the leadership team</a> of Neo Technology, Inc. spearheaded by its CEO, <a href="https://twitter.com/emileifrem" target="_blank">Emil Eifrem</a>. The other stakeholders applicable to Neo4j are listed in <a href="#t1">Table 1</a> and <a href="#figure-stakeholder">Figure 2</a></p>
<table>
<thead>
<tr>
<th>Stakeholder</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Developers and Testers</strong></td>
<td>Most of the developers and testers are the employees of Neo4j. Employees of major customers including Google, ThoughtWorks, GraphAware are among the top contributors and focus on contributing to specific features to fulfill their requirements. The individual users are more adept at raising concerns and fixing minor bugs.</td>
</tr>
<tr>
<td><strong>Suppliers</strong></td>
<td>Though Neo4j supplies the software packages for deployment as downloads, other suppliers provide the whole infrastructure as a service. GrapheneDB specializes in the delivery of managed deployments of Neo4j suitable for most end users. IaaS providers like Heroku, Microsoft Azure supply solutions tailored to meet large scale deployments of Neo4j</td>
</tr>
<tr>
<td><strong>OEM Partners</strong></td>
<td>OEM partners specialize in design, optimization and delivery of both the hardware and software together. The solutions provided by the OEM Partners offer the best performance.</td>
</tr>
<tr>
<td><strong>Support</strong></td>
<td>Neo Technology&apos;s <a href="https://support.neo4j.com/access/" target="_blank">customer support portal</a> provides support for licensed customers. Free support is extended to all via <a href="http://stackoverflow.com/questions/tagged/neo4j" target="_blank">Stackoverflow</a> and <a href="https://groups.google.com/forum/#!forum/neo4j" target="_blank">Google group</a></td>
</tr>
<tr>
<td><strong>Users</strong></td>
<td>The users are anyone who uses the graph functionality of Neo4j. The broad spectrum of users includes individual software developers, students, educational institutions, government organizations, and enterprises including Linkedin, Walmart, eBay, and Cisco.</td>
</tr>
</tbody>
</table>
<pre><code>Table 1: Other stakeholders of Neo4j.
</code></pre><p><img src="images/stakeholder.png" alt="Stakeholders for Neo4j"></p>
<p><div id="figure-stakeholder"></div>
    Figure 2: Stakeholders for Neo4j</p>
<p>The power interest graph depicted in <a href="#figure-power-interest">Figure 3</a> gives a visualization of the measure of the power that a stakeholder wields in the system compared to their interest. The bottom-left quadrant has the least power and interest where as the top-right quadrant has the most. The remaining quadrant on top-left and bottom-right bias towards more power and interest respectively.</p>
<p>As the major stakeholder, Neo Technology, Inc. has the most power and interest. Though the OEM Partners and the Suppliers have slightly lesser interest and power, they are still placed in top-right quadrant along with Neo4j. The enterprise customers are vital for the success of Neo4j and have high power with relatively low interest and are placed in the top-left quadrant.</p>
<p>The end users of the system and DevOp specialists have considerably low power and interest and are placed in the bottom-left quadrant. The bottom-right quadrant consists of occasional contributors from the community, regular contributors with relatively more power than the occasional contributors and the competitors. Though the competitors wield no power, their interest is very high as they do regular market and competitor analysis to keep in line with Neo4j&apos;s new features.</p>
<p><img src="images/power-interest.png" alt="Power/Interest grid for Neo4j"></p>
<p><div id="figure-power-interest"></div>
    Figure 3: Power/Interest grid for Neo4j</p>
<p><div name="context-view"></div></p>
<h1 id="context-view">Context View</h1>
<p>The context view describes the relationships, dependencies, and interactions between the system and its environment. To this end, this section will determine the scope of Neo4j, analyze the external entities and services that interact with it and finally visualize the relationships uncovered.</p>
<p><div name="system-scope"></div></p>
<h2 id="system-scope">System Scope</h2>
<p>Databases are used by virtually every company to securely store information in a scalable manner. As databases are set up entirely by the users according to their own needs a database must be able to fulfil many different functions.<br>In order to be competitive to widely-used existing databases, such as MySQL, Neo4j must be able to meet their standards. However, Neo4j must also provide something that other databases do not. Neo4j does this by utilizing its graph database structure in order to model relationships and store inconsistent data types in far more effective manners.<br>Thus, the scope of Neo4j is to provide unique capabilities and performance in regards to relationship modelling and inconsistent data type handling, as well as providing all functionalities already present in existing databases.</p>
<p><div name="external-entities-and-interfaces"></div></p>
<h2 id="external-entities-and-interfaces">External entities and interfaces</h2>
<p>Neo4j is a fast growing database software with a dedicated company, Neo4j Technologies, sponsoring its development. As can only be expected, there are many external libraries and systems in use to assist in the development and a great deal of interest from third parties. Additionally, Neo4j has many challenges it must live up to as it needs to support a multitude of operating systems and greatly varying requirements. Below, we detail these relationships and visualize them in <a href="#figure-context-view">Figure 4</a>.</p>
<ul>
<li><p>Written in Java and Scala using Eclipse and IntelliJ</p>
</li>
<li><p>Built using Maven and continuous delivery using TeamCity</p>
</li>
<li><p>GitHub is the platform used for hosting and maintaining the source code as well as the tracking of issues</p>
</li>
<li><p>Supports distributions for Windows, Linux &amp; OS X</p>
</li>
<li><p>Technical help for Neo4j use is supplied on StackOverflow, but developers can also be reached on Slack or even Twitter</p>
</li>
<li><p>Neo4j has support for drivers in various programming languages including Java, JavaScript, Ruby, Python and .NET</p>
</li>
<li><p>Dependence on libraries such as JUnit, Mockito, Jetty and Guava, AngularJS, Grunt, Bower, D3.js</p>
</li>
<li><p>Competes with MongoDB, OrientDB, Titan, Oracle and more</p>
</li>
<li><p>Dual licences- commercial license for enterprises and open sourced with AGPL3</p>
</li>
<li><p>Used by small, and large organizations including Cisco, Walmart, National Geographic and more.</p>
</li>
<li><p>Partnered with providers like Heroku, Microsoft Azure, GrapheneDB, ActiveState to provide customized solutions</p>
</li>
</ul>
<p><img src="images/context-view.png" alt="Visualization of Neo4j&apos;s Context View"></p>
<p><div id="figure-context-view"></div>
    Figure 4: Visualization of Neo4j&apos;s Context View</p>
<p><div name="development-view"></div></p>
<h1 id="development-view">Development View</h1>
<p>The development view of a system describes the architecture that supports the software development process. The following section address the concerns of a developer like module organization, common processes, standardization of design and testing, and codeline organization. Finally the technical debt of Neo4j is discussed. </p>
<p><div name="dev-mod"></div></p>
<h2 id="module-organization">Module organization</h2>
<p>The module structure model deals with the organization of system&apos;s source code in terms of modules[1]. The components of the two distributions of Neo4j- community, and enterprise are organized in distict folders. Logically, the enterprise edition encapsulates all the modules in community edition in addtion to a few extra components. This section focusses on structure and organization of the code for community edition of Neo4j in three abstract layers as shown in <a href="#figure-module">Figure 5</a>.</p>
<p>The different components of Neo4j community edition can be organized  three logical layers as seen in <a href="#figure-module">Figure 5</a> in distinct layers</p>
<p><img src="images/module.png" alt="Module organization of community edition"></p>
<p><div name="figure-module"></div>
    Figure 5: Module organization of community edition</p>
<ol>
<li><strong>Access layer</strong> - Provides external interfaces to the database system including cypher query language, bolt protocol, shell and graphical visualization.</li>
<li><strong>Intermediate layer</strong> - core functionalities of the graph system including server APIs, graph engine, graphing algorithms, data collector, lucene index.</li>
<li><strong>Core layer</strong> - made of internal components that are not accessable outside the system. Kernel forms the core of the Neo4j platform priving access to storage and memeory. This layer consists of components like io, csv, function primitives, and unsafe memory access.</li>
</ol>
<p><div name="dev-common"></div></p>
<h2 id="common-processing">Common Processing</h2>
<p>Neo4j is highly modulazired with minimal code duplication. Some common modules that reduce the code duplication include <code>csv</code>, <code>io</code>, <code>collections</code>, and finally <code>common</code>. The <code>common</code> foler contains most of the reused code and greatly helps in code maintainance.</p>
<p><div name="dev-design"></div></p>
<h2 id="standardization-of-design">Standardization of design</h2>
<p>Being an opensource project, Neo4j has a set of strict guidelines for making contributions.</p>
<ul>
<li>The contributor must sign <a href="http://neo4j.com/developer/cla/" target="_blank">CLA</a>.</li>
<li>Use Eclipse or IntelliJ for development</li>
<li>Standardized templates are available for raising issues in GitHub.</li>
<li>The code should strictly adhere to style checks defined and available for Eclispe or IntelliJ IDEs. </li>
<li>The commits must be squashed down and rebased without any merges.</li>
<li>Documentation should be updated for any code changes.</li>
</ul>
<p><div name="dev-test"></div></p>
<h2 id="standardization-of-testing">Standardization of testing</h2>
<p>The maven build process automatically triggers and executes all tests defined in Neo4j&apos;s source code. Code contributions are allowed to be merged only if the tests succeed. Tests are written using Junit and mockito. Continuous integration is achieved by using TeamCity. Following guidelines must be adhered for a Pull request to be successfully merged:</p>
<ul>
<li>All tests must succeed.</li>
<li>Code coverage computed by cobertura is within acceptable limit.</li>
<li>TeamCity integration tests succeed and no issues are raised by CI process.</li>
</ul>
<p><div name="dev-code"></div></p>
<h2 id="codeline-organization">Codeline Organization</h2>
<p>Codeline model defines the overall structure of the codeline and ensures that order is maintained in the organization of the system&apos;s code[1]. The source code of both the editions are maintained in the same github repository. In <a href="#figure-folder-structure">Figure 6</a>, the top level folders are displayed in swim lanes along with their components in respective lanes.</p>
<p>The important folders at the root of the Neo4j repository are <code>community</code>, <code>enterprise</code>, <code>manual</code>, <code>packaging</code>, and <code>tools</code>. <code>manual</code> contains documentation of Neo4j in AsciiDoc format. It can also extract documentation from source code. <code>packaging</code> contains the various utilities for packaging and distribution of the Neo4j releases for different operating systems. Each component inside the community or enterprise folder has a maven <code>pom.xml</code> file in addition to <code>src</code> folder consisting of Java or Scala source code in <code>main</code>, along with <code>tests</code>, and <code>docs</code>.</p>
<p><img src="images/folder-structure.png" alt="Swimlane view of important directories of Neo4j"></p>
<p><div id="figure-folder-structure"></div>
    Figure 6: Swimlane view of important directories of Neo4j</p>
<p>The main components of the Neo4j distribution are listed in table 2.</p>
<table>
<thead>
<tr>
<th>Directory</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td> cypher</td>
<td>Cypher execution engine to support cypher query language</td>
</tr>
<tr>
<td> graph-matching</td>
<td>Graph pattern matching APIs</td>
</tr>
<tr>
<td> graphviz</td>
<td>Visualization of graph data.</td>
</tr>
<tr>
<td> kernel</td>
<td>Core of Neo4j that contains the storage system, embeded API, traversal API, batch processing, configuration, locking and other utilities. </td>
</tr>
<tr>
<td> shell</td>
<td>Provides a command line interface to Neo4j</td>
</tr>
<tr>
<td> backup</td>
<td>Create backup of Neo4j database over the network </td>
</tr>
<tr>
<td> ha</td>
<td>Enables fault-tolerant database architecture and supports replicas as slaves.</td>
</tr>
<tr>
<td> metrics</td>
<td>Modules to expose and report Neo4j metrics </td>
</tr>
</tbody>
</table>
<pre><code>Table 2. Important components of the Neo4j
</code></pre><p><div name="technical-debt"></div></p>
<h2 id="technical-debt">Technical Debt</h2>
<p>Technical debt describes the occurrence of using quick and cheap methods of fixing bugs or implementing features, methods which are typically not thought through well. In essence, the problem with performing such actions lies in the manner in which they make future work more difficult. This is because this manner of work typically does not follow the existing architecture or system design, making it more difficult to oversee the functionality of the system as a whole and create future changes.</p>
<p>Analysis of Neo4j&apos;s technical debt yields very good metrics; only 0.5% of classes have flaws in them. Interestingly, the two classes with the highest cumulative class flaws are both test classes, namely <code>PageCacheTest</code> and <code>NeoStoresTest</code>. The largest package in Neo4j kernel, <code>impl</code> package has likely gotten too convoluted over time and many problems occur within it.</p>
<p>Technical debt is typically differentiated using &apos;Reckless&apos; vs &apos;Prudent&apos; and &apos;Deliberate&apos; vs &apos;Inadvertent&apos;, forming a total of 4 quadrants together. Neo4j contains relatively few flaws, leading us to categorize Neo4j as &apos;Prudent&apos;. Additionally, the area that is most flawed appears to be the a part of the core functionality. This is likely a result of many years of development despite best attempts to avoid it, leading us to also categorize Neo4j as &apos;Inadvertent&apos;.</p>
<p><img src="images/tech-debt.png" alt="Technical debt"></p>
<p><div id="figure-tech-debt"></div>
    Figure 7: Technical debt quadrant</p>
<p><div name="deployment-view"></div></p>
<h1 id="deployment-view">Deployment View</h1>
<p>Database systems are a thing which every modern company requires. This makes it all the more important that database software is simple to deploy and does not impose too many constraints on its users. Neo4j works towards this from the very beginning by utilizing Java and Scala, which can run on any Operating System, allowing users to choose the Operating System which they are most comfortable working with. Additionally, the hardware requirements are very lenient, being able to work with as little as 2 GB of RAM and 10 GB of disk space. In this section, we will look further, however, and analyze third-party software requirements as well as network requirements which Neo4j needs to function.</p>
<p><div name="third-party-software-constraints"></div></p>
<h3 id="third-party-software-constraints">Third-Party Software Constraints</h3>
<p>The installation of Neo4j requires no third party software other than Java runtime 7 or 8 (preferred). However, there are several third-party programs which Neo4j natively supports and that a user may want to install. Below, these programs are highlighted.</p>
<ul>
<li>It is recommended to install software that can visualize the graph database. Neo4j recommends the use of commercial product <a href="http://linkurio.us" target="_blank">Linkurious</a>. However, open-source software <a href="https://gephi.org/" target="_blank">Gephi</a> is frequently used for this as well.</li>
<li>Though it is possible to interface to a Neo4j server using the Neo4j Shell, the recommended method is to use an internet browser such as <a href="https://www.google.com/chrome/" target="_blank">Google Chrome</a>, which allows it to use the D3.js library to visualize data to the user.</li>
<li>Neo4j supports the use of <a href="https://www.docker.com" target="_blank">Docker</a>, a program that can wrap another piece of software in a complete filesystem. Using Docker it becomes simpler to get Neo4j servers running on multiple systems, as it can store the image of the software and install it on another computer with no further hassle. The software on both systems will be identical.</li>
</ul>
<p><div name="network-requirements"></div></p>
<h3 id="network-requirements">Network Requirements</h3>
<p>Neo4j itself uses native messaging and does not have any specific requirements other than interfacing with it using Neo4j Shell or an internet browser. However, the High Availability module, which is responsible for database replication in a master-slave configuration, does impose certain network capacity requirements. As this module is responsible for ensuring identical data across several Neo4j servers, this synchronization can put strain on a network. However, Neo4j has numerous settings to manage the functionality of the High Availability module. For example, the <code>ha.pull_interval</code> setting determines how frequently slaves pull updates from the master. Because this module can be fully configured as per the needs of the user this module has no exact network requirements, but should be taken into consideration when designing and running your database.</p>
<p><div name="evolution-perspective"></div></p>
<h1 id="evolution-perspective">Evolution Perspective</h1>
<p>In order to study the evolution of Neo4j&apos;s configuration and variability[1], we analyzed changelogs and release notes available at <a href="https://github.com/neo4j/neo4j/wiki/Changelog" target="_blank">Neo4j&apos;s GitHub wiki</a>. Neo4j&apos;s evolution history in regards to configuration and variability has been fairly minimal, with the only major changes actually being in recent history. The following section details the changes to configurations in the most recent releases of <code>2.2</code> and <code>2.3</code>, and <code>3.0</code>. For the purpose of keeping the lists clean and concise, bug fixes related to settings are not included.</p>
<p><div name="evolution-in-version-2.2"></div></p>
<h3 id="evolution-in-version-22">Evolution in version 2.2</h3>
<ul>
<li>Query log file rotation was added using the <code>dbms.querylog.rotation.threshold</code> option (this is the option mentioned earlier in the feature identification).</li>
<li><code>dbms.querylog.filename</code> was changed to specify a filename rather than a directory, as would be expected from the name. Additionally, the default value was changed to <code>null</code>, meaning the query logger is disabled by default.</li>
<li><code>logical_log_rotation_threshold</code> default value was changed from 1MB to 250MB.</li>
<li><code>mapped_memory_total_size</code> was renamed to <code>dbms.pagecache.memory</code>.</li>
</ul>
<p><div name="evolution-in-version-2.3"></div></p>
<h3 id="evolution-in-version-23">Evolution in version 2.3</h3>
<ul>
<li>The default setting of <code>dbms.pagecache.memory</code> was changed from 75% to 50% of free system memory</li>
<li>As a result of the Object cache being removed the following settings were removed: <code>cache_type</code>, <code>node_cache_size</code>, <code>relationship_cache_size</code>, <code>node_cache_array_fraction</code>, <code>relationship_cache_array_fraction</code>, <code>cache.memory_ratio</code>, <code>high_performance_cache_min_log_interval</code></li>
</ul>
<p><div name="evolution-in-version-3.0"></div></p>
<h3 id="evolution-in-version-30">Evolution in version 3.0</h3>
<p>In the latest release, version <code>3.0.0-M04</code>, a change was made to the way in which the configuration was loaded. The old functionality had two configuration files, <code>neo4j.properties</code>, and <code>neo4j-server.properties</code>. However, as the difference between these was sometimes vague, as well as the two separate files being rather clumsy, it was merged into the singular <code>neo4j.conf</code> that was mentioned last section.<br>In the process of this update, a number of system properties which Neo4j used to find the configuration file(s) were changed, as well as the developers taking the liberty to remove various deprecated configuration settings from older versions (primarily version <code>2.2</code>).<br>Furthermore, the following changes occurred:</p>
<ul>
<li>The cypher pre-parsing query planner option <code>greedy</code> was removed</li>
<li>The cypher pre-parsing update strategy option <code>eager</code> was added.</li>
<li>The setting <code>org.neo4j.server.database.location</code> was removed.</li>
<li>The setting <code>dbms.active_database</code> was added, more or less a relocation of the former setting.</li>
<li>The setting <code>dbms.directories.data</code> was added, to specify where the database stores its data.</li>
</ul>
<p>To conclude, while there are certainly changes in the configuration options of each Neo4j version, considering the release timeline there is a fairly minimal amount. This can most likely be attributed to a large part that Neo4j&apos;s development focuses on improving performance and adding new features (which do not require many, if any, new settings). There is a fairly small amount of deprecated settings as most modules that have been added over the duration of Neo4j&apos;s development time have not been removed or replaced, which can be attributed to Neo4j having a clear and detailed design architecture which the developers follow closely.</p>
<p><div name="variability-perspective"></div></p>
<h1 id="variability-perspective">Variability Perspective</h1>
<p>The variability of a system is an important characteristic of any system. Through customization of the settings a system can be made easier to work with for users, performance of the system can be increased and unused or unwanted modules can be disabled. In short, by providing a great deal of customization options a product can gain a competitive advantage over similar products.  </p>
<p>Neo4j, being a database system, has a particularly high need for variability. It serves as a framework for users of Neo4j to store all data they deem important and can have many different use cases. For example, a bank requires their database to have features and options to tighten security and confidentiality as much as possible, where as a cloud-service requires fast responses and high availability.  </p>
<p>These demands can be met using variability, which is especially ideal as making all such features compulsory would mean overburdening users that have no need for such advanced features. In this chapter we identify and analyze the work that Neo Technologies has put toward variability based on the work done by Apel et. al in their book <em>Feature-Oriented Software Product Lines</em>[2]. We analyze the ways in which Neo4j can be customized by its users, as well as the way in which these customizations were implemented by the developers.</p>
<p><div name="feature-identification"></div></p>
<h3 id="feature-identification">Feature Identification</h3>
<p>In this section we identify a number of the configuration options (features) available in Neo4j. In total there are roughly a hundred options, ranging from basic settings such as specifying the location of the database directory, to more advanced optimization options such as buffer and cache sizes. Settings are either general settings or module-specific settings. This section gives a number of examples of both general settings and for a specific module, in this case, Cypher was chosen.</p>
<p><div name="general-settings"></div></p>
<h5 id="general-settings">General settings</h5>
<p>A number of the settings available in Neo4j do not belong under any specific module, but are still significant settings which are important to mention. Below a number of these are highlighted.</p>
<ul>
<li><strong>Allow File URLs</strong> - A server setting that determines whether the Cypher API will accept file URLs when loading data using <code>LOAD CSV</code>.</li>
<li><strong>Read Only</strong> - This setting determines whether users are allowed to write new data or update existing data to the Neo4j server or not. This is a useful method for developers to protect their data from users if the users have direct access to the server.</li>
<li><strong>Index Sampling Update Percentage</strong> - Determines the percentage of indexes need to be updated before sampling of an index is triggered.</li>
<li><strong>Internal Store Log Level</strong> - Sets the verbosity level of the log. Can be set to e.g. <code>DEBUG</code>, <code>INFO</code>, <code>NONE</code> and more.</li>
</ul>
<p><div name="cypher-settings"></div></p>
<h5 id="cypher-settings">Cypher settings</h5>
<p>Cypher Query Language (CQL) is Neo4j&apos;s custom made query language, similar in nature to the more well known SQL. There are a number of settings specifying how cypher queries are processed and handled, expanded upon below.</p>
<ul>
<li><strong>Cypher Parser Version</strong> - Sets the language version to use of the Cypher parser. Must be either <code>2.3</code> or <code>default</code>.</li>
<li><strong>Cypher Planner</strong> - Sets the default query planner to use which determines how to execute and optimize the query given to Neo4j. Should be either <code>COST</code> or <code>RULE</code>.</li>
<li><strong>Cypher Min Replan Interval</strong> - Determines the minimum time before Neo4j will start considering to re-plan a query currently in execution. This is typically done because the initial plan was poorly constructed and would take longer than re-planning a more efficient plan.</li>
<li><strong>Query Cache Size</strong> - Determines the maximum number of Cypher query execution plans that the server keeps in cache.</li>
</ul>
<p><div name="feature-relationships"></div></p>
<h2 id="feature-relationships">Feature Relationships</h2>
<p>The majority of features in Neo4j possess no dependency and have no conflicts with each other besides the need to turn their respective module on. For example, for the &apos;Query log threshold&apos; setting to have any impact, &apos;Query logging&apos; itself must be turned on.  </p>
<p>Furthermore, though many settings are mandatory (i.e. the system always uses them), every setting has a default value. Most of the time this default value need not be changed. In fact, in case of the &apos;High Availability&apos; module it is recommended that you do not change anything. As such, despite there being a great deal of settings the amount being requested of the user is very minimal.</p>
<p>Figure 8 displays the relationship between a large number of features present in Neo4j. Unfortunately, there are too many to display all within a single figure.</p>
<p><img src="images/feature-relationship.png" alt="Visualization of the relationship between the features"></p>
<p><div id="figure-feature-relationships"></div>
   <em>Figure 8: Feature relationships in Neo4j based on [3]</em></p>
<p><div name="feature-binding-time-and-variability"></div></p>
<h3 id="feature-binding-time-and-variability-strategy">Feature Binding Time and Variability Strategy</h3>
<p>All Neo4j configuration options have a binding time of startup-time. The reason behind this decision is most likely a result of the manner in which databases are typically used, namely as long-running programs, often being active for days, weeks or even months at a time without pause. During this time there is generally no need to change settings, hence the ability to do so was not considered important.</p>
<p>The strategy for implementing these settings was to use a single configuration file. All settings can be defined in a <code>neo4j.conf</code> file which is located within the base directory of a database. This configuration file is read upon start-up of the Neo4j server and the settings are then stored within the program itself as a global object for quick access by the program. As such, making modifications to this file after start-up will not affect the server until Neo4j has been restarted.  </p>
<p>The configuration file has a simple structure, in which settings are assigned values with simple <code>=</code> statements and comments can be placed using <code>#</code>. For example, below is what a possible configuration file might look like:</p>
<pre><code># Enable shell server so that remote clients can connect via Neo4j shell.
remote_shell_enabled=true
# The network interface IP the shell will listen on (use 0.0.0.0 for all interfaces).
remote_shell_host=127.0.0.1
# The port the shell will listen on, default is 1337.
remote_shell_port=1337
</code></pre><p>By default the properties file is empty, meaning that each setting uses its default value. By giving each setting a default value Neo4j becomes easier to use, as less specific information is requested from newly starting users. The default values that are used for each setting can be found in the Neo4j documentation, which also features a description of each setting and the possible input values (e.g. value ranges/enumerator values).<div name="performance-and-scalability-perspective"></div></p>
<h1 id="performance-and-scalability-perspective">Performance and Scalability Perspective</h1>
<p>The performance and scalability is very crucial to a database. One of the most important characteristic to evaluate the performance of a database is the query time. Due to the tremendous rate of growth of data in the present day, it becomes more difficult for traditional database to provide real-time feedback. Furthermore, the increase in data means that databases should have be highly scalable to fit the needs. The graph database that was created and implemented by Neo4j has achieved that goal in its current situation. However, will Neo4j still meet the performance criteria if the workload increases even further in the future? The following sections focus on further discussion of the performance and scalability of Neo4j. Since these two points are essential to this software, we want to spend some time to analyze it on a number of points.</p>
<p><div name="performance"></div></p>
<h3 id="performance">Performance</h3>
<p>There are two major characteristics of performance:</p>
<ol>
<li>Response time</li>
<li>Throughput</li>
</ol>
<p>The Neo4j is known as high performance when managing a huge amount of different data. Relational database search all of the data looking for anything that meets the search criteria. The larger the set of data, the longer it takes to find matches, because the database has to examine everything in the collection. However, a graph database only examines at nodes that are directly connected to other nodes. If a limit is given on how many steps it is allow to make, it can ignore everything further away for additional performance boosts. </p>
<p><img src="images/nodes.png" alt="Relations Illustration"></p>
<p><div id="figure-nodes"></div>
    Figure 9: Visualization of Neo4j&apos;s node routing</p>
<p>Figure 9 depicts how nodes are connected within Neo4j. Only the blue nodes are searched during a query. Neo4j knows where it is at any time, and has no need to start over from the beginning or backtrack.</p>
<h4 id="response-time">Response time</h4>
<p>This leads to the difference in response time compared to relational databases. Graph databases have a much better performance if the data is not identical. The average response time will be hundreds times faster than the relational database. Conversely, it will be slower if the data is identical. </p>
<h4 id="throughput">Throughput</h4>
<p>The throughput of Neo4j will vary considerable depending on the data type. If the data is unique and the steps limit is set, the performance will be quite similar. However, the performance will be heavily influenced if the numbers of connections between two nodes increases drastically. </p>
<p><div name="scalability"></div></p>
<h3 id="scalability">Scalability</h3>
<p>Scalability can mean different things to different people. Common points are:</p>
<ol>
<li>Redundancy to failure</li>
<li>Managing increasing read load</li>
<li>Managing increasing data size</li>
<li>Managing increasing write load</li>
</ol>
<p><img src="images/cluster.jpg" alt="Cluster Illustration"></p>
<p><div id="figure-cluster"></div>
    Figure 10: Visualization of Neo4j&apos;s Cluster system</p>
<h4 id="redundancy-to-failure">Redundancy to failure</h4>
<p>Neo4j offers a scalability package which includes:</p>
<ul>
<li>Online backups when the cluster is running </li>
<li>Global cluster for data locality</li>
<li>Disaster recovery for data center redundancy</li>
<li>Reporting instances for ad-hoc reporting</li>
</ul>
<p>In a Neo4j cluster, the full graph is replicated to each instance in the cluster. All the data is safe as long as one instance remains available. A single instance of Neo4j can house at most 34 billion nodes, 34 billion relationships, and 68 billion properties, in total.</p>
<h4 id="managing-increasing-read-load">Managing increasing read load</h4>
<p>Read operations can be done locally on each slave. This allows the read capacity to increase linearly with the number of servers. </p>
<h4 id="managing-increasing-data-size">Managing increasing data size</h4>
<p>A graph database can find the neighbors of any node without going through the all relationships. Thus, as the data size increases, the query time will remain a constant. Additionally, if the steps limit is set properly, the query time is likely within a very small range. However, the performance will be influenced depending on whether the data is unique or not.</p>
<h4 id="managing-increasing-write-load">Managing increasing write load</h4>
<p>Neo4j has a single master to coordinate all write operations, and it limits the write throughput of a single machine. However, there are few scenarios dealing with high write load. Furthermore, a queuing solution could be implemented to handle this situation. A steady manageable stream of write operations can be serviced by the cluster.</p>
<p><div name="conclusion"></div></p>
<h1 id="conclusion">Conclusion</h1>
<p>This chapter summarized Neo4j in architectural opinions. The stakeholder analysis was discussed followed by different views and perspectives.  In the stakeholder analysis, who they are and what they do were discussed. After that, there were three views introduced the software in context, development and deployment. At the last, there were three perspectives introduced the software in evolution, variability, performance and scalability. </p>
<p>Companies and organizations after reading this chapter can get more insght to the software. Companies and organizations today not only need to store the large amount data, but need to get an insight from the existing data as well. In order to use the data relationships, companies and organizations need a database to store relationships as well.</p>
<p>Neo4j is a new approach to cope with the increasing data. Also, graphs are the most efficient and natural way to represent relationships. It gives higher efficiency, faster response, easier maintenance and safer operations comparing to the conventional database. </p>
<p><div name="bibliography"></div></p>
<h1 id="bibliography">Bibliography</h1>
<p><strong>[1]</strong> - Rozanski, Nick, and E&#xF3;in Woods. Software systems architecture: working with stakeholders using viewpoints and perspectives. Addison-Wesley, 2012.  </p>
<p><strong>[2]</strong> - Apel, Sven, et al. &quot;Feature-Oriented Software Product Lines.&quot; </p>
<p><strong>[3]</strong> - Th&#xFC;m, Thomas, et al. &quot;FeatureIDE: An extensible framework for feature-oriented software development.&quot; 
Science of Computer Programming 79 (2014): 70-85.</p>
<p><strong>[4]</strong> - Neo Technologies&apos; CEO, Emil Eifrem&apos;s interview <a href="https://twitter.com/emileifrem/status/712327903032188928" target="_blank">https://twitter.com/emileifrem/status/712327903032188928</a></p>

                                
                                </section>
                            
    </div>
