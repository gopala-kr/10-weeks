<h1 id="tensorflow---open-source-library-for-machine-learning-applications">TensorFlow&#x2122; - Open Source Library for Machine Learning Applications</h1>
<p align="center">
  <img src="https://delftswa.gitbooks.io/desosa2016/content/tensorflow/images-team-tensorflow/TF.png" width="300">
</p>

<p align="center">
By: Carmen Chan-Zheng, Ilse Verdiesen, Johan Carvajal-Godinez and Pranav Sailesh Mani <br>
Software Architecture, Delft University of Technology
</p>

<h2 id="abstract">Abstract</h2>
<p>TensorFlow&#x2122; is an open source software library developed by the Google Brain team for the purpose of conducting machine learning and deep neural networks research. The library performs numerical computation by using data flow graphs, where the nodes in the graph represent mathematical operations and the graph edges represent the multidimensional data arrays (tensors) which communicate between the nodes. The API has been used in the fields of medicine, translation services, and the analysis of financial markets. This chapter first describes TensorFlow&#x2122; by its features and stakeholders, secondly the architecture is analyzed by means of the context, development, and deployment view, and finally a conclusion is provided.</p>
<h2 id="table-of-contents">Table of Contents</h2>
<ol>
<li><a href="#int">Introduction</a><br></li>
<li><a href="#wit">What is TensorFlow?</a><br>
2.1. <a href="#fea">Features</a><br>
2.2. <a href="#sth">Stakeholders</a><br></li>
<li><a href="#arc">Architecture</a><br>
3.1 <a href="#vie">Views</a><br><ul>
<li>3.1.1 <a href="#contv">Context view</a><br></li>
<li>3.1.2 <a href="#devv">Development view</a><br></li>
<li>3.1.3 <a href="#depv">Deployment view</a><br>
3.2 <a href="#per">Perspectives</a><br></li>
<li>3.2.1 <a href="#evp">Evolution perspective</a><br></li>
<li>3.2.2 <a href="#vap">Variability perspective</a><br></li>
<li>3.2.3 <a href="#pep">Performance perspective</a><br></li>
</ul>
</li>
<li><a href="#con">Conclusion</a><br></li>
<li><a href="#ref">References</a><br></li>
</ol>
<h2 id="1-introduction"><div name="int">1. Introduction</div></h2>
<p>Machine learning is an artificial intelligence enabler that provides the foundations for extending the computer capabilities closer to human brain. To get there, new tools need to be developed, especially new models of computation that support faster application development cycle. This is not an easy task, which requires the help from the crowd sourcing community. 
TensorFlow&#x2122; is an extended version of DistBelief, a system developed for internal use at Google. DistBelief was internally used by Google employees to build large neural networks and scale training to thousands of cores in Google&apos;s datacenters. Some of the applications of Distbelief were image recognition, speech recognition, Google search etc. However, DistBelief had its own disadvantages. It was specifically designed for neural networks and was difficult to configure. It was also tightly coupled to Google&apos;s internal infrastructure. In order to overcome this problem, Google developed TensorFlow&#x2122; whose main purpose is to simplify real world use of machine learning systems. It is only recently (From December 18th 2015) that the TensorFlow&#x2122; team has started accepting contributions through GitHub before they were using the Gerrit system for collaborating. The history of developments starts from TensorFlow&#x2122; v0.5.0 till the current version 0.7.0.
This chapter is intended to explore three key elements: (1) What is TensorFlow&#x2122;, (2) its main architectures views, and (3) its more relevant perspectives. Following this purpose, this chapter has been organized to explore the stakeholders, the context view, the development view, the deployment view, the evolution-, the variability-, and the performance perspectives.</p>
<h2 id="2-what-is-tensorflow"><div name="wit">2. What is TensorFlow&#x2122;?</div></h2>
<p>TensorFlow&#x2122; is an open source library for developing machine learning applications. These applications are implemented using graphs to organize the flow of operations and tensors for representing the data. It offers an application programming interface (API) in Python, as well as a lower level set of functions implemented using C++. It provides a set of features to enable faster prototyping and implementation of machine learning models and applications for highly heterogeneous computing platforms.</p>
<h4 id="21-features"><div name="fea">2.1 Features</div></h4>
<p><a href="https://www.tensorflow.org/" target="_blank">Tensorflow&#x2122;&apos;s webpage</a> enlists the system&apos;s most important features, which are described as:</p>
<ol>
<li><strong>Deep Flexibility</strong>: Provides tools to assemble graphs for expressing diverse machine learning models. New operations can be written in Python and low-level data operators are implemented using in C++.</li>
<li><strong>True Portability</strong>: Runs on CPUs, GPUs, desktop, server, or mobile computing platforms. That make it very suitable in several fields of application, for instance medical, finance, consumer electronic, etc. </li>
<li><strong>Connect Research and Production</strong>: TensorFlow&#x2122; allows industrial researchers a faster product prototyping. It also provides academic researchers with a development framework and a community to discuss and support novel applications. </li>
<li><strong>Auto-Differentiation</strong>: This is a key feature within the machine learning community. Gradient based machine learning algorithms benefit from automatic differentiation capabilities. As a TensorFlow&#x2122; user, you define the computational architecture for your predictive model, combine it with your objective function, and just add data to test your machine learning model.</li>
<li><strong>Language Options</strong>: Python and C++. However, currently other APIs are being developed, for example a Ruby API.</li>
<li><strong>Maximize Performance</strong>: Allows you to make the most of your installed hardware. Freely assign compute elements of your TensorFlow&#x2122; graph to different devices, and let TensorFlow&#x2122; handle the copies.</li>
</ol>
<h3 id="22-stakeholders"><div name="sth">2.2 Stakeholders</div></h3>
<p>TensorFlow&#x2122; is a very active community consisting of a very diverse group of Developers, Integrators, Researchers, Students, Architects, Software Engineers, Companies (i.e Engineers, managers, CEO, etc.), Consultants and Hardware Manufacturers (NVIDIA, ARM, Intel) (figure 1). Each group is assigned to each type of stakeholders according to the classification proposed in Mitchell et al.[<a href="#mi">1</a>].</p>
<table>
<thead>
<tr>
<th>Type of Stakeholder</th>
<th>Description[<a href="#mi">1</a>]</th>
<th>Application to TensorFlow&#x2122;</th>
</tr>
</thead>
<tbody>
<tr>
<td>Dormant Stakeholder (1)</td>
<td>The relevant attribute of a dormant stakeholder is power. Dormant  stakeholders possess power to impose their will on a firm, but by not having a legitimate relationship or an urgent claim, their power remains unused.</td>
<td>Integrators</td>
</tr>
<tr>
<td>Discretionary Stakeholder (2)</td>
<td>Discretionary stakeholders possess the attribute of legitimacy, but they have no power to influence the firm and no urgent claims.</td>
<td>Researchers</td>
</tr>
<tr>
<td>Demanding Stakeholder (3)</td>
<td>Where the sole relevant attribute of the stakeholder-manager relationship is urgency, the stakeholder is described as &quot;demanding.&quot; Demanding stakeholders, those with urgent claims but having neither power nor legitimacy, are the &quot;mosquitoes buzzing in the ears&quot; of managers.</td>
<td>Students, Consultants and Companies</td>
</tr>
<tr>
<td>Dominant stakeholders  (4)</td>
<td>In the situation where stakeholders are both powerful and legitimate, their influence in the firm is assured, since by possessing power with legitimacy, they form the &quot;dominant coalition&quot; in the enterprise.</td>
<td>Hardware Manufacturers</td>
</tr>
<tr>
<td>Dangerous stakeholders  (5)</td>
<td>We suggest that where urgency and power characterize a  stakeholder who lacks legitimacy, that stakeholder will be coercive and possibly violent, making the stakeholder &quot;dangerous,&quot; literally, to the firm.</td>
<td>Researchers using multiple libraries, for instance Microsoft <a href="https://github.com/Microsoft/CNTK" target="_blank">CNTK</a></td>
</tr>
<tr>
<td>Dependent Stakeholder  (6)</td>
<td>We characterize stakeholders who lack power but who have urgent legitimate claims as &quot;dependent,&quot; because these stakeholders depend upon others (other  stakeholders or the firm&apos;s managers) for the power necessary to carry out their will.</td>
<td>Architects and Software Engineers</td>
</tr>
<tr>
<td>Definitive Stakeholder  (7)</td>
<td>By definition, a stakeholder exhibiting both power and legitimacy already will be a member of a firm&apos;s dominant coalition. When such a stakeholder&apos;s claim is urgent, managers have a clear and immediate mandate to attend to and give priority to that stakeholder&apos;s claim.</td>
<td>Developers</td>
</tr>
</tbody>
</table>
<p>The following figure plots each of the stakeholder according to its type:</p>
<p align="center">
  <img src="https://delftswa.gitbooks.io/desosa2016/content/tensorflow/images-team-tensorflow/Stakeholder.model4.jpg" width="500">
</p>

<pre><code>                               Figure 1. Stakeholder groups for TensorFlow
</code></pre><h2 id="3-architecture"><div name="arc">3. Architecture</div></h2>
<p>The architecture of TensorFlow&#x2122; is described based on (1)<em>views</em>, which according to Rozanski and Woods[<a href="#rw">2</a>] consists of elements or aspects of the architecture that are relevant to the concerns of the stakeholders, and (2)<em>perspectives</em> which are a set of related quality properties across a number of the system&#x2019;s architectural views that require consideration. In this paragraph first the context-, development- and deployment view are described, followed by the evolution-, variability- and performance perspective. </p>
<h3 id="31-views"><div name="vie">3.1 Views</div></h3>
<p>In this paragraph the context view provides insight in the relationship between TensorFlow&#x2122; and its environment, the development view gives a description of models that are of concern of the stakeholders, and the deployment view shows the environment into which the system is deployed and the dependencies that the system has on its elements.</p>
<h4 id="311-context-view"><div name="contv">3.1.1 Context view</div></h4>
<p>The purpose of this section is to elaborate on the relationships, dependencies and interactions between TensorFlow&#x2122; and its environment. The main goal is discovering how these elements affect TensorFlow&#x2019;s&#x2122; architecture. It will help to understand TensorFlow&#x2122; boundaries, as well as, its scope.</p>
<h5 id="3111-scope-definition">3.1.1.1 Scope definition</h5>
<p>For this chapter, the most relevant elements surrounding TensorFlow&#x2122;  have been considered. There were identified 5 key aspects that enables the operation of the library. These are: stakeholder community, repository management, execution platforms, visualization tools, and Library dependencies. These elements are described in more detail in the following subsections.    </p>
<h6 id="3112-stakeholder-community">3.1.1.2 Stakeholder community</h6>
<p>In the previous section the stakeholder community was described in detail. From this analysis, four key players were identified: developers, researchers, integrators and companies. 
Developers are those who enable new models, operations and tools within the API. They have a strong background in computer science. On the other hand, researchers use the latest version of TensorFlow&#x2122;&apos;s implementation to develop applications and study machine learning algorithms. Integrators are in charge to make decisions on whether or not a contribution can be integrated to the code base. These contributions are being proposed mainly by developers and researchers. Finally, the companies explore the results of researchers and try to enable new features on their products, taking advantage of their improvements. All of these four actor define the contributor community of TensorFlow&#x2122;, which is supported by Google, in order to provide resources, but to gain expertise that could be used in future products.</p>
<h6 id="3113-repository-management">3.1.1.3 Repository Management</h6>
<p>TensorFlow&#x2122;  is hosted at GitHub under the Google&apos;s support. As mentioned previously, integrators are in charge of analyzing pull requests and determining if these can be merged. TensorFlow&#x2122; uses Jenkins as a continuous integration platform. Also, Docker is used to support the their delivery process.</p>
<h6 id="3114-execution-platforms">3.1.1.4 Execution Platforms</h6>
<p>The execution environment surrounding TensorFlow&#x2122; is very heterogeneous. The Library supports ports for CPU, GPU and mobile platforms. It makes the library suitable for many application fields, but increases the implementation complexity. For example, for GPU implementation, currently only CUDA is supported, and for mobile platforms only Android. Also, there is a price to be paid when offering flexibility, which is performance. Later in this chapter we will see an analysis of this aspect.</p>
<h6 id="3115-visualization-tools">3.1.1.5 Visualization tools</h6>
<p>Visualization is a key element for researchers. It allows to compare, but also to play with parameters to optimize the algorithm performance. Tensorboard is a module provided for that purpose. It takes the results from execution and enables the user to display, and compare different runs.</p>
<h6 id="3116-dependencies">3.1.1.6 Dependencies</h6>
<p>As many other libraries, TensorFlow&#x2122; requires features from other systems, not just for maintaining the repository, but for enabling new functionalities. The main dependencies are the NVIDIA driver support for CUDA, the Python and C++ language support. There are several other dependencies that would be detailed in the development view.</p>
<p>In figure 2 the relation between the surrounding elements and the TensorFlow&#x2122; library are illustrated.</p>
<p align="center">
  <img src="https://delftswa.gitbooks.io/desosa2016/content/tensorflow/images-team-tensorflow/Contextview.png" width="500">
</p>

<pre><code>                          Figure 2 Context diagram for TensorFlow&#x2122; 
</code></pre><h4 id="312-development-view"><div name="devv">3.1.2 Development view</div></h4>
<p>This view addresses the specific concerns of the software developers and testers[<a href="#rw">2</a>]. This section contains the description of three different models: Codeline Models, Module Structure Model, and Common Design Models.</p>
<h5 id="3121-codeline-models">3.1.2.1 Codeline Models</h5>
<p>This section explores the code structure of TensorFlow&#x2122;  with the purpose of getting a better understanding on how the project is organized. </p>
<h6 id="31211-source-code-hierarchy">3.1.2.1.1 Source code hierarchy</h6>
<p>TensorFlow&#x2122; &apos;s root directory at GitHub is organized in five main subdirectories: google, tensorflow, third-party, tools and util/python. Additionally, the root directory provides information on how to contribute to the project, and other relevant documents. In figure 3, the source code hierarchy is illustrated.</p>
<p align="center">
  <img src="https://delftswa.gitbooks.io/desosa2016/content/tensorflow/images-team-tensorflow/TensorFlowTree.png">
</p>


<pre><code>                             Figure 3. TensorFlow&#x2122; source code organization
</code></pre><p>Following subsections will elaborate on the purpose of the five main subdirectories shown in figure 3:</p>
<h6 id="31212-google">3.1.2.1.2 Google</h6>
<p>This subdirectory provides an instance of &#xA8;Protocol Buffers&#xA8; library, a Google&apos;s language and platform neutral, mechanism for serializing structured data. That is required since TensorFlow&#x2122; supports implementations in C++ using a single Python API, which requires a common data interface. Also, it enables support to implementation with other programming languages, for instance, Java, Ruby and many others.</p>
<h6 id="31213-tensorflow">3.1.2.1.3 Tensorflow</h6>
<p>This is the heart of the library&apos;s implementation. It contains a set of subdirectories intended to:</p>
<ul>
<li>cc: declaring function wrappers for C++ code.</li>
<li>contrib: containing features and contributions that eventually should get merged into tensorflow/core. </li>
<li>core: providing an implementation for the main functionalities of TensorFlow&#x2122;. </li>
<li>examples: containing reference applications for contributors. </li>
<li>g3docs: contains documentation for Python and C++ APIs. </li>
<li>models: containing models for specific application implementation.</li>
<li>python: containing the implementation of Python to support the application development API. </li>
<li>stream-executor: providing an interface with hardware accelerators (GPUs).</li>
<li>tensorboard: containing a suite of web applications for inspecting and understanding of TensorFlow&#x2122; runs and graphs.</li>
<li>tools: providing a proper execution environment for the library.</li>
<li>user_ops: providing wrappers for customized user functions (i.e. ackermann).</li>
</ul>
<h6 id="31214-third-party">3.1.2.1.4 Third-party</h6>
<p>This directory provides instances of useful third-party libraries to help the TensorFlow&#x2122; application developers. Three main libraries are identified here: </p>
<ul>
<li><a href="http://eigen.tuxfamily.org/index.php?title=3.0" target="_blank">Eigen3</a>: a C++ template library for linear algebra operations.</li>
<li>gpus: a crosstool wrapper for compiling CUDA programs.</li>
<li>[numpy] (<a href="http://www.numpy.org/" target="_blank">http://www.numpy.org/</a>): a package for scientific computing with Python.</li>
</ul>
<h6 id="31215-tools">3.1.2.1.5 Tools</h6>
<p>This provides a place to put a script to indicate Bazel which version of Python is being used.</p>
<h6 id="31216-util-python">3.1.2.1.6 Util/ python</h6>
<p>This provides a place to put a script to generate relative paths for Python, so it works in both a local or remote repository.</p>
<h5 id="3122--module-structure-models">3.1.2.2  Module Structure Models</h5>
<p>The purpose of this section is to focus on the organization of the TensorFlow&#x2122;&apos;s repository and group the modules into layers of abstractions. </p>
<h6 id="31221-classify-the-modules">3.1.2.2.1 Classify the Modules</h6>
<p>As shown in the section &quot;Codeline Models&quot;, the TensorFlow&#x2122; GitHub Repository is organized and classified as shown in Figure 3, these can be classified in the following way:</p>
<ul>
<li>Application development modules: Python API (<em>pp</em> folder), C++ API(<em>cc</em> folder), Tensorboard, contributions (<em>contrib</em> folder), examples, tools such as Jenkins, pip and Docker (<em>tools</em> folder in root directory) and useful documentation such as: APIs documentation, tutorial, getting started example located in <em>g3docs</em> directory.</li>
<li>Framework modules: Models, user operations, then from <em>tensorflow/core</em> directory: libraries (<em>lib</em> folder), and from the <em>root</em> directory: 3rd party.</li>
<li>Platform modules: from <em>tensorflow/tensorflow</em> directory: Stream executor and the <em>_tensorflow/tensorflow/core</em> directory: kernels implementation, common_runtime, distributed_runtime, etc.</li>
</ul>
<h6 id="31222-module-dependencies">3.1.2.2.2 Module Dependencies</h6>
<p>To identify the module dependencies, each code from the application development, framework and platform modules group were analyzed. For example, the <em>function.py</em> (from the Python API of the Application development group) shows a clear dependency to the Platform modules and Framework modules. This same approach was applied for each source file from the repository and the main identified dependencies are:</p>
<ul>
<li>Application development group and Framework group share dependencies between them. </li>
<li>Application development group with Platform group.</li>
<li>Platform group and Framework group share dependencies between them.</li>
</ul>
<h6 id="31223-layering-rules">3.1.2.2.3 Layering Rules</h6>
<p>In <em>Classify the Modules</em> section, the modules have been classified into different groups. These groups can be used as the layers to organize the structure of the TensorFlow&#x2122; repository:</p>
<ol>
<li>Application Development layer: This layer contains the tools for the user to develop any TensorFlow&#x2122; application. It contains API documentations, examples, tutorials, contributions from other users, installation and distribution tools.</li>
<li>Framework layer: This layer contains the definition of the operations used for the application development, models for specific application implementation and session implementations. </li>
<li>Platform layer: This layer provides the interface with hardware (GPUs and CPUs), operation kernels, platform operations, datatype definition and execution framework.</li>
</ol>
<p>The system&apos;s layer organization is shown in the following figure:</p>
<p align="center">
  <img src="https://delftswa.gitbooks.io/desosa2016/content/tensorflow/images-team-tensorflow/Structure.png">
</p>

<pre><code>                              Figure 4. Structure model of the TensorFlow&#x2122;
</code></pre><h5 id="3123--common-design-models">3.1.2.3  Common Design Models</h5>
<p>From the structure obtained in figure 4, we started to identify modules which are common processing. </p>
<h6 id="31231-common-processing-elements">3.1.2.3.1 Common Processing elements</h6>
<p>The following elements can be identified as common processing elements:</p>
<ul>
<li>Message logging and instrumentation: For logging error messages in Python and C++ it is possible to log utilities. This controls which methods from pyglib.logging are used and a logline prefix using the google2 format is assembled.</li>
<li>Use of third-party libraries: Third-party libraries that are used are CUDA, Eigen, NumPy and protobuf. </li>
</ul>
<h4 id="313-deployment-view"><div name="depv">3.1.3 Deployment view</div></h4>
<p>According to Rozanski and Woods[<a href="#rw">2</a>], the deployment view describes the environment into which the system is deployed and the dependencies that the system has on its elements. This view encapsulates the hardware environment that a system requires, the technical environment requirements for each element, and the mapping of the software elements to the runtime environment that will execute them. The next two sections will discuss the overview of TensorFlow&#x2122; Runtime Requirements, and later, it presents two deployment view models. </p>
<h5 id="3131-overview-of-tensorflow-runtime-requirements">3.1.3.1 Overview of TensorFlow&#x2122; Runtime Requirements</h5>
<p>As discussed in the previous section, TensorFlow&#x2122; provides Python API and C++ API to the users to express a variety of algorithms, such as something as simple as math computation to a variety of machine learning models. 
In order to deploy (or distribute) the system, the TensorFlow&#x2122; team has provided four methods to install the Python API:</p>
<ol>
<li><p>Clone the files from GitHub source (For Linux 64-bit and Mac OS X 64-bit): This method might be the most tedious method since the user needs to install all dependencies separately. It requires Bazel, which is a build tool that builds code quickly and reliably. Then it requires to install all the Python dependencies, and lastly, (if needed) it requires the installation of the CUDA package. Less experienced users can follow the next three methods.</p>
</li>
<li><p>Pip install (For Linux 64-bit and Mac OS X 64-bit): pip is a package management system used to install and manage software packages written in Python. This method might upgrade previous installed Python packages.</p>
</li>
<li><p>Virtual env install (For Linux 64-bit and Mac OS X 64-bit): a tool that allows the creation of isolated Python environments. Using this, TensorFlow&#x2122; will be installed in its own directory.</p>
</li>
<li><p>Docker (For any Operating System 64-bit environment): tool which wraps up a piece of software into one container where contains everything needs to run the system. This tool allows the use of TensorFlow&#x2122; in different operating system environments.</p>
</li>
</ol>
<p>On the other hand, the C++ API deployment is only available through cloning the files from GitHub source.
Without regard of which Operating System is currently been used, the system needs Third-party software requirements, such as Python 2.7 or Python 3.3+ installed in the system. Also, the GPU version only can be run in Linux system and it requires the installation of Cuda Toolkit (at least version 7.0) and cuDNN (at least version v2).</p>
<p>Lastly, as for the hardware requirement, the TensorFlow&#x2122; team has not specified the minimum hardware requirements for running its architecture. However, since it uses the CUDA toolkit, we can assume that this is only intended for NVIDIA&apos;s GPU. Beside this assumption, the developer team only mentions that it will run in a conventional desktop CPU and optionally in GPU (in TensorFlow&#x2122; terminology CPU and GPU are called as devices). It can be deployed to a single device environment, multiple device environment (several devices within the same machine) or distributed environment (devices are distributed in several machines). However, there are examples that a written application using the Python API has been successfully deployed to an Android device by using Bazel, Android NDK and Android SDK (<a href="https://github.com/tensorflow/tensorflow/tree/master/tensorflow/examples/android" target="_blank">Click here for further information</a>).</p>
<h5 id="3132-deployment-view-models">3.1.3.2 Deployment View Models</h5>
<p>According to Rozanski and Woods[<a href="#rw">2</a>], there are three models to describe the architecture of TensorFlow&#x2122; from the deployment view:</p>
<ul>
<li>Runtime Platform Models</li>
<li>Network Models</li>
<li>Technology Dependency Models</li>
</ul>
<p>The next two subsections will detail the first two models since these are the most relevant for TensorFlow&#x2122;.</p>
<h5 id="3133-runtime-platform-models">3.1.3.3 Runtime Platform Models</h5>
<p>Rozanski and Woods[<a href="#rw">2</a>] state that the Runtime Platform model is the core of this view. It defines the set of hardware nodes required, the interconnection within the node, and software elements hosted in the hardware nodes. In order to build this model, it is important to understand how the system underlying mechanism works. According to the whitepaper[<a href="#whp">3</a>], a user creates an algorithm in TensorFlow&#x2122; with the provided API and internally that algorithm is described by a graph that represents a dataflow computation. In the graph, each node corresponds to an operation (for example: an arithmetic operation), the values that flow along the edges are tensors (that&apos;s why it is called TensorFlow&#x2122;!). The following figure obtained from the whitepaper[<a href="#whp">3</a>] shows an example of TensorFlow&#x2122; code fragment with its corresponding computation graph:</p>
<p align="center">
  <img src="https://delftswa.gitbooks.io/desosa2016/content/tensorflow/images-team-tensorflow/Deployment1.png">
</p>


<pre><code>                             Figure 5. TensorFlow&#x2122; code fragment with its computation graph example[[3]]
</code></pre><p>The whitepaper[<a href="#whp">3</a>] also mentions that the main components in TensorFlow&#x2122; are the clients, the master and one or more worker processes. If a user wants to run an algorithm, the user as a client, interacts with the master where it runs a placement algorithm to decide how to distribute the computation among all the worker processes. Each worker processes is responsible for arbitrating access to one or more computational devices. Each of the devices can communicate to each other through Send- and Receive node functions of the TensorFlow&#x2122; library.</p>
<p>The following figure shows the runtime model for TensorFlow&#x2122;:</p>
<p align="center">
  <img src="https://delftswa.gitbooks.io/desosa2016/content/tensorflow/images-team-tensorflow/Deployment2.png">
</p>


<pre><code>                              Figure 6. Runtime Platform Model
</code></pre><p>The model above applies for single, multiple and distributed environment.  </p>
<h5 id="3134-network-models">3.1.3.4 Network Models</h5>
<p>The Runtime Platform Model describes a high level of communication between the client, master and worker. The Network model describes specifically which nodes need to be connected and any other specific services and bandwidth requirements. In TensorFlow&#x2122; this model is applied to the cross device communication. Cross device communication means data transference between two or more devices (GPUs or CPUs), in which each device corresponds to a node in the network model.</p>
<p>According to the whitepaper[<a href="#whp">3</a>], once the master has run the placement algorithm, the graph is partitioned into a set of subgraphs, one per device, as shown in the left graph of the following figure:</p>
<p align="center">
  <img src="https://delftswa.gitbooks.io/desosa2016/content/tensorflow/images-team-tensorflow/Deployment3.png">
</p>


<pre><code>                              Figure 7. Network Model: TensorFlow&#x2122; Cross Device Communication
</code></pre><p>Once it is placed, TensorFlow&#x2122; removes the graph x -&gt; y and replaces it by two subgraphs: x -&gt; send node and receive -&gt; y as shown in the right side of Figure 7. At runtime, the implementation of send and receive nodes (which is part of TensorFlow&#x2122; library) coordinate the transfer of data across devices. By using this implementation, it isolates all communication inside Send- and Receive nodes which simplifies the rest of runtime. Also, one of the benefits of this implementation is that it decentralizes the system: the sender and receiver nodes impart the necessary synchronization between different workers and devices while the master only needs to issue requests per graph execution to each worker rather than being involved in the scheduling of cross device communication, thus, it makes the system much more scalable.  </p>
<h3 id="32-perspectives"><div name="per">3.2 Perspectives</div></h3>
<p>In the following paragraphs the evolution perspective gives insight in the history of TensorFlow&#x2122;, the variability perspective shows the modular development and different configurations, and the performance perspective gives an overview of the performance of TensorFlow&#x2122; compared to other machine learning applications. </p>
<h4 id="321-evolution-perspective"><div name="evp">3.2.1 Evolution perspective</div></h4>
<p>The history of developments starts from TensorFlow&#x2122; v0.5.0 till the current version 0.7.0. In order to 
know the history of developments, the <a href="https://www.tensorflow.org/versions/master/resources/roadmap.html#roadmap" target="_blank">roadmap</a> of TensorFlow&#x2122; was first looked at. Currently they are working on the support for <a href="https://github.com/tensorflow/tensorflow/issues/16" target="_blank">iOS support</a> and <a href="https://github.com/tensorflow/tensorflow/issues/22" target="_blank">OpenCL support</a>. The initial version of <a href="https://github.com/tensorflow/tensorflow/issues/23" target="_blank">distributed support</a> is available in the source code. However, this has not been released in the binary versions as of now. </p>
<h4 id="322-variability-perspective"><div name="vap">3.2.2 Variability perspective</div></h4>
<p>Many of the libraries in TensorFlow&#x2122; were developed separately and then integrated into the main codebase. This kind of modular development made it very easy to implement variability in TensorFlow&#x2122;. TensorFlow&#x2122; can be run in two different configurations, namely single device execution and multi-device execution. Apart from this, there is a GPU version of TensorFlow&#x2122; and non-GPU version of TensorFlow&#x2122;. It is supported in two separate Operating Systems, Linux and Mac OS. So, TensorFlow&#x2122; has a lot of variability built into it and the modular development of code is one of the reasons why TensorFlow&#x2122; can have this high amount of Variability. The core library is written C++ along with CUDA and for running the code on a machine containing a NVidia GPU. CUDA must be installed on the computer so as to support the code written for the GPU. 
In order to discuss the strategy used for implementing variability, we must first discuss the components of the TensorFlow&#x2122; application. The components in the TensorFlow&#x2122; application [<a href="#whp">3</a>] are:</p>
<h5 id="3221-client">3.2.2.1 Client</h5>
<p>The client is the application written in C++/ Python that interacts with the TensorFlow&#x2122; libraries and perform the required operations. The client creates a &quot;Session&quot; for interacting and using the TensorFlow&#x2122; libraries.</p>
<h5 id="3222-master-processes-and-worker-processes">3.2.2.2 Master processes and Worker processes</h5>
<p>The session created by the client interacts with the Master process, which in turn splits the client program into different sub programs/ sub graphs and allocates the work among different Worker Processes. These worker processes are responsible for running the computations on each of the devices/ processors. The devices in this case maybe GPU or CPU.</p>
<p>We can see the modularity built into the application. This kind of modularity allows for a huge amount of variability where each process works independent of each other. For example, if we want TensorFlow&#x2122; to run locally on a single computer, the client master and the worker processor all run on a single machine in the context of a single Operating system. This single computer can either be with or without the GPU. This is managed by the worker processes. So, this handles with variability of processors. The difference between the local and distributed versions is that they share the same code but the difference is that the client, the workers and the master can all be on different machines. These different tasks are containers in jobs managed by a cluster scheduling system. </p>
<p>For distributed versions of TensorFlow&#x2122;, <a href="http://www.grpc.io/" target="_blank">gRPC</a> is used for interprocess communication.  Detailed steps for setting up the distributed version TensorFlow&#x2122; can be found <a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/core/distributed_runtime/README.md" target="_blank">here</a>. We have identified the relevant steps from the <a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/core/distributed_runtime/README.md" target="_blank">source</a> and have listed them below. During build time, we must specify whether we need a CPU only or the GPU version. We need to have bazel installed on the computer in which we are building and currently this can be done only through source based installation of TensorFlow&#x2122;.</p>
<h4 id="323-performance-perspective"><div name="pep">3.2.3 Performance perspective</div></h4>
<p>According to Rozanski and Woods [<a href="#rw">2</a>], some of the important concerns are response time, throughput, turnaround time, scalability, predictability, Hardware Resource Requirements and Peak Load Behaviour. In our chapter, we focus only on Response time and throughput. We don&apos;t go into detail on these aspects, but we will be discussing at a high level about Performance Perspective of TensorFlow&#x2122;. Performance Perspective is very important to a tool like TensorFlow&#x2122; as the performance of machine learning applications written in TensorFlow&#x2122; is extremely crucial. In complex machine learning applications, the best hardware might not give us the best results and the performance mainly depends on the code quality and the effectiveness with which memory is utilized by the software. Due to the complexity of the algorithms involved it is an extremely difficult task to benchmark the performance of TensorFlow&#x2122; by ourselves. So, we decided to use the information provided by other developers involved in the field of machine learning. These benchmark details were obtained from this <a href="https://github.com/soumith/convnet-benchmarks/blob/master/README.md" target="_blank">document</a> in GitHub. Convnet has been used for the benchmarking. Convolutional network (Convnet) is a specific artificial neural network topology that is inspired by biological visual cortex and tailored for computer vision tasks. The benchmarks were performed on a machine with the following specifications:<code>6-core Intel Core i7-5930K CPU @ 3.50GHz</code> + <code>NVIDIA Titan X</code> + <code>Ubuntu 14.04 x86_64</code> . Some of the popular imagenet models were picked up and benchmarked. The benchmarking results are also done with other libraries available and we can draw some conclusions and compare them with other libraries to get a good idea of the actual performance of TensorFlow&#x2122; and whether it is one of the best libraries for machine learning. The benchamarked results are tabulated below:</p>
<p><strong><a href="https://code.google.com/p/cuda-convnet2/source/browse/layers/layers-imagenet-1gpu.cfg" target="_blank">AlexNet (One Weird Trick paper)</a></strong> - Input 128x3x224x224</p>
<table>
<thead>
<tr>
<th style="text-align:left">Library</th>
<th style="text-align:left">Class</th>
<th style="text-align:right">Time (ms)</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left">CuDNN[R4]-fp16 (Torch)</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">71</td>
</tr>
<tr>
<td style="text-align:left">Nervana-neon-fp16</td>
<td style="text-align:left"><a href="https://github.com/soumith/convnet-benchmarks/blob/master/nervana/README.md" target="_blank">ConvLayer</a></td>
<td style="text-align:right">78</td>
</tr>
<tr>
<td style="text-align:left">CuDNN[R4]-fp32 (Torch)</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">81</td>
</tr>
<tr>
<td style="text-align:left">Nervana-neon-fp32</td>
<td style="text-align:left"><a href="https://github.com/soumith/convnet-benchmarks/blob/master/nervana/README.md" target="_blank">ConvLayer</a></td>
<td style="text-align:right">87</td>
</tr>
<tr>
<td style="text-align:left">fbfft   (Torch)</td>
<td style="text-align:left"><a href="https://github.com/facebook/fbcunn/tree/master/src/fft" target="_blank">fbnn.SpatialConvolution</a></td>
<td style="text-align:right">104</td>
</tr>
<tr>
<td style="text-align:left">TensorFlow</td>
<td style="text-align:left"><a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/ops/nn.py" target="_blank">conv2d</a></td>
<td style="text-align:right">151</td>
</tr>
<tr>
<td style="text-align:left">Chainer</td>
<td style="text-align:left"><a href="https://github.com/pfnet/chainer/blob/master/chainer/links/connection/convolution_2d.py" target="_blank">Convolution2D</a></td>
<td style="text-align:right">177</td>
</tr>
<tr>
<td style="text-align:left">cudaconvnet2*</td>
<td style="text-align:left"><a href="https://github.com/soumith/cuda-convnet2.torch/blob/master/cudaconv3/src/filter_acts.cu" target="_blank">ConvLayer</a></td>
<td style="text-align:right">177</td>
</tr>
<tr>
<td style="text-align:left">CuDNN[R2] *</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">231</td>
</tr>
<tr>
<td style="text-align:left">Caffe (native)</td>
<td style="text-align:left"><a href="https://github.com/BVLC/caffe/blob/master/src/caffe/layers/conv_layer.cu" target="_blank">ConvolutionLayer</a></td>
<td style="text-align:right">324</td>
</tr>
<tr>
<td style="text-align:left">Torch-7 (native)</td>
<td style="text-align:left"><a href="https://github.com/torch/cunn/blob/master/SpatialConvolutionMM.cu" target="_blank">SpatialConvolutionMM</a></td>
<td style="text-align:right">342</td>
</tr>
<tr>
<td style="text-align:left">CL-nn (Torch)</td>
<td style="text-align:left"><a href="https://github.com/hughperkins/clnn/blob/master/SpatialConvolutionMM.cl" target="_blank">SpatialConvolutionMM</a></td>
<td style="text-align:right">963</td>
</tr>
</tbody>
</table>
<p><strong><a href="http://arxiv.org/abs/1312.6229" target="_blank">Overfeat [fast]</a></strong> - Input 128x3x231x231</p>
<table>
<thead>
<tr>
<th style="text-align:left">Library</th>
<th style="text-align:left">Class</th>
<th style="text-align:right">Time (ms)</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left">CuDNN[R4]-fp16  (Torch)</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">242</td>
</tr>
<tr>
<td style="text-align:left">CuDNN[R4]-fp32  (Torch)</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">268</td>
</tr>
<tr>
<td style="text-align:left">fbfft  (Torch)</td>
<td style="text-align:left"><a href="https://github.com/facebook/fbcunn/tree/master/src/fft" target="_blank">SpatialConvolutionCuFFT</a></td>
<td style="text-align:right">342</td>
</tr>
<tr>
<td style="text-align:left">TensorFlow</td>
<td style="text-align:left"><a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/ops/nn.py" target="_blank">conv2d</a></td>
<td style="text-align:right">349</td>
</tr>
<tr>
<td style="text-align:left">Chainer</td>
<td style="text-align:left"><a href="https://github.com/pfnet/chainer/blob/master/chainer/links/connection/convolution_2d.py" target="_blank">Convolution2D</a></td>
<td style="text-align:right">620</td>
</tr>
<tr>
<td style="text-align:left">cudaconvnet2*</td>
<td style="text-align:left"><a href="https://github.com/soumith/cuda-convnet2.torch/blob/master/cudaconv3/src/filter_acts.cu" target="_blank">ConvLayer</a></td>
<td style="text-align:right">723</td>
</tr>
<tr>
<td style="text-align:left">CuDNN[R2] *</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">810</td>
</tr>
<tr>
<td style="text-align:left">Caffe</td>
<td style="text-align:left"><a href="https://github.com/BVLC/caffe/blob/master/src/caffe/layers/conv_layer.cu" target="_blank">ConvolutionLayer</a></td>
<td style="text-align:right">823</td>
</tr>
<tr>
<td style="text-align:left">CL-nn (Torch)</td>
<td style="text-align:left"><a href="https://github.com/hughperkins/clnn/blob/master/SpatialConvolutionMM.cl" target="_blank">SpatialConvolutionMM</a></td>
<td style="text-align:right">963</td>
</tr>
<tr>
<td style="text-align:left">Caffe-CLGreenTea</td>
<td style="text-align:left"><a href="https://github.com/naibaf7/caffe" target="_blank">ConvolutionLayer</a></td>
<td style="text-align:right">2857</td>
<td>616</td>
<td>2240</td>
</tr>
</tbody>
</table>
<p><strong><a href="http://arxiv.org/abs/1409.1556/" target="_blank">OxfordNet [Model-A]</a></strong> - Input 64x3x224x224</p>
<table>
<thead>
<tr>
<th style="text-align:left">Library</th>
<th style="text-align:left">Class</th>
<th style="text-align:right">Time (ms)</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left">CuDNN[R4]-fp16  (Torch)</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">471</td>
<td>CuDNN[R4]-fp32  (Torch)</td>
<td><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td>529</td>
</tr>
<tr>
<td style="text-align:left">Chainer</td>
<td style="text-align:left"><a href="https://github.com/pfnet/chainer/blob/master/chainer/links/connection/convolution_2d.py" target="_blank">Convolution2D</a></td>
<td style="text-align:right">885</td>
</tr>
<tr>
<td style="text-align:left">TensorFlow</td>
<td style="text-align:left"><a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/ops/nn.py" target="_blank">conv2d</a></td>
<td style="text-align:right">982</td>
</tr>
<tr>
<td style="text-align:left">fbfft    (Torch)</td>
<td style="text-align:left"><a href="https://github.com/facebook/fbcunn/tree/master/src/fft" target="_blank">SpatialConvolutionCuFFT</a></td>
<td style="text-align:right">1092</td>
</tr>
<tr>
<td style="text-align:left">cudaconvnet2*</td>
<td style="text-align:left"><a href="https://github.com/soumith/cuda-convnet2.torch/blob/master/cudaconv3/src/filter_acts.cu" target="_blank">ConvLayer</a></td>
<td style="text-align:right">1229</td>
</tr>
<tr>
<td style="text-align:left">CuDNN[R2] *</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">1099</td>
</tr>
<tr>
<td style="text-align:left">Caffe</td>
<td style="text-align:left"><a href="https://github.com/BVLC/caffe/blob/master/src/caffe/layers/conv_layer.cu" target="_blank">ConvolutionLayer</a></td>
<td style="text-align:right">1068</td>
</tr>
<tr>
<td style="text-align:left">Torch-7 (native)</td>
<td style="text-align:left"><a href="https://github.com/torch/cunn/blob/master/SpatialConvolutionMM.cu" target="_blank">SpatialConvolutionMM</a></td>
<td style="text-align:right">1105</td>
<td>350</td>
<td>755</td>
</tr>
<tr>
<td style="text-align:left">CL-nn (Torch)</td>
<td style="text-align:left"><a href="https://github.com/hughperkins/clnn/blob/master/SpatialConvolutionMM.cl" target="_blank">SpatialConvolutionMM</a></td>
<td style="text-align:right">3437</td>
<td>875</td>
<td>2562</td>
</tr>
<tr>
<td style="text-align:left">Caffe-CLGreenTea</td>
<td style="text-align:left"><a href="https://github.com/naibaf7/caffe" target="_blank">ConvolutionLayer</a></td>
<td style="text-align:right">5620</td>
<td>988</td>
<td>4632</td>
</tr>
</tbody>
</table>
<p><strong><a href="http://research.google.com/pubs/pub43022.html" target="_blank">GoogleNet V1</a></strong> - Input 128x3x224x224</p>
<table>
<thead>
<tr>
<th style="text-align:left">Library</th>
<th style="text-align:left">Class</th>
<th style="text-align:right">Time (ms)</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left">CuDNN[R4]-fp16   (Torch)</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">462</td>
</tr>
<tr>
<td style="text-align:left">CuDNN[R4]-fp32  (Torch)</td>
<td style="text-align:left"><a href="https://github.com/soumith/cudnn.torch/blob/master/SpatialConvolution.lua" target="_blank">cudnn.SpatialConvolution</a></td>
<td style="text-align:right">470</td>
</tr>
<tr>
<td style="text-align:left">Chainer</td>
<td style="text-align:left"><a href="https://github.com/pfnet/chainer/blob/master/chainer/links/connection/convolution_2d.py" target="_blank">Convolution2D</a></td>
<td style="text-align:right">687</td>
</tr>
<tr>
<td style="text-align:left">TensorFlow</td>
<td style="text-align:left"><a href="https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/ops/nn.py" target="_blank">conv2d</a></td>
<td style="text-align:right">905</td>
</tr>
<tr>
<td style="text-align:left">Caffe</td>
<td style="text-align:left"><a href="https://github.com/BVLC/caffe/blob/master/src/caffe/layers/conv_layer.cu" target="_blank">ConvolutionLayer</a></td>
<td style="text-align:right">1935</td>
</tr>
<tr>
<td style="text-align:left">CL-nn (Torch)</td>
<td style="text-align:left"><a href="https://github.com/hughperkins/clnn/blob/master/SpatialConvolutionMM.cl" target="_blank">SpatialConvolutionMM</a></td>
<td style="text-align:right">7016</td>
</tr>
<tr>
<td style="text-align:left">Caffe-CLGreenTea</td>
<td style="text-align:left"><a href="https://github.com/naibaf7/caffe" target="_blank">ConvolutionLayer</a></td>
<td style="text-align:right">9462</td>
</tr>
</tbody>
</table>
<p>TensorFlow&#x2122; and Chainer are benchmarked with CuDNN, but it is not explicitly mentioned, and  one might think that these frameworks as a whole are faster, than for example Caffe, which might not be the case. However, one thing that can be inferred from the table above is that TensorFlow&#x2122; isn&apos;t the best library out there and it as its own set of performance issues and there is a lot of room for improvement. TensorFlow&#x2122; only uses cuDNN v2 and its performance is  almost 1.5x slower than Torch with cuDNN v2. It must be noted that the benchmark results are done using only a single-powerful GPU. However, these benchmarks were run on an older version of TensorFlow&#x2122; and the current benchmarking results are not yet available. More detailed and a clear view of TensorFlow&#x2122;&apos;s performance results for all kinds of architectures and number of machines can be expected in the next versions of whitepaper. However, not much detail is available from Google itself. Benchmarking performance is on their roadmap and more clear results can be expected in the future.</p>
<h2 id="4-conclusion"><div name="con">4. Conclusion</div></h2>
<p>Based on the analysis of the architecture, we can conclude that TensorFlow&#x2122; is a startup project which is not yet mature and has a lot of room for future improvements. In the previous section it was shown that TensorFlow&#x2122; has performance issues compared to other machine learning applications. Next to this, the variability of TensorFlow&#x2122; is limited at this moment and it would be beneficial to extend support to OpenCL and add different platforms, such as iOS. Despite these limitations, we believe that TensorFlow&#x2122; has a lot of potential. Opening up TensorFlow&#x2122; to the OpenSource community is a very important step to tackle these limitations. When Google can address the current shortcomings it might very well become the defacto standard for machine learning.  </p>
<h2 id="5-references"><div name="ref">5. References</div></h2>
<p>[1] Mitchell, R. K., Agle, B. R., &amp; Wood, D. J. (1997). Toward a Theory of Stakeholder Identification and Salience: Defining the Principle of Who and What Really Counts. The Academy of Management Review, 22(4), 853&#x2013;886. Retrieved from <a href="http://www.jstor.org/stable/259247" target="_blank">http://www.jstor.org/stable/259247</a><div id="mi"></div></p>
<p>[2] Nick Rozanski and Eoin Woods. (2011). Software Systems Architecture: Working with Stakeholders Using Viewpoints and Perspectives. Addison-Wesley Professional.<div id="rw"></div></p>
<p>[3] Mart&#xED;n Abadi, Ashish Agarwal, Paul Barham, Eugene Brevdo, Zhifeng Chen, Craig Citro, Greg S. Corrado, Andy Davis, Jeffrey Dean, Matthieu Devin, Sanjay Ghemawat, Ian Goodfellow, Andrew Harp, Geoffrey Irving, Michael Isard, Rafal Jozefowicz, Yangqing Jia, Lukasz Kaiser, Manjunath Kudlur, Josh Levenberg, Dan Man&#xE9;, Mike Schuster, Rajat Monga, Sherry Moore, Derek Murray, Chris Olah, Jonathon Shlens, Benoit Steiner, Ilya Sutskever, Kunal Talwar, Paul Tucker, Vincent Vanhoucke, Vijay Vasudevan, Fernanda Vi&#xE9;gas, Oriol Vinyals, Pete Warden, Martin Wattenberg, Martin Wicke, Yuan Yu, and Xiaoqiang Zheng. TensorFlow: Large-scale machine learning on heterogeneous systems, 2015. Software available from tensorflow.org. <div id="whp"></div></p>
