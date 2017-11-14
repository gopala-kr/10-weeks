<h1 id="scikit-learn">Scikit learn </h1>
<p>By <a href="https://github.com/i-am-xhy" target="_blank">N.Bakker</a>, <a href="https://github.com/romikharisnawan" target="_blank">R.Kharisnawan</a>, <a href="https://github.com/berndkr" target="_blank">B.Kreynen</a> and <a href="https://github.com/harrisval" target="_blank">C.M.Valsamos</a></p>
<p><em>Delft University of Technology, 2016</em></p>
<p><img src="images-team-scikit-learn/scikit-learn-logo.png" alt=""></p>
<h2 id="abstract"><em>Abstract</em> </h2>
<p><em>Scikit-learn started as a Google Summer of code project by David Cournapeau 9 years ago. Currently it is one of the most used libraries in python regarding machine learning due to its efficiency and simplicity. Despite its small size in its core team, external developers contribute daily to the project and the project keeps growing. Being passionate data scientists we were eager to explore its framework, and thus conducted a stakeholder analysis to see who is involved with scikit-learn. We then describe scikit-learn from various viewpoints and perspectives to understand its software architecture. Finally, this chapter closes with the analysis of technical and testing debt.</em></p>
<h2 id="introduction">Introduction</h2>
<p>This chapter describes scikit-learn from the software architecture perspective. Scikit-learn is an open source machine learning library in the Python programming language. It has been growing and becoming more popular because of its efficiency and simplicity in use. Also, the fact that it is an open source library makes scikit-learn not only used by companies but also by individuals.</p>
<p>The chapter starts with a stakeholder analysis of the scikit-learn library. In this section, stakeholders are identified and an analysis is given on how they influence the library. This is done through Rozanski and Woods&apos; classification, an additional stakeholders analysis, and a power-interest grid analysis. In addition, the project integrators are also identified. The section is followed by software views, which consists of the context, development, and deployment view. In this section, scikit-learn is explored from different kind of views to give a better understanding on how the library works, both internally and externally. Perspective on computational performance gives further explanation on performance of scikit-learn as machine learning library. The next section is software debts, which discusses technical debt and testing debt. Lastly, the chapter is closed with the conclusion of the whole analysis.</p>
<h1 id="stakeholders-analysis">Stakeholders Analysis</h1>
<h2 id="core-team-members-and-contributors">Core team members and contributors</h2>
<p>In this subsection, stakeholder analysis is explained  based on a chapter in Rozanski and Woods&apos; book; Software Systems Architecture: Working With Stakeholders Using Viewpoints and Perspectives Chapter 9 [2]. Stakeholders are classified into:</p>
<h3 id="acquirers">Acquirers</h3>
<p>Acquirers oversee the procurement of the system or product and foresee funding [2]. Some companies and institutions have provided funding or use scikit-learn. These will have to make decisions about the acquisition of scikit-learn and might expect a return on investment of some sort. Examples include INRIA (Institut National de Recherche en Informatique et en Automatique), Paris-Saclay Center for Data Science, NYU Moore-Sloan Data Science Environment, T&#xE9;l&#xE9;com Paristech, Columbia University, Google, Tinyclues.</p>
<h3 id="assessors">Assessors</h3>
<p>Assessors oversee the system&apos;s conformance to standards and legal regulations [2]. Contributors who review pull requests ensure that the proposed changes adhere to the standards of scikit-learn contributions. However, someone with the clear role of assessing legal regulations could not be identified.</p>
<h3 id="communicators">Communicators</h3>
<p>Communicators explain the system to other stakeholders, provide training and create manuals [2]. Scikit-learn&apos;s website is the main communication tool where its content is also managed by contributors and maintainers. There are several communication channels besides the website, such as  Stack Overflow [4], a mailing list, and an IRC channel.</p>
<h3 id="developers">Developers</h3>
<p>Developers construct and deploy the system from specifications [2]. Contributors on GitHub are developers. Some of them are sponsored by the institutions and organizations mentioned in the acquirers section.</p>
<h3 id="maintainers">Maintainers</h3>
<p>Maintainers manage the evolution of the system when it is operational, they focus on developing documentation, instrumentation, debug environments, preservation of knowledge, .... [2]. This role is mainly performed by Andreas M&#xFC;ller who has the role of release manager[1] at the time of writing. Other maintainers are contributors in GitHub who are willing to maintain the documentation and code of the library.</p>
<h3 id="production-engineers">Production engineers</h3>
<p>Production engineers design, deploy and manage the hardware and software environments in which the system will be built, tested and run [2]. Andreas M&#xFC;ller performs this role as a release manager. Staff in the companies who use scikit-learn can also fall under this category.</p>
<h3 id="suppliers">Suppliers</h3>
<p>Suppliers build and/or supply hardware, software or infrastructure to run the system [2]. They can also provide staff for its development or operation. Some of the suppliers of scikit-learn are:</p>
<ul>
<li><strong>Rackspace</strong>: Provides cloud services for automatically building documentation [1].</li>
<li><strong>Shining Panda</strong>: Provides CPU time on continuous integration servers [1].</li>
<li><strong>Github</strong>: Provides hosting of version control.</li>
<li>Acquirers of project: Some provide funding to developers, for example Columbia University [1].</li>
</ul>
<h3 id="support-staffs">Support staffs</h3>
<p>Support staff provides support to users when the system is operational [2]. Communicators and support staff are the same group of stakeholders in scikit-learn.</p>
<h3 id="system-administrators">System administrators</h3>
<p>System administrators run the system once it is has been deployed [2]. As scikit-learn is a library used in python, it runs locally on whichever system the users wants to use it on. Therefore, system administrators are those people the users of scikit-learn appoint to do this task.</p>
<h3 id="testers">Testers</h3>
<p>Testers systematically test the system to see if it is suitable for deployment and use [2]. When an enhancement is proposed to scikit-learn via a pull request, high-coverage tests are required for them to be accepted [3]. In addition, continuous integration tools automatically run these tests to ensure they pass each PR as well.</p>
<h3 id="users">Users</h3>
<p>Users are those who eventually use the system. Several examples of users are Spotify, betaworks, evernote, booking.com, AWeber, YHat, Research teams at INRIA, T&#xE9;l&#xE9;com ParisTech. Scikit-learn is also suited for individual users who want to do research, or do a project involving data analysis.</p>
<h2 id="additional-stakeholders">Additional Stakeholders</h2>
<p>With the categorization of stakeholders in the method proposed by Rozanski &amp; Woods [2], we can find relevant stakeholders for most categories. However, it is noticeable that many stakeholders appear in many different categories in some way. In this section, a new categorization of the stakeholders is introduced to make the categories more distinct and the roles less intertwined. This categorization is less generally applicable, since it&apos;s tailored to scikit-learn. The different categories are contributors, users, funders and competitors.</p>
<p><img src="images-team-scikit-learn/stakeholder.jpg" alt=""><br><em>Figure 1: Visualization of the stakeholder categories for scikit-learn.</em></p>
<h3 id="contributors">Contributors</h3>
<p>The first category is the contributors category. These stakeholders consist of everyone who contributes on Github. In March 2017, there were 798 contributors on the Github repository of scikit-learn. They are actively involved in raising issues, development, documentation, maintenance, and testing of scikit-learn. They also help with roles that belong to the communicators and support staff in Rozanski &amp; Woods, since the contributors also create tutorials and contribute on Stack Overflow, the mailing list, and IRC channel.</p>
<p>For this group, it is important that they collectively understand the architecture and functionality of scikit-learn. Since they maintain and develop the system, they are concerned with the maintainability, flexibility, documentation and preservation of knowledge of the library.</p>
<h3 id="users">Users</h3>
<p>As opposed to the categorization by Rozanski &amp; Woods[2], we do not make the distinction between acquirers and users. Due to the simplicity of acquiring scikit-learn, an acquirers category seems less relevant to scikit-learn.</p>
<p>The users of scikit-learn are the various companies and organizations who utilise scikit-learn. There are quite a few variations between the users of scikit-learn but overall users will be concerned with documentation and ease of use since they will want to know how to use the methods implemented in scikit-learn. Reliability and correctness will also be a big concern for the users of scikit-learn. Finally, they may also be concerned about the maintainability of code which implements scikit-learn as opposed to the maintainability of scikit-learn itself.</p>
<h3 id="funders">Funders</h3>
<p>Funding to scikit-learn can be in the material or monetary form. This category corresponds somewhat to the acquirers category of Rozanski &amp; Woods[2]. Generally, they expect some type of return on investment but this can come in many forms. Research institutions, for example, might want to be able to influence the developtment of scikit-learn to benefit their research and might be interested in the knowledge gained from working on the development of scikit-learn. An example of this would be INRIA. Companies might also want to influence the development of scikit-learn through funding but might be more concerned with influencing it so that they can use it to get a return on investment. Finally, companies like Rackspace and Shining Panda, who provide free services, might be interested in the publicity gained from working with scikit-learn.</p>
<h3 id="competitors">Competitors</h3>
<p>Competitors to scikit-learn are other libraries which provide machine learning methods. Their developers could be interested in the development of scikit-learn to see which methods of scikit-learn they can utilize as well. However, they have very little influence on the development of scikit-learn. Examples of competitors are GraphLab [25] (machine learning library in C++) and ROOT [26] (data analysis framework in C++).</p>
<h2 id="project-integrators">Project Integrators</h2>
<p>The project integrators are those people whose job (or volunteered work) it is to guarantee different qualitative properties and validate changes to the project. On March 2017, there were 40 people that have the capability of doing this[5].</p>
<p>These integrators face a specific set of challenges for scikit-learn. Starting with scikit-learn being a very theory heavy project, which is reflected by the length of discussions on issues. The discussion are often about whether pull requests are properly implementing the expected theory correctly. Examples are PR 8253 [6] and PR 8280 [7].</p>
<p>Because of this complexity, they also need to handle their Integrators with extra scrutiny, requiring two of them to write off on each and every pull request. Integrators also use automated testing and demand high coverage before accepting pull requests. The process is done to further guarantee the quality under pull request checklist [8].</p>
<h2 id="power-interest-grid">Power-interest grid</h2>
<p>Figure 2 shows the quadrants of power and interest of scikit-learn stakeholders. The x-axis determines interest of stakeholders to scikit-learn which is divided into low and high interest. The interest of stakeholders is demonstrated by their willingness to explore, use, or contribute to the library. Contributions could be in the form of funding or taking part in development. The y-axis determines the power of stakeholders which is also divided into low and high power. Power is related to how influential the stakeholder is in scikit-learn&apos;s past, current, and future development. Therefore, the most powerful entities are in the upper-right quadrant and the least powerful ones in the opposite lower-left quadrant. As an example, Andreas M&#xFC;ller is in the upper-right quadrant because he has been the release manager since 2016, which indicates his high interest and influence in the development process. On the other hand, David and Matthieu were founders of scikit-learn [1] but they are not active in the development any more. Thus, they are classified in the high interest and low power area.</p>
<p><img src="images-team-scikit-learn/powerinterest.png" alt=""><br><em>Figure 2: Power-Interest grid.</em></p>
<h1 id="views">Views</h1>
<p>In this section, we describe three views on the scikit-learn architecture: context, development, and deployment view. A view can be seen as a model of the architecture, with each view capturing different aspects of the architecture.</p>
<h2 id="context-view">Context View</h2>
<p>This section contains the relationship between scikit-learn and other related entities. It helps to identify the purpose of the system and to understand its relationship with the environment.</p>
<h3 id="design-philosophy"><strong>Design Philosophy</strong></h3>
<p>Scikit-learn was developed to provide easier implementation of data analysis methods, so individuals without much prior knowledge can use it. As a machine learning library, it provides several techniques in both supervised and unsupervised learning. Also, to make the library easy-to-use, scikit-learn provides examples of implementations and datasets. It is important to provide standardized datasets, not only for showing implementation examples, but also to provide training data to create classifiers. Additionally, a machine learning library will not be a useful library without visualization. Therefore, there are visualization examples to illustrate the performance of a classifier by using matplotlib as a basis of visualization.</p>
<h3 id="diagram"><strong>Diagram</strong></h3>
<p>Figure 3 describes the relationship between scikit-learn and its environment. It consists of ten external entity types which are related to scikit-learn. Each entity has a specific relationship to the library, for example users use scikit-learn or GitHub manages versioning and issue tracking for scikit-learn. Each specific entity inside an entity type may have a different weight of closeness to the library depending on their interactions, for example INRIA may have a stronger relation compared to Paris-Saclay Center for Data Science because they are still sponsoring scikit-learn at the time of writing.</p>
<p><img src="images-team-scikit-learn/contextview_2.png" alt=""></p>
<p><em>Figure 3: Context View.</em></p>
<h2 id="development-view">Development View</h2>
<p>The development view is what gives developers (and testers) a birds eye view of the architecture. It should not be too detailed or descriptive, but still cover the most important bases.<br>The development viewpoint discussed here is about scikit-learn&apos;s module structure model.</p>
<h3 id="module-structure-model">Module Structure Model</h3>
<p>The module structure model defines the organization of the system&#x2019;s source code and related external systems, in terms of the modules into which the individual source files are collected and the dependencies among these modules [2]. In Figure 4 layers are identified for scikit-learn with each layer consisting of one or more module(s). These layers are:</p>
<ul>
<li>Domain layer: consisting of all main functionality modules: data transformations [29], data loader [30], model selection [31], supervised learning [32], and unsupervised learning [33].</li>
<li>Utility layer: consisting of modules that support basic functionality that can be used in domain layer, such as testing, validation, preprocessing, sparse tool, and external configuration.</li>
<li>Platform layer, which contains modules of the required packages, such as python [34], NumPy [35], and SciPy [36].</li>
<li>Build tool layer, which contains build modules [37] to build the library. Each module consists of files to download, install, testing, or setting the required library.
Dependency of one layer to the other layer(s) is demonstrated by a dashed arrow which points to the destination of the required layer. As an example, the utility layer uses all libraries available from python, NumPy, SciPy, and Pandas by importing them in the module. In addition, there are explicit intermodule dependencies for all modules in the domain layer for python because all files under each module requires python.</li>
</ul>
<p><img src="images-team-scikit-learn/modules_model.jpeg" alt="alt tag"><br><em>Figure 4: Modules Structure Model.</em></p>
<p>This model answers the first concern of Rozanski and Woods addressed by the development view [2] by giving a better understanding of the module organization. Each module consists of hundred, possibly thousands, of source files and even more lines of code, which are used to implement libraries or functional elements. As a software architect it is useful to know the generic view of a system before going too much into detail. By analyzing through this model, we understand better in which way scikit-learn has been managed and the depencies between modules are clearly highlighted. In this library, a module is usually representated by a folder in the sklearn directory[9].</p>
<p>Another good thing that can be inferred by this model is how to arrange code in a logical structure. Thereby, it will help to manage dependencies and cultivate a better understanding with developers of these interdependencies without affecting other modules in unexpected ways.</p>
<h2 id="deployment-view">Deployment view</h2>
<p>The deployment view is what looks into how the program is expected to operate in live operation. It will show what &quot;hidden&quot; dependencies scikit-learn has, it&apos;s runtime environment and lastly the required specialist knowledge for (parts of) scikit-learn.</p>
<p><img src="images-team-scikit-learn/deployment_view.png" alt="alt tag"><br><em>Figure 3A: the deployment view for scikit-learn</em></p>
<h3 id="dependencies">Dependencies</h3>
<p>Running a scikit-learn instance requires several supporting libraries and programs [10]. These are, at the time of writing:</p>
<ul>
<li>Pip, while not a hard demand, in general is the way scikit-learn gets installed</li>
<li>Conda, an alternative to pip to install scikit-learn</li>
<li>Python, ( &gt; =2.6 or &gt; =3.3) scikit-learn requires an instance of python to run it&apos;s scripts.</li>
<li>NumPy (&gt;=1.6.1)</li>
<li>SciPy(&gt;=0.9)</li>
</ul>
<p>there are some technology compatibility conflicts between pip/conda and the required libraries. As the former tends to compile from source whereas the libraries tested are the provided binaries. Which can lead to differences.</p>
<h3 id="runtime-environment">Runtime environment</h3>
<p>As scikit-learn runs entirely within a single system, and on this system it runs inside python. Most of its runtime environment is either highly simplified or defined by its hosting programs.</p>
<ul>
<li>A computing system (computer/phone etc.) with support for python (&lt;1GB hdd space and a supporting processor architecture, preferably a bit of ram as well (say 128MB+))</li>
<li>the prerequisites mentioned in dependencies</li>
</ul>
<p>These limits are, however, rather unrealistic when using scikit-learn. As in most cases, scikit-learn is used on rather large datasets, which would increase RAM/HDD usage accordingly.</p>
<h3 id="specialist-knowledge">Specialist knowledge</h3>
<p>To use Scikit-learn(&apos;s full potential) a lot of specialist knowledge is required. These required types of specialists are people a major company may want to have before adopting scikit-learn.</p>
<ul>
<li>Linear algebra, practically a demand for using scikit-learn as it is used almost everywhere that constitutes actual functionality. In addition, it is often a prerequisite for the other knowledge areas.</li>
<li>Machine learning, scikit-learn allows use of neural network techniques, k-means and other techniques to provide most of its functionality.</li>
<li>Set/collection theory, operations on and properties of sets are (implicitly) used as the basis for certain operations (such as biclustering, mean_shift and kmeans)</li>
</ul>
<h1 id="perspective">Perspective</h1>
<h2 id="computational-performance-perspective">Computational performance perspective</h2>
<p>One of important perspective of implementing machine learning library is computational performance. There are two computational performance metrics that can be used: latency and throughput at prediction time. Optimization is usually done to minimize latency and maximize throughput but it can hurt prediction accuracy.</p>
<h3 id="prediction-latency">Prediction latency</h3>
<p>Prediction latency is measured as the elapsed time necessary to make a prediction (e.g. in micro-seconds) [38]. There are four main factors that influence the prediction latecy: number of features, input data representation and sparsity, model complexity, feature extraction.
Number of features affects memory consumption, which shows number of basic operations, such as multiplications for vector-matrix products. Matrix of M instances with N features will result O(NxM) space complexity.
In sparse input data representation, optimization using sparse format is essential to make performance better by not storing zeros which will lead to less memory consumption. As a rule of thumb you can consider that if the sparsity ratio is greater than 90% you can probably benefit from sparse formats [38].
Model complexity will lead to more predictive power and latency. Increasing predictive power is usually interesting, but for many applications we would better not increase prediction latency too much [38].
In many real world applications the feature extraction process (i.e. turning raw data like database rows or network packets into numpy arrays) governs the overall prediction time [38]. In many cases it is thus recommended to carefully time and profile your feature extraction code as it may be a good place to start optimizing when your overall latency is too slow for your application.</p>
<h3 id="prediction-throughput">Prediction throughput</h3>
<p>Prediction throughput is defined as the number of predictions the software can deliver in a given amount of time (e.g. in predictions per second) [38]. There are several ways to improve prediction throughput, such as spawn additional instances that share same model or add more machines to spread the load.</p>
<h1 id="software-debts">Software Debts</h1>
<p>There is an increasing amount of danger of not being able to add or enhance features as the project evolves. Technical debt needs to be looked at from the start of the project because small issues can lead to bigger problems later in the development of the project.</p>
<h2 id="technical-debt">Technical debt</h2>
<p>Although, there is extensive maintenance from the beginning of the project, technical debt is still evident in the project as we are going to point out in this section. Several aspects regarding technical debt will be covered.</p>
<h3 id="solid-principles">Solid principles</h3>
<p>For identifying technical debt, a good method is to look into the SOLID principles and how these are handled for scikit-learn. These principles could give an indication of arguably bad design being used, preventing or making it more difficult to make changes in the future.</p>
<h4 id="single-responsibility-principle">Single Responsibility Principle</h4>
<p>The Single Responsibility Principle states that a class should only have a single responsibility [27].</p>
<p>Whether this principle is broken in a widespread manner is difficult to say for scikit-learn due to the size of its code base. In general, all classes such as neural networks [51], kdtree [53] and label propagation [20] model a certain specific theory, and therefore tend to model this in a rather direct way.</p>
<p>This is a fine way to separate concerns, given one important assumption: The theory either does not change or a change in theory fundamentally requires a new class. For instance, a new theory is not an update of the old, therefore requires a new class.</p>
<pre><code class="lang-python"><span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">email</span>:</span>
    function setSender(email_as_string)
</code></pre>
<p><em>Figure 5: A bad implementation of single responsibility principle.</em></p>
<pre><code class="lang-python"><span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">email_address</span>:</span>
   function getAddress():
       <span class="hljs-keyword">return</span> this.address

<span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">email</span>:</span>
    function setSender(email_as_email_address):
        this.address = email_as_email_addres.getAddress()
</code></pre>
<p><em>Figure 6: A proper separation of concerns, this allows for example checking of format of an email in the constructor of the email_address class.</em></p>
<p>This is also mostly true for places where modularization breaks down or other problems exist, as will be addressed further in this chapter, such as utils. the mocking file [19] is responsible for mocking functionality, and arrayfuncs [18] provides functions for arrays.</p>
<p>There are probably still splits that are possible, but the division of responsibilities makes a lot of sense for what scikit-learn is trying to do.</p>
<h3 id="openclosed-principle">Open/Closed Principle</h3>
<p>The Open/Closed Principle states that software entities should be open for extension, but closed for modification.</p>
<pre><code class="lang-python"><span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">drawer</span>:</span>
    drawCircle():
    drawSquare():
    drawShape(x):
        <span class="hljs-keyword">if</span>(isinstance(x, circle):
            drawCircle()
        <span class="hljs-keyword">else</span>:
            drawSquare()

<span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">shape</span>:</span>

<span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">circle</span><span class="hljs-params">(shape)</span>:</span>

<span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">square</span><span class="hljs-params">(shape)</span>:</span>
</code></pre>
<p><em>Figure 7: Example of bad application of the open/closed principle, drawer needs knowledge about every extending class. requiring changes for each new class implementing shape.</em></p>
<pre><code class="lang-python"><span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">drawer</span>:</span>
    drawShape(x):
        x.draw()

<span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">shape</span>:</span>
    draw(): <span class="hljs-comment"># python does not have interfaces, but duck-typing.</span>

<span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">circle</span><span class="hljs-params">(shape)</span>:</span>
    draw():

<span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">square</span><span class="hljs-params">(shape)</span>:</span>
    draw():
</code></pre>
<p>Figure <em>8: A good implementation of the open/closed principle, drawer can simply take any new implementation of shape as well.</em></p>
<p>For implementations that have similar roots (such as neural networks [15]) a parent class will be made defining basic behaviour that does not depend on specifics of the child to be useful. This closes the parent class, but keeps the child class open for extension</p>
<h4 id="liskov-substitution-principle">Liskov Substitution Principle</h4>
<p>The Liskov Substitution Principle states that if S is a subtype of T then objects of type T may be replaced with objects of type S</p>
<pre><code class="lang-python"><span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">rectangle</span>:</span>
    setHeight(self,x):
        self.height = x

    setWidth(self, x):
        self.width = x

    getArea(self):
        <span class="hljs-keyword">return</span> self.width*self.height

<span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">square</span><span class="hljs-params">(rectangle)</span>:</span>
    setHeight(self,x):
        self.height = x
        self.width = x

    setWidth(self,x):
        self.height = x
        self.width = x

s = square()
s.setWidth(<span class="hljs-number">10</span>)
s.setHeight(<span class="hljs-number">5</span>)
print(s.getArea) <span class="hljs-comment"># no valid expectation on area (either 25 from square, or 50 from rectangle)</span>
</code></pre>
<p><em>Figure 9: Bad implementation of Liskov substitution principle, square has additional restrictions on it that rectangle does not have, leading to weird situations when functions for rectangles get called on it.</em></p>
<p>This principle does not seem to be violated in scikit-learn. Lower classes do not tend to introduce additional restrictions and can replace their parent class where necessary. This is also because scikit-learn tends to implement proper duck-typing, which -when done properly- ensures the Liskov Substitution Principle.</p>
<p>Duck-typing says that the suitability of a certain class S to replace T is that it should offer at least the same functionality as T. i.e. &quot;If it walks like a duck and quacks like a duck, it must be a duck.&quot; [16].</p>
<h4 id="interface-segregation-principle">Interface Segregation principle</h4>
<p>The Interface Segregation Principle states that no client should be forced to depend on methods it does not use.</p>
<p>This is again true because scikit-learn applies good duck typing. A duck does not talk, therefore its parent classes will not demand this of it.</p>
<p>This could also be explained as being caused by using python, as it does not support interfaces, fundamentally ignoring this principle. And therefore any program written in python is incapable of applying it [28].</p>
<h4 id="dependency-inversion-principle">Dependency Inversion Principle</h4>
<p>Dependency Inversion Principle states that high level modules should not depend on low level modules, but instead both should depend on abstractions. Furthermore, abstractions should not depend on details but details on abstractions.</p>
<p>This does happen on occasion inside scikit-learn for example multilayer perceptron[17] creates a LabelBinarizer, meaning it is now dependent on how LabelBinarizer works for its own behaviour. Instead of passing a LabelBinarizer through the constructor.</p>
<pre><code class="lang-py"><span class="hljs-keyword">if</span> <span class="hljs-keyword">not</span> incremental:
            self._label_binarizer = LabelBinarizer()
            self._label_binarizer.fit(y)
            self.classes_ = self._label_binarizer.classes_
</code></pre>
<p><em>Figure 10: Example of breaking Dependency Inversion Principle.</em></p>
<p>Reducing these kinds of instances could reduce the amount of technical debt, because it would be easier, and more explicit, when the class is passed through the constructor to change the specific class delivering the functionality in case a NewBetterLabelBinarizer class is required.</p>
<h3 id="debt-from-structure">Debt From Structure</h3>
<p>Scikit-learn has several different ways of formatting its code. It uses both the classes and their respective imports [17].</p>
<pre><code class="lang-python"># filename: duck.py
class duck
    def quack():
        return &apos;Quack!&apos;
</code></pre>
<p><em>Figure 11: Example of new importing.</em></p>
<pre><code class="lang-python"><span class="hljs-keyword">from</span> duck <span class="hljs-keyword">import</span> duck
whatDoesTheDuckSay = duck().quack()
</code></pre>
<p><em>Figure 12: Another example of new importing.</em></p>
<p>and defs with file based imports</p>
<pre><code class="lang-python"><span class="hljs-comment"># filename: duck.py</span>
<span class="hljs-function"><span class="hljs-keyword">def</span> <span class="hljs-title">quack</span>:</span>
    <span class="hljs-keyword">return</span> <span class="hljs-string">&apos;Quack!&apos;</span>
</code></pre>
<p><em>Figure 13: Example of old importing.</em></p>
<pre><code class="lang-python"><span class="hljs-keyword">import</span> duck
duck.quack()
</code></pre>
<p><em>Figure 14: Another example of old importing.</em></p>
<p>This means different files function differently for the same type of functionality, possibly restricting flexibility and this could therefore be seen as technical debt.</p>
<h3 id="debt-from-modularization">Debt From Modularization</h3>
<p>For the most part scikit-learn has a logical document structure. An important exception to this is the utils folder, which seems to contain a lot of very different modules such as math [21], testing [22] and array functions [23]. This might make it more difficult to find specific functionality, increasing technical debt.</p>
<h3 id="discussion-of-technical-debt---in-the-source-code">Discussion of Technical Debt - In the Source Code</h3>
<p>This section will look at how the contributors of Scikit-learn discuss technical debt. In some projects (maybe even most) occasionally technical debt is being discussed in the source code itself. This is often in the form of <em>TODO</em> or <em>FIXME</em> comments. In general, we find this a bad way of discussing technical debt as it is often forgotten about. However, in Scikit-learn it still happens occasionally.</p>
<p>We used grep to look for any <em>TODO</em> or <em>FIXME</em> comments in the whole Scikit-learn repository (this includes the documentation). The following commands were used in the root directory of the scikit-learn repository:</p>
<blockquote>
<p>grep -r  &quot;FIXME&quot; . --ignore-case<br>grep -r  &quot;TODO&quot; . --ignore-case</p>
</blockquote>
<p><em>Figure 15: Grep commands.</em></p>
<p>We found 76 occurrences of <em>TODO</em> comments, spread out over 48 files. Four of these files are documentation files, but these have two purposes. Sometimes a <em>TODO</em> is added in the documentation to indicate that a feature for example should still be implemented in the code, other times it actually means that something is missing in the documentation. We found 20 occurrences of <em>FIXME</em> comments, spread out over 16 files, 2 of which are documentation files and 4 test files. The fact that there are both <em>FIXME</em> and <em>TODO</em> comments in the testing and documentation code indicates some form of testing and documentation debt present in the project.</p>
<p>The following picture sums up how well this method works for discussing technical debt:</p>
<p><img src="images-team-scikit-learn/FixMeSoon.PNG" alt=""><br><em>Figure 16: &#x201C;FIXME&#x201D; comment added long ago, which is still present in the code now.</em></p>
<h3 id="testing-debt">Testing debt</h3>
<h4 id="code-testing">Code Testing</h4>
<p>The code coverage for scikit-learn on 16 March was 94.76% which is very good. We can see a breakdown of the code coverage for different modules in the barplot in Figure 17. The full information can be found here [24]. Despite having modules where the code coverage is low(e.g. datasets) overall the system is tested very well.</p>
<p>The major contributors of scikit-learn have agreed upon approximately 90% coverage. Also, the project is well tested by implementing unit-testing. Unit testing as the developers in scikit-learn mention is &quot;a corner-stone of the scikit-learn development process&quot; [2].</p>
<p>We have also made a barplot where it is easier to see the different coverage scores for the different modules. We can identify the big difference of code coverage between the datasets module and the other modules.</p>
<p><img src="images-team-scikit-learn/codecovw.jpg" alt=""></p>
<p><em>Figure 17: Code coverage about different modules ordered.</em></p>
<p>In addition, the project of scikit-learn relies on integration testing services like Travis CI [14], circleci [12] and AppVeyor [13]. It is a common procedure of the scikit-learn testing procedure to report the results of tests on continuous integration (CI) platforms. We can see an example of successful and unsuccessful testing on a PR in the figure below. All PRs need to pass all five check tests from different CI platforms before it gets merged: ci/circleci, codecov/patch, codecov/project, continuous-integration/appveyor/pr, and continuous-integration/travis-ci/pr. Thus, all changes in scikit-learn are well-tested and it reduces the risk. Also, it helps the reviewers to make decisions about which PR should be merged and to give constructive advice to the authors in order to fix PR.</p>
<p><img src="images-team-scikit-learn/integration.png" alt=""><br><em>Figure 18: Tests on different CI platforms.</em></p>
<p><strong>Testing results on CI platforms.</strong></p>
<p>As is mentioned above, unit testing is also performed with the nose package [15]. The tests are functions with appropriate names, located in tests subdirectories. The tests check the validity of the algorithms and the different options of the code. The full scikit-learn tests can be run using &apos;make&apos; in the root folder. Alternatively, running &apos;nosetests&apos; in a folder will run all the tests of the corresponding subpackages. The code coverage of new features are expected to be at least around 90%.</p>
<h4 id="proposal-for-removing-debt">Proposal for Removing Debt</h4>
<p>It is dangerous to have this form of technical debt in a place where contributors might be less aware of it. To remove this form of technical debt we would firstly propose to keep track of it in a better way, so that the advantage of being an open source project can be utilized better to get rid of it. In issue 8581 [11] we proposed the following work-flow to remove it:</p>
<ol>
<li>Create an issue on GitHub for each file still containing TODOs/FIXMEs.</li>
<li>File by file create issues for each TODO/FIXME comment.</li>
<li>Either remove the comments in a new PR linking the newly created issues or if it is preferable to keep the comments in the code as well, instead of removing the comment add a link to the issue in the comment.</li>
</ol>
<p>This issue attracted the attention of a couple developers in scikit-learn. They highlighted that this is tedious work and it is more preferable to focus on existing issues. Also, these TODO/FIXME comments require expertise not currently available in the project.</p>
<h1 id="conclusion">Conclusion</h1>
<p>In the beginning of the chapter the different stakeholders of scikit-learn were introduced. Initially, the categories as defined by Rozanski &amp; Woods were used, but using four main categories of stakeholders were more applicable to scikit-learn, which are contributors, users, funders and competitors. This section was followed by the views sections where three different aspects of the architecture were discussed through the use of the context view, the Development View and Deployment View. The Development View consisted of the Module Structure Model. The Module Structure Model identified the structure of the code in terms of how the code was grouped into modules. Finally, the Deployment View looked at the system in operation. It identified dependencies required to run and install scikit-learn, the environment needed to run it in and it also identified the need for specialist knowledge to utilize scikit-learn to it&apos;s fullest. The perspective on computational performance is the additional section to explore more about performance of scikit-learn as machine learning library. The last section looked at two main aspects of software debt, technical and testing debt. It started off with a section about looking at technical debt through the SOLID principles. This concluded that the SOLID principles are not fully applicable to this project due to using Python.  In this section, we also found that one prominent form of technical debt were <em>TODO</em> and <em>FIXME</em> comments. To mitigate this debt, we proposed a work-flow for adding these issues to GitHub one by one so that they could be tracked and solved more easily. Through our interactions with the scikit-learn contributors, we learned that they struggle with having enough expert knowledge to deal with these issues. When looking at the testing debt, it was evident that scikit-learn has high test coverage (94.76%) and that the contributors put in a lot of effort to keep this coverage high when reviewing pull requests. High test coverage really is a corner-stone of their development process. This is also noticeable when submitting a pull request since various continuous integration tools need to pass before a pull request can be approved.</p>
<h2 id="references">References</h2>
<p>[1] <a href="http://scikit-learn.org/stable/about.html#people" target="_blank">http://scikit-learn.org/stable/about.html#people</a></p>
<p>[2] Rozanski, _Nick, and Eoin Woods. Software Systems Architecture: Working with Stakeholders Using Viewpoints and Perspectives._ Upper Saddle River, N.J.: Addison-Wesley, &#xA9;2012.</p>
<p>[3] <a href="http://scikit-learn.org/stable/developers/contributing.html" target="_blank">http://scikit-learn.org/stable/developers/contributing.html</a></p>
<p>[4] <a href="http://stackoverflow.com/tags/scikit-learn/topusers" target="_blank">http://stackoverflow.com/tags/scikit-learn/topusers</a></p>
<p>[5] <a href="https://github.com/orgs/scikit-learn/people" target="_blank">https://github.com/orgs/scikit-learn/people</a></p>
<p>[6] <a href="https://github.com/scikit-learn/scikit-learn/pull/8253" target="_blank">https://github.com/scikit-learn/scikit-learn/pull/8253</a></p>
<p>[7] <a href="https://github.com/scikit-learn/scikit-learn/pull/8280" target="_blank">https://github.com/scikit-learn/scikit-learn/pull/8280</a></p>
<p>[8] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/CONTRIBUTING.md#user-content-pull-request-checklist" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/CONTRIBUTING.md#user-content-pull-request-checklist</a></p>
<p>[9] <a href="https://github.com/scikit-learn/scikit-learn/tree/master/sklearn" target="_blank">https://github.com/scikit-learn/scikit-learn/tree/master/sklearn</a></p>
<p>[10] <a href="http://scikit-learn.org/stable/install.html" target="_blank">http://scikit-learn.org/stable/install.html</a></p>
<p>[11] <a href="https://github.com/scikit-learn/scikit-learn/issues/8581" target="_blank">https://github.com/scikit-learn/scikit-learn/issues/8581</a></p>
<p>[12] <a href="https://circleci.com/" target="_blank">https://circleci.com/</a></p>
<p>[13] <a href="https://www.appveyor.com/" target="_blank">https://www.appveyor.com/</a></p>
<p>[14] <a href="https://travis-ci.org/" target="_blank">https://travis-ci.org/</a></p>
<p>[15] <a href="http://nose.readthedocs.io/en/latest/" target="_blank">http://nose.readthedocs.io/en/latest/</a></p>
<p>[16] <a href="http://www.dictionary.com/browse/duck-typing" target="_blank">http://www.dictionary.com/browse/duck-typing</a></p>
<p>[17] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/neural_network/multilayer_perceptron.py" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/neural_network/multilayer_perceptron.py</a></p>
<p>[18] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/utils/extmath.py" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/utils/extmath.py</a></p>
<p>[19] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/neighbors/kd_tree.pyx" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/neighbors/kd_tree.pyx</a></p>
<p>[20] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/semi_supervised/label_propagation.py" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/semi_supervised/label_propagation.py</a></p>
<p>[21] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/utils/extmath.py" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/utils/extmath.py</a></p>
<p>[22] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/utils/testing.py" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/utils/testing.py</a></p>
<p>[23] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/utils/arrayfuncs.pyx" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/sklearn/utils/arrayfuncs.pyx</a></p>
<p>[24] <a href="https://codecov.io/gh/scikit-learn/scikit-learn/tree/603ff1a61d2d3d08624e18b32d05c177711d7299" target="_blank">https://codecov.io/gh/scikit-learn/scikit-learn/tree/603ff1a61d2d3d08624e18b32d05c177711d7299</a></p>
<p>[25] <a href="https://turi.com" target="_blank">https://turi.com</a></p>
<p>[26] <a href="https://root.cern.ch" target="_blank">https://root.cern.ch</a></p>
<p>[27] [<a href="http://www.oodesign.com/single-responsibility-principle.html" target="_blank">http://www.oodesign.com/single-responsibility-principle.html</a></p>
<p>[28] [<a href="https://www.python.org/dev/peps/pep-0245/" target="_blank">https://www.python.org/dev/peps/pep-0245/</a></p>
<p>[29] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/doc/data_transforms.rst" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/doc/data_transforms.rst</a></p>
<p>[30] <a href="https://github.com/scikit-learn/scikit-learn/tree/master/doc/datasets" target="_blank">https://github.com/scikit-learn/scikit-learn/tree/master/doc/datasets</a></p>
<p>[31] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/doc/model_selection.rst" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/doc/model_selection.rst</a></p>
<p>[32] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/doc/supervised_learning.rst" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/doc/supervised_learning.rst</a></p>
<p>[33] <a href="https://github.com/scikit-learn/scikit-learn/blob/master/doc/unsupervised_learning.rst" target="_blank">https://github.com/scikit-learn/scikit-learn/blob/master/doc/unsupervised_learning.rst</a></p>
<p>[34] <a href="https://www.python.org" target="_blank">https://www.python.org</a></p>
<p>[35] <a href="http://www.numpy.org" target="_blank">http://www.numpy.org</a></p>
<p>[36] <a href="https://www.scipy.org" target="_blank">https://www.scipy.org</a></p>
<p>[37] <a href="https://github.com/scikit-learn/scikit-learn/tree/master/build_tools" target="_blank">https://github.com/scikit-learn/scikit-learn/tree/master/build_tools</a></p>
<p>[38] <a href="http://scikit-learn.org/stable/modules/computational_performance.html" target="_blank">http://scikit-learn.org/stable/modules/computational_performance.html</a></p>
