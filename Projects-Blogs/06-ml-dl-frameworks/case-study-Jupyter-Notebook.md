
<p><em>Jupyter notebook, the next generation of IPython, is an open-source web-application that allows the user to create and share documents containing live code, comments, formulas, images and more, all in one place.
The current chapter analyses this project in depth. 
Our team was able to make six pull requests regarding technical debt and bug fixes, which were accepted.
A good overview of the whole project is given by analysing stakeholders and the context view.
Next, various viewpoints and perspectives on the architecture of the project are investigated.
This chapter aims to help people who would like to join the Jupyter community and make contributions, by providing extensive analysis of the project.</em></p>
<h3 id="table-of-contents">Table of Contents</h3>
<ul>
<li><a href="#intro">Introduction</a></li>
<li><a href="#org">Organization</a><ul>
<li><a href="#stake">Stakeholders</a></li>
<li><a href="#cont">Context View</a></li>
</ul>
</li>
<li><a href="#arch">Architecture</a>    <ul>
<li><a href="#dev">Development Viewpoint</a></li>
<li><a href="#fun">Functional Viewpoint</a></li>
</ul>
</li>
<li><a href="#debt">Technical Debt</a></li>
<li><a href="#evo">Evolution Perspective</a></li>
<li><a href="#concl">Conclusion</a></li>
<li><a href="#ref">References</a></li>
</ul>
<div id="intro"></div>

<h2 id="introduction">Introduction</h2>
<p>Jupyter Notebook is a cross-platform open source web application which allows running code, visualising its output (such as plots, images, tables etc.) and writing explanations in natural language, accompanied by equations and all this in one so-called Notebook file. It provides the opportunity to process large amount of data and supports <strong>Ju</strong>lia, <strong>Pyt</strong>hon, <strong>R</strong> (origin of the name <strong>Jupyter</strong>) and many other programming languages. It is intuitive, easy to install and use, which makes it suitable for scientists, programmers and learners. </p>
<p>It is adopted by teachers in universities such as <a href="https://developer.rackspace.com/blog/deploying-jupyterhub-for-education/" target="_blank">UC Berkeley</a> where they use JupyterHub (server, hosting Notebooks where users log in and immediately start coding) in which students do their assignments. Furthermore, Github supports the rendering of Notebook <code>.ipynb</code> files. Entire books have been written with Notebook and published on Github. Multiple online courses on Machine Learning, Computer Science, Python programming, Data Analysis and others can be found in <a href="https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks" target="_blank">this Github repository</a>. </p>
<p>This chapter aims to give users a quick understanding of how Jupyter Notebook is organised, developed and maintained. First, the Stakeholders and Context view are analysed to provide insights into the organisation of the project. Furthermore, detailed analysis of the architecture is presented in order to understand its structure. In addition, technical debt in terms of code, testing and documentation was also found throughout the analysis of the system and is presented in the chapter. This is followed by the evolution of the project explaining how Notebook emerged from IPython and discussing the JupyterLab project which is considered as the future of Notebook. Finally, the chapter concludes with our findings of the project.</p>
<div id="org"></div>

<h2 id="organization">Organization</h2>
<p>This section discusses the parties that are involved in the development, maintenance, testing and building of the system. These stakeholders are then visualised using a context-view diagram.</p>
<div id="stake"></div>

<h3 id="stakeholders">Stakeholders</h3>
<p>A number of different types of stakeholders exist as defined by Rozanski &amp; Woods [<a href="#rw">1</a>] and this section goes through them w.r.t. Jupyter Notebook.</p>
<h4 id="assessors"><strong>Assessors</strong></h4>
<p>As Jupyter Notebook&apos;s team consists of fifteen core developers who oversee the conformance of the (programming &amp; other) standards. They are responsible for handling pull requests and communicate them between each other to decide whether or not to merge. Furthermore, they do the planning of future releases and/or sub-systems of the Notebook. </p>
<h4 id="communicators"><strong>Communicators</strong></h4>
<p>Communicators are people who explain the system and the architecture to other stakeholders via documentation or training materials. A <a href="https://www.slideshare.net/mbussonn/jupyter-a-platform-for-data-science-at-scale" target="_blank">number</a> <a href="https://www.slideshare.net/BigDataColombia/ipython-jupyter" target="_blank">of</a> <a href="https://www.slideshare.net/Plotly/plotcon-nyc-the-architecture-of-jupyter-protocols-for-interactive-data-exploration-and-visualization-across-languages" target="_blank">presentations</a> are available online, prepared and presented by Fernando Perez and Matthias Bussonier. Jupyter Notebook communicators are also all the developers who have written the documentation. They are a small team and all of them update the documentation when necessary. The documentation is useful as well for developers and contributors to the system. </p>
<h4 id="developers"><strong>Developers</strong></h4>
<p>Two major types of Developer stakeholders were identified in Jupyter Notebook: core and contributors.</p>
<ul>
<li><strong>Core</strong>: Core developers work actively to write, fix, test and improve the system. Their main job is to also go through the open pull requests on Github and  ensure that the contribution proposals are well tested and do not interfere with the current system in any way other than to improve it. 
Core developers are @<a href="https://github.com/carreau" target="_blank">carreau</a>, @<a href="https://github.com/takluyver" target="_blank">takluyver</a>, @<a href="https://github.com/jasongrout" target="_blank">jasongrout</a>, @<a href="https://github.com/rgbkrk" target="_blank">rgbkrk</a>, @<a href="https://github.com/minrk" target="_blank">minrk</a> and @<a href="https://github.com/blink1073" target="_blank">blink1073</a>.</li>
<li><strong>Contributors</strong> are important for open source projects as they often solve issues the core team has no time for or implement new features making the product even better. They contribute also by improving documentation, bug fixes and even by writing their own kernel supporting a new programming language. Examples of these contributors are @<a href="https://github.com/vidartf" target="_blank">vidartf</a> and @<a href="https://github.com/yuvipanda" target="_blank">yuvipanda</a>.</li>
</ul>
<div id="maint"></div>

<h4 id="maintainers"><strong>Maintainers</strong></h4>
<p>The <strong>Steering Council</strong> consists of Project Contributors writing substantial code of high quality and quantity for over one year. Working with the BDFL (Benevolent Dictator for Life) Fernando Perez the council ensures the long-term progress and existence of the project. The <a href="http://numfocus.org" target="_blank">NumFOCUS Foundation</a> serves as the projects&apos; fiscal sponsor and acts as a parent legal entity. The NumFOCUS Subcommittee consists of four Council and one external member. </p>
<h4 id="support-staff"><strong>Support Staff</strong></h4>
<p>As per the book [<a href="#rw">1</a>], support staff are the people who provide support to the users. Therefore Jupyter Notebook members taking care of issues in their Github repository could be considered support staff. These users are usually @<a href="https://github.com/minrk" target="_blank">minrk</a> and @<a href="https://github.com/takluyver" target="_blank">takluyver</a>. In case they are not sure about something, they know who to get involved. </p>
<h4 id="testers"><strong>Testers</strong></h4>
<p>Testers are people who test the system to ensure it is suitable to use. Since the Notebook team consists of only fifteen core developers, each of them has to write tests whenever they implement a new feature or improve the current code. All of them can thus be considered testers as well. However, while going through the project a few members were identified who wrote new or updated the old tests frequently: @<a href="https://github.com/jdfreder" target="_blank">jdfreder</a> (no longer active), @<a href="https://github.com/minrk" target="_blank">minrk</a> (core dev),  @<a href="https://github.com/ssanderson" target="_blank">ssanderson</a> (contributor) and others.</p>
<h4 id="users"><strong>Users</strong></h4>
<p>The two biggest categories of users are the following:</p>
<ul>
<li><strong>Scientists:</strong> Jupyter is mainly used by data scientists working with R and Python on daily basis, however, it is not only aimed at them but is generally used by other types of users as well. </li>
<li><strong>Learners</strong> are stakeholders who, for example, use Notebook for study &amp; teaching purposes. </li>
</ul>
<h4 id="sponsors"><strong>Sponsors</strong></h4>
<p>Sponsors are an additional stakeholder class to the main ones, related to the project. It consists of companies and universities that support the project financially. Some of them are <a href="https://jupyter.org/assets/google-color.svg" target="_blank">Google</a>, <a href="https://jupyter.org/assets/microsoft-color.svg" target="_blank">Microsoft</a>, <a href="https://jupyter.org/assets/rackspace-color.svg" target="_blank">Rackspace</a>, <a href="https://jupyter.org/assets/helmsley.svg" target="_blank">Leona M. and Harry B Helmsley Charitable Trust</a>, <a href="https://www.moore.org/" target="_blank">Gordon and Betty Moore Foundation</a> etc.  They do not take decisions about the projects&apos; progress, however, they may influence these decisions. </p>
<div id="cont"></div>

<h3 id="context-view">Context View</h3>
<p>In this section, the context viewpoint of Jupyter Notebook is described. The context view describes and visualises the relationships and interactions between Jupyter Notebook with the environment.</p>
<h4 id="system-scope">System Scope</h4>
<p>According to the Jupyter foundation <a href="http://jupyter.org/" target="_blank">website</a>, the Jupyter Notebook is</p>
<blockquote>
<p>an open-source web application that allows you to create and share documents that contain live code, equations, visualisations and explanatory text. </p>
</blockquote>
<p>The Notebooks are typically used for data cleaning and transformation, numerical simulation and machine learning tasks; the target audience is the broad tech audience, spanning from high school students to the most advanced researchers of the world.</p>
<p>Jupyter Notebook is the main application of the broader Jupyter project, which focuses on interactive and exploratory computing that is reproducible and multi-language.</p>
<h4 id="context-model">Context Model</h4>
<div id="contextmodel"></div>

<p><img src="https://delftswa.gitbooks.io/desosa-2017/content/jupyter/images-jupyter/contextview.png" alt="Context View"></p>
<p><strong>Figure 1</strong> - <em>Context Model of Jupyter Notebook.</em></p>
<p>In <a href="#contextmodel">Figure 1</a>, the context model of Jupyter Notebook is displayed. A short description of the most important entities in the diagram follows.</p>
<p>The project, which is a complex web application mainly <strong>used by</strong> <em>researchers</em> and <em>students</em>, can be conceptually separated in <em>front-end</em> and <em>back-end</em>. For what concerns the <strong>programming languages</strong>, <em>Python</em> is used for the back-end while the <em>LESS</em> stylesheet language is used in combination with <em>HTML</em> and <em>Javascript</em> for the front-end.</p>
<p>Thanks to the interoperability of Python, the project can run on most <strong>platforms</strong>, including <em>Windows</em>, <em>Mac OS X</em> and other <em>Unix-like</em> systems. There are no clear indications of officially supported <strong>browsers</strong>, but the documentation recommends the usage of <em>Chrome</em>, <em>Firefox</em> or <em>Safari</em>.</p>
<p>In terms of <strong>testing frameworks</strong>, <em>Nose</em> is used for the Python back-end while <em>CasperJS</em> is used for the front-end. Tests are executed automatically at each pull request, thanks to <strong>continuous integration</strong>. To this regard, <em>Travis CI</em> is used for testing on Linux and <em>AppVeyor</em> for Windows. Code coverage is analysed by <em>Codecov</em>. <em>ESLint</em> is used to enforce the <strong>code quality</strong> on the Javascript sources.</p>
<p>The system has multiple external <strong>dependencies</strong>, both in the front-end and in the back-end. In the former case, the key ones are <em>Bootstrap</em>, <em>Backbone.js</em>, <em>CodeMirror</em>, <em>Marked</em> and <em>MathJax</em>. In the latter, they are <em>Jinja2</em> and <em>Tornado</em>. The dependencies are managed using <strong>package managers</strong>, in particular, <em>Bower</em> is used for the front-end and <em>NPM</em> is used for the building tools.</p>
<p><strong>Sponsoring</strong> occurs in two ways: directly from companies like <em>Google</em>, <em>Microsoft</em> and <em>Rackspace</em> or by employing members of the Steering Council. The latter is the case for companies like <em>Bloomberg</em>, <em>Netflix</em> and for the <em>Berkeley University of California</em>. The <strong>development</strong> is carried on by the members of the Steering Council, including the BFDL Fernando P&#xE9;rez, and by the Github community.</p>
<p>As far as the <strong>documentation</strong> goes, it is maintained using the <em>Sphinx</em> documentation generator and published on the <em>Read The Docs</em> hosting platform.</p>
<p>The main <strong>competitors</strong> are the <em>Beaker Notebook</em> and <em>Apache Zeppelin</em>, both of which have shorter history and have not yet reached the maturity level of Jupyter.</p>
<p>Jupyter Notebook is <strong>licensed</strong> using the <em>3-clause BSD license</em>, while the <strong>copyright</strong> of the code belongs to the respective authors</p>
<div id="arch"></div>

<h2 id="architecture">Architecture</h2>
<div id="dev"></div>

<h3 id="development-viewpoint">Development Viewpoint</h3>
<p>The development view describes the architecture of a project from the viewpoint of the developers. According to Rozanski and Woods [<a href="#rw">1</a>], the development view is responsible for addressing different aspects of the system development process such as code structure and dependencies, build and configuration management of deliverables, system-wide design constraints, and system-wide standards to ensure technical integrity. In the following sections, the development view of Jupyter Notebook is presented based on the three models that Rozanski and Woods [<a href="#rw">1</a>] define in their book: Module Structure Model, Common Design Model and Codeline Model. In addition to this, a high-level view of Jupyter Notebook is included in order to ensure a thorough understanding of the project in different granularity.</p>
<h4 id="high-level-view">High-level view</h4>
<p><img src="https://delftswa.gitbooks.io/desosa-2017/content/jupyter/images-jupyter/global-overview.png" alt="Global overview"></p>
<p><strong>Figure 2</strong> - <em>High-level view of Jupyter Notebook.</em> [<a href="#global_view">2</a>]</p>
<p>The high-level view is visualized in Figure 2. First, the user interacts with the browser, consequently, a request is sent to the Notebook server. This can be either HTTP or WebSocket request. If user code has to be executed, the notebook server sends it to the kernel in <a href="http://zeromq.org/" target="_blank">ZeroMQ</a> messages. The kernel returns the results of the execution. At last, the notebook server returns an HTML page to the user.
When the user saves the document, it is sent from the browser to the notebook server. The server saves it on disk as a JSON file with a <code>.ipynb</code> extension. This notebook file contains the code, output and markdown notes. [<a href="#global_view">2</a>]</p>
<h4 id="module-structure-model">Module Structure Model</h4>
<p>The module structure model defines the organisation of the system&apos;s code clustering related source code files into modules and determining the dependencies between them [<a href="#rw">1</a>]. In this section first the modules of the project are briefly described and then the dependencies between them are visualised in a diagram. It should be also noted that this section focuses only on the internal modules of the project and not the external dependencies.</p>
<p>Here follows a short description of the modules that make up the project:</p>
<ul>
<li><strong>notebookapp</strong>: it is the entry point of the web application, including the Tornado-based server; it is responsible for the configuration of the server, including the mapping of requests to the handlers classes.</li>
<li><strong>auth</strong>: it manages the authentication to the notebook and other security-related features.</li>
<li><strong>base</strong>: it contains the base Tornado handlers that are extended by the other ones throughout the structure of the directory hierarchy; moreover, the handlers for the ZeroMQ sockets, which are responsible for the communication with the kernel, are included.</li>
<li><strong>bundler</strong>: it is used in order to bundle the notebook documents, packaging them in tarballs or zip archives.</li>
<li><strong>edit</strong>, <strong>kernelspecs</strong>, <strong>nbconvert</strong>, <strong>view</strong>, <strong>files</strong>, <strong>terminal</strong>, <strong>tree</strong>, <strong>notebook</strong>:
they contain the handlers for rendering the text editor interface, handling the views that are displayed to the user, converting notebook files to other formats, serving files via the content manager, rendering the terminal interface, displaying the tree view and controlling the live notebook view respectively.</li>
<li><strong>frontend</strong>: this module contains the code related to the user interface; in particular, <code>static</code> contains the Javascript &amp; CSS sources while <code>templates</code> consists of the Jinja2 HTML templates rendered by Tornado.</li>
<li><strong>services</strong>: it contains the handlers for the backend services, including kernels, kernel specifications and contents web services; all the handlers registered here start with the <code>/api/</code> prefix and communicate with the frontend using JSON whereas the other handlers render the HTML views.</li>
</ul>
<p>The module structure and dependencies are shown in <a href="#modulediagram">Figure 3</a>.</p>
<div id="modulediagram"></div>

<p><img src="https://delftswa.gitbooks.io/desosa-2017/content/jupyter/images-jupyter/module.png" alt="Module dependencies"></p>
<p><strong>Figure 3</strong> - <em>Module dependencies diagram.</em></p>
<p>Furthermore, it should be noted that the figure above shows high-level dependencies between the most significant modules of the system. In this graph modules that share a similar role in the system are grouped together for the convenience of the reader. The same purpose serve the colours of each of the modules. The diagram starts from the top with the <code>notebookapp</code> module which constitutes the entry point of the web application. It is worth mentioning that there are no <a href="https://en.wikipedia.org/wiki/Circular_dependency" target="_blank">circular dependencies</a> which makes the system easier to understand and maintain.</p>
<h4 id="source-code-structure">Source code structure</h4>
<p>The overall structure of the directory hierarchy of the Jupyter Notebook is organised as follows. The root folder consists of several files that are used to configure the system. More specifically, the root folder contains YAML files that are responsible for configuring the continuous integration of the project such as <code>.travis.yml</code> and <code>appveyor.yml</code>. Other important configuration files that are included in the root folder are <code>bower.json</code>, <code>setup.py</code> and <code>setupbase.py</code>. The <code>bower.json</code>  manifest file keeps track of the right versions of the front-end packages that are needed for the system. The <code>setup.py</code> and <code>setupbase.py</code> files are essential for configuring the installation of packages and their dependencies. </p>
<p>Furthermore, the root folder is divided into five separate folders: the <code>docs/</code> folder where all the documentation files that are built using Sphinx are located, the <code>git-hooks/</code> which consists of custom git hooks that are available for Jupyter Notebook. For example, there is a git hook that can be enabled to automatically compile the LESS stylesheets and the Javascript code after a git checkout. The <code>scripts/</code> which contains scripts that are used as an interface to the components of the notebook for the command line, the <code>tools/</code> folder containing tools used in the build process and the <code>notebook/</code> which contains all of the source code.</p>
<p>The <code>notebook/</code> folder is divided into sub-folders by grouping together source files with similar purpose and functionality. First off, it is divided into sub-folders that contain back-end functionality which are structured in a similar way. The related initializers can be found in <code>__init__.py</code> for the given sub-folder and next to that every sub-folder contains a module called <code>handlers.py</code> in which the Tornado handlers are included and registered. In addition, a <code>tests/</code> folder is included which consists of files that test the Tornado handlers functionality. </p>
<p>The front-end code is located in separate folders. In particular, the Javascript and CSS files are located in the <code>static</code> folder using as the name for the sub-folders the one of the back-end components they interact with. The <a href="http://jinja.pocoo.org/docs/2.9/" target="_blank">Jinja2</a> HTML templates are included in the <code>templates/</code> folder. Concerning the tests that are responsible for testing the front-end functionality, they are contained in the <code>notebook/tests/</code> folder. Finally, the <code>notebook/</code> folder contains the entry point of the web application which is the <code>notebookapp.py</code> module and some common utilities that are used throughout the whole source code. A graphical overview can be found in <a href="#src">Figure 4</a>.</p>
<div id="src"></div>

<p><img src="https://delftswa.gitbooks.io/desosa-2017/content/jupyter/images-jupyter/source_code.png" alt="Source code structure"></p>
<p><strong>Figure 4</strong> - <em>Source code structure of Jupyter Notebook.</em></p>
<h4 id="continuous-integration-and-testing-approach">Continuous Integration and Testing Approach</h4>
<p><em>Continuous Integration (CI)</em> refers to the development practice in which developers <em>integrate</em> the code to a shared repository frequently. Each integration is verified by an automated build and test system.</p>
<h5 id="testing-frameworks">Testing Frameworks</h5>
<p>The Jupyter Notebook project has a Python backend and an HTML + Javascript frontend. There are two separate testing suites: one for the backend and one for the frontend.</p>
<p>The Python <strong>backend</strong> is tested using the <code>nose</code> testing framework, a package built on top of <code>unittest</code> to simplify test-driven development.
This testing framework <a href="https://nose.readthedocs.io/en/latest/" target="_blank">has been</a> in maintenance mode for several years now and its maintainers are suggesting to move to the newer framework <code>nose2</code>, but the Jupyter Notebook maintainers don&apos;t seem to have any plan to move forward.</p>
<p>For the <strong>frontend</strong> code testing, CasperJS is used. It is a Javascript testing framework built with JS itself and leveraging PhantomJS.
In the recent issue <a href="https://github.com/jupyter/notebook/issues/2243" target="_blank">#2243</a>, the developers discuss the problems related to the Javascript tests. Apparently, race conditions and the asynchronous nature of Javascript make the tests fail at times. Developers are investigating a fix for this.</p>
<h5 id="continuous-integration-services">Continuous Integration Services</h5>
<p>The project uses the integration <a href="https://github.com/integrations/feature/continuous-integratio" target="_blank">offered</a> by Github to automate building and testing of the pull requests as they are opened or updated.
In particular, three CI services are used: <em>Travis CI</em>, <em>AppVeyor</em> and <em>Codecov</em>.</p>
<p><strong>Travis CI</strong> is used by the project to automate build and testing on Linux. The configuration, specified using the <code>.travis.yml</code> file, is such that:</p>
<ul>
<li>Testing is done using both Python 2.7 and 3.5.1</li>
<li><em>Both</em> the frontend and the backend are tested</li>
<li>When testing is done, the Python coverage reports generated by Nosetests are uploaded to Codecov.</li>
</ul>
<p>Since Travis CI does not yet support the Windows OS, <strong>AppVeyor</strong> is used for the testing on this platform. The configuration is such that only the backend is tested, using both Python 2.7 and 3.5, and code coverage is not checked.</p>
<p><strong>Codecov</strong> is a hosted CI service that computes a coverage score of the unit tests.
The Jupyter Notebook project uses Codecov to analyse the coverage of the Python backend tests at each pull request. The coverage is not checked for the frontend because the testing framework does not support the generation of coverage reports. The service is configured by means of the <code>codecov.yml</code> file <a href="#codecov-yaml">[6]</a> so that the automatic checking of the pull requests fails if a decrease in the coverage score greater than 10% is observed.</p>
<div id="fun"></div>

<h3 id="functional-viewpoint">Functional Viewpoint</h3>
<p>Rozanski and Woods [<a href="#rw">1</a>] explain that the functional view &quot;defines the architectural elements that deliver the function of the system being described&quot; (p. 294). 
This view documents the key runtime functional elements, their responsibilities, interfaces and primary interactions. 
In the notebook project, different key functional elements are present that interact with internal and external elements during run-time.
Interfaces like in <code>Java</code> are not present in <code>Python</code>. 
But these functional elements do behave like interfaces, as they have well-defined functions that can be called by other elements, to perform different actions. 
The functional view of our project is visualised on figure 5. The key elements and the interaction between them is described next.</p>
<p><img src="https://delftswa.gitbooks.io/desosa-2017/content/jupyter/images-jupyter/functional_view.png" alt="Functional view">
<strong>Figure 5</strong>: <em>UML diagram of the Functional View.</em></p>
<p>The main entry point of the web application is an instance of the class <code>NotebookApp</code>. 
It sets up a Tornado based Notobook server that serves an HTML/Javascript client. 
It also launches an instance of the <code>NotebookWebApplication</code> class. The server delegates all the incoming requests to the <code>NotebookWebApplication</code> object. 
This class is a sub-class of <code>Tornado.Web.Application</code>, which is used to map the different types of incoming requests to the correct handlers.</p>
<p>The handlers use external elements to leverage existing functionalities from the other Jupyter projects.<br><code>Jupyter_core</code> is used for basic functionalities like handling configuration files and filesystem locations. 
<code>Jupyter_client</code> provides APIs for working with kernels. Kernels are used to execute user code. 
Furthermore, <code>nbformat</code> provides APIs for working with notebook files, such as loading, reading and saving. 
Notebook uses <code>nbconvert</code> to export notebook files into various static formats such as PDF, HTML and LaTeX.</p>
<p>The <code>NotebookApp</code> can only be used by a single user with no login. On top of the notebook, there are other external elements which provide additional functionalities. 
First, <code>tmpnb</code> can launch a temporary Jupyter notebook server for multi-user use, without login. 
Second, <code>jupyterhub</code> can create a multi-user hub with login which manages multiple instances of the single-user <code>NotebookApp</code>. 
At last, <code>nbgrader</code> provides a toolbar extension which allows a teacher to make and grade assignments on the notebook.</p>
<div id="debt"></div>

<h2 id="technical-debt">Technical Debt</h2>
<p>The technical debt concept is related to the extra development work that is introduced when solutions that are easy to implement in the short run are used instead of applying the optimal ones that will keep the project maintainable in the long run; it is not only related to the code, it can also be associated with the (lack of) documentation, or with the low testing coverage.</p>
<p>This section focuses on the following three types of technical debt: <em>code debt</em>, <em>testing debt</em> and <em>documentation debt</em>.</p>
<h3 id="code-debt">Code Debt</h3>
<p>Coping with code debt as soon as possible is important because the size of the code, as it grows, will make the maintenance difficulty ever increasing.
The identification of code debt has been done using both automated analysis tools and via manual inspection. </p>
<p>In relation to the code readability, the Jupyter project documentation states in the <a href="http://jupyter.readthedocs.io/en/latest/development_guide/coding_style.html" target="_blank">coding style</a> section that the code should follow the PEP8 guidelines. 
To investigate the adherence of the code to the guidelines the <code>flake8</code> tool was used to lint the codebase, discovering numerous inconsistencies, including mis-indentation, usage of tabs, unused imports, multiple imports on the same line and lambda expressions assigned to variables, for a total of 2075 errors/warnings.</p>
<p>Deprecation warnings are another symptom of code debt, as they mean that the developers are not keeping the code up to date with the evolution of the ecosystem. An example of this kind of debt was discovered while running the automated backend test suite.  In particular, the <code>decodestring() is a deprecated alias, use decodebytes()</code> deprecation warning was shown.
As the Python documentation states, there is a new API to work with base 64 encoding (<a href="https://docs.python.org/3/library/base64.html#base64.b64decode" target="_blank">base64.b64decode</a>) which is supposed to be used. A pull request (<a href="https://github.com/jupyter/notebook/pull/2280" target="_blank">#2280</a>) was submitted to the project repository to fix this issue.</p>
<p>Another way of identifying code debt is by manually searching for <a href="https://github.com/jupyter/notebook/search?utf8=%E2%9C%93&amp;q=TODO" target="_blank">&quot;TODO&quot;</a> and <a href="https://github.com/jupyter/notebook/search?utf8=%E2%9C%93&amp;q=FIXME" target="_blank">&quot;FIXME&quot;</a> comments in the codebase. As of <em>13/03/2017</em> Jupyter Notebook had <strong>21 &quot;TODO&quot;</strong> and <strong>10 &quot;FIXME&quot;</strong> comments in the code. 
A TODO comment was found in the <a href="https://github.com/jupyter/notebook/blob/666ecbf35c3310335a3c8c182e8f53441c991c14/notebook/static/base/js/page.js" target="_blank">page.js</a> file, referring to the removal of hard-coded selectors from the code. Hard-coded strings are generally considered a bad coding practice that seriously hinders the flexibility of the code. A pull request (<a href="https://github.com/jupyter/notebook/pull/2279" target="_blank">#2279</a>) that tackles this code debt refactoring the parameters to be dynamic was submitted. A FIXME comment was also found in the file <a href="https://github.com/jupyter/notebook/blob/master/notebook/services/contents/handlers.py#L126-L129" target="_blank">handlers.py</a>, mentioning that a certain functionality should have been implemented in the frontend rather than in the backend. An examination of the frontend code revealed that the functionality was already present there and thus pull request <a href="https://github.com/jupyter/notebook/pull/2281" target="_blank">#2281</a> was submitted to remove the redundancy.</p>
<h3 id="testing-debt">Testing Debt</h3>
<p>For what concerns the <strong>backend</strong> testing, the coverage is reported by <code>nose</code> and analysed by CodeCov. The actual coverage on the master branch is <a href="https://codecov.io/gh/jupyter/notebook" target="_blank">77.24%</a>. Test coverage usefulness as a metric has been debated, and the general consensus <a href="https://martinfowler.com/bliki/TestCoverage.html" target="_blank">is that</a> it is mainly a tool to discover untested parts of the codebase, rather than being an assurance that the codebase is well tested. The source files with the lowest reported coverage were analysed, and in the process, it was discovered that the tests for a certain file were not run because of a missing requirement in Travis CI; pull request <a href="https://github.com/jupyter/notebook/pull/2283" target="_blank">#2283</a> was opened to fix the issue resulting in a 1.09% increase of the overall coverage.</p>
<p>On the <strong>frontend</strong> side, test coverage is not analysed because the testing framework chosen cannot output coverage reports. It seems anyway that there is significant technical debt. For instance, a number of pull requests were lately <a href="https://github.com/jupyter/notebook/pull/2220#issuecomment-283406164" target="_blank">accepted</a> without requiring the unit tests, since the Javascript testing suite seems to have significant problems; issue <a href="https://github.com/jupyter/notebook/issues/2243" target="_blank">#2243</a> was opened by the maintainers to track the status of the testing suite and possibly fix the problems.
It also <a href="https://github.com/jupyter/notebook/pull/2220#issuecomment-283530644" target="_blank">seems like</a> not all the developers are up to date with the frontend testing. In addition to this, Travis CI was configured to use the <code>travis_retry</code> for the frontend tests, in order to repeat them 3 times in the case that they fail. This function is <a href="https://docs.travis-ci.com/user/common-build-problems/" target="_blank">supposed to be used</a> to deal with network timeouts during the requirements installation and is therefore misused in this context. </p>
<h3 id="documentation-debt">Documentation Debt</h3>
<p>Developers need to write documentation of their source code, which may be of help for other developers to understand their code. More importantly, when they would not work anymore for a project, people coming after and new contributors should also be able to understand the system and its setup. In addition, documentation for the end user of the product is needed in order to understand how to download, install and use the product. </p>
<p>Jupyter Notebook documentation is lacking in many parts of the project.
Specific examples are listed below:</p>
<ul>
<li>An example of bad documentation is observed in issue <a href="https://github.com/jupyter/notebook/issues/603" target="_blank">#603</a> where a new user tries to use the shortcuts within Notebook but runs into trouble because the functionality is not clearly explained. This is supposed to be fixed in release <a href="https://github.com/jupyter/notebook/milestone/18" target="_blank">5.0</a> as @<a href="https://github.com/pkgw" target="_blank">pkgw</a> and @<a href="https://github.com/ellisonbg" target="_blank">ellisonbg</a> advised.</li>
<li>Another documentation debt is identified in the issue <a href="https://github.com/jupyter/notebook/issues/1754" target="_blank">#1754</a> where user @<a href="https://github.com/dsblank" target="_blank">dsblank</a> wanted to contribute to the project and tried to install the development environment on Ubuntu but got a lot of errors. Eventually, he managed to fix the issue by looking at the setup of the <a href="https://github.com/jupyter/notebook/blob/master/.travis.yml" target="_blank"><code>.travis.yml</code></a> file. The user notes that this is not explained in the documentation.</li>
</ul>
<p>Finally, the biggest part of documentation debt was found from the first sight, by just looking at the title, which says <em>(source: old IPython wiki)</em> (<a href="https://jupyter.readthedocs.io/en/latest/development_guide/index.html" target="_blank">IPython Development Guide</a>) and the whole documentation is outdated. There is, in fact, a note that states:</p>
<blockquote>
<p>This is copied verbatim from the old IPython wiki and is currently under development. Much of the information in this part of the development guide is out of date.</p>
</blockquote>
<p>This is a clear indication of debt that needs to be paid and may cause confusion about where the correct documentation is if such exists and where is it located. Improvements of documentation are always welcome by the core developers and they try to encourage contributors to help them with this.</p>
<div id="evo"></div>

<h2 id="evolution-perspective">Evolution Perspective</h2>
<p>In this section, the evolution of the project is presented, along with the most important facts and changes part of its history.</p>
<h3 id="the-past-ipython">The Past: IPython</h3>
<p>The predecessor of Jupyter Notebook is IPython. It was born in 2001 as an afternoon hack by the hands of Fernando Perez [<a href="#ipython-history">3</a>], in the attempt to improve the Python REPL. 
It was a 250 lines Python script trying to mimic the Wolfram Mathematica prompt system to enable scientific computing with Python.</p>
<p>Over the years the need for a notebook-like front-end grew, and after multiple unsuccessful attempts, in 2011 the IPython Notebook was born. 
The key in building this fully working web-based notebook system was the coupling of the Tornado webserver for asynchronous WebSocket-based communication and ZeroMQ for the communication with the kernels.</p>
<p>Many features were added in the following years following the users&apos; needs, and the codebase developed organically incorporating different components that were increasingly becoming distinct projects. 
Moreover, at this point many different languages were supported by the project, so the name <em>Interactive Python</em> was starting to feel odd.</p>
<h3 id="the-present-jupyter">The Present: Jupyter</h3>
<p>For these reasons, in 2014 at the SciPy conference, the Jupyter project was announced, incorporating all the language-agnostic features of IPython, such as the notebook. </p>
<p><img src="https://delftswa.gitbooks.io/desosa-2017/content/jupyter/images-jupyter/evolution_loc.png" alt="Evolution of LOC of the IPython project"></p>
<p><strong>Figure 6</strong> - <em>Evolution of LOC of the IPython project.</em> [<a href="#evolution-loc">4</a>]</p>
<p>In 2015 the first phase of <a href="http://blog.jupyter.org/2015/04/15/the-big-split/" target="_blank">The Big Split&#x2122;</a> was completed, splitting all the components into subprojects.
As can be seen from Figure 6, a vast amount of code was removed from the IPython project and moved to separate repositories corresponding to the different subprojects, such as <em>traitlets</em>, <em>nbformat</em> and the <em>notebook</em> itself.
IPython continues to live to this day as a kernel for Jupyter and as the interactive shell environment.</p>
<p>The Jupyter project gained more popularity, not only among data scientist but also among software engineers. At this point, Jupyter Notebook was not only about the notebook experience because it also shipped with a web-based terminal, text editor, and file browser. All these components were not blended together and the user community started expressing the need for a more integrated experience.</p>
<h3 id="the-future-jupyterlab">The Future: JupyterLab</h3>
<p>At the SciPy 2016 conference, the JupyterLab project <a href="https://www.youtube.com/watch?v=Ejh0ftSjk6g" target="_blank">was announced</a>. It was described as the natural evolution of the Jupyter Notebook interface.</p>
<p>The codebase of the Notebook was showing its age and it was becoming more and more difficult to extend. The cost of maintaining the old codebase and implementing new features on top of it was ever increasing.</p>
<p>The developers incorporated in this new project all the lessons that they learned from the usage patterns of the Notebook, to build a robust and clean foundation for a flexible interactive computing experience and an improved user interface.</p>
<p><img src="https://delftswa.gitbooks.io/desosa-2017/content/jupyter/images-jupyter/jupyterlab.png" alt="JupyterLab User Interface"></p>
<p><strong>Figure 7</strong> - <em>JupyterLab User Interface.</em></p>
<p>In figure 7 the user interface of the JupyterLab project, based on the PhosporJS framework, is shown. The division in tabs and panes allows using different components (file browser, terminal, notebook), that can be used only separately in the classic Notebook, at the same time.</p>
<p>As of April 2017, the project is still in the early preview phase, and it is not suitable for general usage yet. A series of phases are planned to enable a smooth transition from the classic Notebook to the new environment, as eventually JupyterLab will become the default UI and the classic notebook will only be available as a separate download.</p>
<div id="concl"></div>

<h2 id="conclusion">Conclusion</h2>
<p>Jupyter notebook is currently the most popular and widely used tool for students and data scientists to create and share documents containing live code, explanations and visualisations.
Its popularity can be validated by the fact that Github natively supports the rendering of notebook files.</p>
<p>While going through the code, our team found five issues that could give problems in the long-run i.e. non-compliance to code style, hard-coded variables, duplicate code, deprecated methods and low test coverage.
Pull requests were made to pay off these technical-debt-related issues and four of them got accepted.
Two additional pull requests, related to bug fixes, were made and both were merged to master.
The developers provided extensive feedback and suggestions to our pull-requests which was very helpful.</p>
<p>Even though the documentation of the project was lacking for the most part and the analysis of the project&apos;s architecture proved to be more challenging than we thought, our team managed to understand the inner workings of the system. We learned that real-world software does not always correspond to the ideal architectures that we discuss in theory, but it can nonetheless be successful. We also learned that <em>The code is the truth, but it is not the whole truth</em> (Grady Booch), and that the Jupyter ecosystem, including its community, plays a major part in the success of the project.
We are excited to see what the future has in store for the Jupyter project.</p>
<p><em>If you are considering joining the Jupyter notebook community and make contributions, do not hesitate.
The Jupyter community will welcome you with open arms. This chapter together with the contribution <a href="https://github.com/jupyter/notebook/blob/master/CONTRIBUTING.rst" target="_blank">guidelines</a> and <a href="https://jupyter.readthedocs.io/en/latest/" target="_blank">documentation</a> will guide you towards your contributions.</em></p>
<div id="ref"></div>

<h2 id="references">References</h2>
<ol>
<li><div id="rw"></div>Nick Rozanski and Eoin Woods. Software Systems Architecture: Working with Stakeholders using Viewpoints and Perspectives. Addison-Wesley, 2012.</li>
<li><div id="global_view"></div>Jupyter documentation (<a href="http://jupyter.readthedocs.io/en/latest/architecture/how_jupyter_ipython_work.html" target="_blank">http://jupyter.readthedocs.io/en/latest/architecture/how_jupyter_ipython_work.html</a>)</li>
<li><div id="ipython-history"></div>The IPython notebook: a historical retrospective (<a href="http://blog.fperez.org/2012/01/ipython-notebook-historical.html" target="_blank">http://blog.fperez.org/2012/01/ipython-notebook-historical.html</a>)</li>
<li><div id="evolution-loc"></div>IPython LOC Analysis (<a href="https://www.openhub.net/p/ipython/analyses/latest/languages_summary" target="_blank">https://www.openhub.net/p/ipython/analyses/latest/languages_summary</a>)</li>
</ol>

                                

