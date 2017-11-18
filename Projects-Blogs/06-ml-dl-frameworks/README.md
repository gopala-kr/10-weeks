## case study: ml/dl frameworks/libraries(an architectural overview)

 * **frameworks:** Theano, Tensorflow, Caffe + caffe2, Torch + pytorch, MXNet
 * **libraries/ services:** Keras, Deeplearning4j, Microsoft Cognitive Toolkit, Lasagne, BigDL, scikit-learn, chainer

********************************
**Goals of this article**

* a casestudy to outilne all available AI-ML-DL-Scientific computing libraries/frameworks.
* to study architectures of some importatnt frameworks/libraries

******************************

 | HackerNews        | Medium         | Reddit  |  Quora-QA  | Stack-Overflow-QA | Awesome-gh | Online-Courses | Official docs|
| ------------- |:-------------:| -----:| -----:|-----:|-----:|-----:|-----:|
|  [torch](https://hn.algolia.com/?query=torch&sort=byPopularity&prefix&page=0&dateRange=all&type=story)  | [torch](https://medium.com/tag/torch))  | [torch](https://www.reddit.com/r/pytorch/)  | [torch](https://www.quora.com/topic/Torch-machine-learning)  |  [torch](https://stackoverflow.com/questions/tagged/torch)    | [torch](https://github.com/carpedm20/awesome-torch)  | [torch](https://github.com/Atcold/torch-Video-Tutorials)  |  [torch](http://torch.ch/)  |
|  [theano](https://hn.algolia.com/?query=theano&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story)  | [theano](https://medium.com/tag/theano)  | [theano](https://www.reddit.com/r/MachineLearning/)  | [theano](https://www.quora.com/topic/Theano)  |   [theano](https://stackoverflow.com/search?q=theano)   | [theano](https://github.com/kjw0612/awesome-rnn)  | [theano](http://nbviewer.jupyter.org/github/craffel/theano-tutorial/blob/master/Theano%20Tutorial.ipynb)  |[theano](http://deeplearning.net/software/theano/)  |
|  [caffe](https://hn.algolia.com/?query=caffe&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story)  | [caffe](https://medium.com/tag/caffe)  | [caffe](https://www.reddit.com/r/MachineLearning/comments/4pxprc/a_practical_introduction_to_deep_learning_with/)  | [caffe](https://www.quora.com/topic/Caffe-Deep-Learning-Framework-1)  |   [caffe](https://stackoverflow.com/search?q=caffe)  | [caffe](https://github.com/MichaelXin/Awesome-Caffe)  | [caffe](http://caffe.berkeleyvision.org/tutorial/)  | [caffe](http://caffe.berkeleyvision.org/)  |
 |  [tensorflow](https://hn.algolia.com/?query=tensorflow&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story)  | [tensorflow](https://medium.com/tag/tensorflow)  | [tensorflow](https://www.reddit.com/r/tensorflow/)  | [tensorflow](https://www.quora.com/topic/TensorFlow-software-library)  |   [tensorflow](https://stackoverflow.com/search?q=tensorflow)  | [tensorflow](https://github.com/jtoy/awesome-tensorflow)  | [tensorflow-linkedin](https://www.linkedin.com/learning/topics/google-tensorflow-2) , [stanford-course](https://web.stanford.edu/class/cs20si/), [OpenSAP-course](https://open.sap.com/courses/ml2),  [nvidia](https://www.nvidia.com/en-us/data-center/gpu-accelerated-applications/tensorflow/) | [tensorflow](https://www.tensorflow.org/) |
|  [maxnet](https://hn.algolia.com/?query=mxnet&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story)  | [mxnet](https://medium.com/tag/mxnet)  | [mxnet](https://www.reddit.com/r/mxnet/) | [mxnet](https://www.quora.com/topic/MXNet)  |   [mxnet](https://stackoverflow.com/questions/tagged/mxnet)  | [mxnet](https://github.com/chinakook/Awesome-MXNet)  | [mxnet](https://www.youtube.com/watch?v=GBkOMtc9BIk)  | [mxnet](https://mxnet.incubator.apache.org/)  |
| [keras](https://hn.algolia.com/?query=keras&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story) | [keras](https://medium.com/tag/keras) | [keras](https://www.reddit.com/r/KerasML/) | [keras](https://www.quora.com/topic/Keras) | [keras](https://stackoverflow.com/questions/tagged/keras) | [keras](https://github.com/fchollet/keras-resources) | [keras](https://www.linkedin.com/learning/topics/keras) | [keras](https://keras.io/) |
| [deeplearning4j](https://hn.algolia.com/?query=deeplearning4j&sort=byPopularity&prefix=false&page=0&dateRange=all&type=story) | [deeplearning4j](https://medium.com/tag/deeplearning4j) | [deeplearning4j](https://www.reddit.com/r/deeplearning4j/) | [deeplearning4j](https://www.quora.com/topic/Deeplearning4j) | [deeplearning4j](https://stackoverflow.com/search?q=deeplearning4j) | [deeplearning4j](https://github.com/josephmisiti/awesome-machine-learning) | [deeplearning4j](https://deeplearning4j.org/tutorials) | [deeplearning4j](https://deeplearning4j.org/) |
| [scikit-learn](https://hn.algolia.com/?query=scikit-learn&sort=byPopularity&prefix&page=0&dateRange=all&type=story) | [scikit-learn](https://medium.com/tag/scikit-learn) | [scikit-learn](https://www.reddit.com/subreddits/search?q=scikit-learn) | [scikit-learn](https://www.quora.com/topic/scikit-learn) | [scikit-learn](https://stackoverflow.com/questions/tagged/scikit-learn) | [scikit-learn](https://github.com/josephmisiti/awesome-machine-learning) | [scikit-learn](http://scikit-learn.org/stable/tutorial/index.html) | [scikit-learn](http://scikit-learn.org/) |


***********************

 Nowadays Quora and Medium's have become learning platforms, some useful tags to understand AI in simple words:

 
 | [Artificial Intelligence](https://www.quora.com/topic/Artificial-Intelligence) | [Machine Learning](https://www.quora.com/topic/Machine-Learning) | [Artificial Neural Networks](https://www.quora.com/topic/Artificial-Neural-Networks) |
[Deep Learning](https://www.quora.com/topic/Deep-Learning) | [computer vision](https://www.quora.com/topic/Computer-Vision) |[Convolutional Neural Networks](https://www.quora.com/topic/Convolutional-Neural-Networks-1) | [Natural Language Processing](https://www.quora.com/topic/Natural-Language-Processing) | [Mathematics and Machine Learning
](https://www.quora.com/topic/Mathematics-and-Machine-Learning) |  [Gradient Descent](https://www.quora.com/topic/Gradient-Descent) | [Support Vector Machines](https://www.quora.com/topic/Support-Vector-Machines)|  [Naive Bayes](https://www.quora.com/topic/Naive-Bayes) | [Kernel methods](https://www.quora.com/topic/Kernel-methods-1) |  [Classification
(machine learning)](https://www.quora.com/topic/Classification-machine-learning) | [Random Forests
(algorithm)](https://www.quora.com/topic/Random-Forests-algorithm) | [Bayesian Networks](https://www.quora.com/topic/Bayesian-Networks) | [Sentiment Analysis](https://www.quora.com/topic/Sentiment-Analysis) | [Bayes' Theorem](https://www.quora.com/topic/Bayes-Theorem) | [Decision Trees](https://www.quora.com/topic/Decision-Trees) | [Machine Translation](https://www.quora.com/topic/Machine-Translation) | [Information Retrieval](https://www.quora.com/topic/Information-Retrieval) | [Statistics
(academic discipline)](https://www.quora.com/topic/Statistics-academic-discipline) | [Data Science](https://www.quora.com/topic/Data-Science) | [Data Mining](https://www.quora.com/topic/Data-Mining) | [Big Data](https://www.quora.com/topic/Big-Data) | [Datasets](https://www.quora.com/topic/Datasets) | [Convolutional Neural Networks](https://www.quora.com/topic/Convolutional-Neural-Networks-1) | [Web Crawling](https://www.quora.com/topic/Web-Crawling) | [Recurrent Neural Networks
(RNNs)](https://www.quora.com/topic/Recurrent-Neural-Networks-RNNs) | [Long Short-term Memory](https://www.quora.com/topic/Long-Short-term-Memory) | [Neural Machine Translation](https://www.quora.com/topic/Neural-Machine-Translation) | [Google Translate](https://www.quora.com/topic/Google-Translate) | [Graphics Processing Unit](https://www.quora.com/topic/Graphics-Processing-Unit) | [Reinforcement Learning](https://www.quora.com/topic/Reinforcement-Learning) | [Supervised Learning](https://www.quora.com/topic/Supervised-Learning) | [Unsupervised Learning](https://www.quora.com/topic/Unsupervised-Learning) | [Autoencoder](https://www.quora.com/topic/Autoencoder) | [Restricted Boltzmann Machine
(RBM)](https://www.quora.com/topic/Restricted-Boltzmann-Machine-RBM) | [Dimensionality Reduction](https://www.quora.com/topic/Dimensionality-Reduction) | [Probabilistic Graphical Models](https://www.quora.com/topic/Probabilistic-Graphical-Models) | [Hidden Markov Models](https://www.quora.com/topic/Hidden-Markov-Models) | [Markov Chains](https://www.quora.com/topic/Markov-Chains) | [Stochastic Processes](https://www.quora.com/topic/Stochastic-Processes) | [GPU Computation](https://www.quora.com/topic/GPU-Computation) | [Compute Unified Device Architecture
(CUDA)](https://www.quora.com/topic/Compute-Unified-Device-Architecture-CUDA) | [Pattern Recognition](https://www.quora.com/topic/Pattern-Recognition) | [Speech Recognition](https://www.quora.com/topic/Speech-Recognition) | [Generative Adversarial Networks](https://www.quora.com/topic/Generative-Adversarial-Networks-1) | [K-Means Algorithms](https://www.quora.com/topic/K-Means-Algorithms) | [Cluster analysis](https://www.quora.com/topic/Cluster-analysis) | [Semi-supervised Learning](https://www.quora.com/topic/Semi-supervised-Learning) | [Q-learning](https://www.quora.com/topic/Q-learning) |[Computational Neuroscience](https://www.quora.com/topic/Computational-Neuroscience) | [Cognitive Neuroscience](https://www.quora.com/topic/Cognitive-Neuroscience) | [Brain Training](https://www.quora.com/topic/Brain-Training) | [Cognitive Psychology](https://www.quora.com/topic/Cognitive-Psychology) | [Behavioral Psychology](https://www.quora.com/topic/Behavioral-Psychology) | [Human Psychology](https://www.quora.com/topic/Human-Psychology) | [Brain Games](https://www.quora.com/topic/Brain-Games-1) | [Neurons](https://www.quora.com/topic/Neurons) | [Axon](https://www.quora.com/topic/Axon) | [Nerves](https://www.quora.com/topic/Nerves) | [Nervous System](https://www.quora.com/topic/Nervous-System) | [Brain-Computer Interfaces](https://www.quora.com/topic/Brain-Computer-Interfaces) | [Robotics](https://www.quora.com/topic/Robotics) | [Chatbots and Conversational Agents](https://www.quora.com/topic/Chatbots-and-Conversational-Agents) | [Bots
(software)](https://www.quora.com/topic/Bots-software) | [Intelligence](https://www.quora.com/topic/Intelligence) |



**********************
---------------------

### Scientific Computing Tools for Python

<div class="toctree-wrapper compound">
</div>
<p>SciPy refers to several related but distinct entities:</p>
<ul class="simple">
<li>The <em>SciPy ecosystem</em>, a collection of open source software for scientific
computing in Python.</li>
<li>The <em>community</em> of people who use and develop this stack.</li>
<li>Several <em>conferences</em> dedicated to scientific computing in Python - SciPy,
EuroSciPy and SciPy.in.</li>
<li>The <a class="reference internal" href="scipylib/index.html"><span class="doc">SciPy library</span></a>, one component of the SciPy stack,
providing many numerical routines.</li>
</ul>
<div class="section" id="the-scipy-ecosystem">
<h4>The SciPy ecosystem<a class="headerlink" href="#the-scipy-ecosystem" title="Permalink to this headline">¶</a></h4>
<p>Scientific computing in Python builds upon a small core of packages:</p>
<ul class="simple">
<li><a class="reference external" href="https://www.python.org/">Python</a>, a general purpose programming language. It is interpreted and
dynamically typed and is very suited for interactive work and quick
prototyping, while being powerful enough to write large applications in.</li>
<li><a class="reference external" href="http://www.numpy.org/">NumPy</a>, the fundamental package for numerical computation. It defines the
numerical array and matrix types and basic operations on them.</li>
<li>The <a class="reference internal" href="scipylib/index.html"><span class="doc">SciPy library</span></a>, a collection of numerical algorithms and
domain-specific toolboxes, including signal processing, optimization,
statistics and much more.</li>
<li><a class="reference external" href="http://matplotlib.org/">Matplotlib</a>, a mature and popular plotting package, that provides
publication-quality 2D plotting as well as rudimentary 3D plotting</li>
</ul>
<p>On this base, the SciPy ecosystem includes general and specialised tools for data management and computation, productive experimentation and high-performance computing. Below we overview some key packages, though there are <a class="reference internal" href="topical-software.html"><span class="doc">many more relevant packages</span></a>.</p>
<p>Data and computation:</p>
<ul class="simple">
<li><a class="reference external" href="http://pandas.pydata.org/">pandas</a>, providing high-performance, easy to use data structures.</li>
<li><a class="reference external" href="http://www.sympy.org/">SymPy</a>, for symbolic mathematics and computer algebra.</li>
<li><a class="reference external" href="http://scikit-image.org/">scikit-image</a> is a collection of algorithms for image processing.</li>
<li><a class="reference external" href="http://scikit-learn.org/">scikit-learn</a> is a collection of algorithms and tools for machine learning.</li>
<li><a class="reference external" href="http://www.h5py.org">h5py</a> and <a class="reference external" href="http://www.pytables.org">PyTables</a> can both access data stored in the HDF5 format.</li>
</ul>
<p>Productivity and high-performance computing:</p>
<ul class="simple">
<li><a class="reference external" href="http://ipython.org/">IPython</a>, a rich interactive interface, letting you quickly process data and
test ideas.</li>
<li>The <a class="reference external" href="http://jupyter.org/">Jupyter</a> notebook provides IPython functionality and more in your web
browser, allowing you to document your computation in an easily reproducible form.</li>
<li><a class="reference external" href="http://cython.org/">Cython</a> extends Python syntax so that you can conveniently build C extensions,
either to speed up critical code, or to integrate with C/C++ libraries.</li>
<li><a class="reference external" href="https://dask.readthedocs.io/">Dask</a>, <a class="reference external" href="https://joblib.readthedocs.io/">Joblib</a> or <a class="reference external" href="https://ipyparallel.readthedocs.io/">IPyParallel</a> for distributed processing with a focus on numeric data.</li>
</ul>
<p>Quality assurance:</p>
<ul class="simple">
<li><a class="reference external" href="https://nose.readthedocs.org/en/latest/">nose</a>, a framework for testing Python code, being phased out in preference for <a class="reference external" href="https://docs.pytest.org/">pytest</a>.</li>
<li><a class="reference external" href="https://github.com/numpy/numpydoc">numpydoc</a>, a standard and library for documenting Scientific Python libraries.</li>
</ul>
</div>
</div>



-----------------------------
------------------------------

## Reference list

-------------------

### tf papers

* [TensorFlow: Large-Scale Machine Learning on Heterogeneous Distributed Systems](http://download.tensorflow.org/paper/whitepaper2015.pdf) - This paper describes the TensorFlow interface and an implementation of that interface that we have built at Google
* [TF.Learn: TensorFlow's High-level Module for Distributed Machine Learning](https://arxiv.org/abs/1612.04251)
* [Comparative Study of Deep Learning Software Frameworks](http://arxiv.org/abs/1511.06435) - The study is performed on several types of deep learning architectures and we evaluate the performance of the above frameworks when employed on a single machine for both (multi-threaded) CPU and GPU (Nvidia Titan X) settings
* [Distributed TensorFlow with MPI](http://arxiv.org/abs/1603.02339) - In this paper, we extend recently proposed Google TensorFlow for execution on large scale clusters using Message Passing Interface (MPI)
* [Globally Normalized Transition-Based Neural Networks](http://arxiv.org/abs/1603.06042) - This paper describes the models behind [SyntaxNet](https://github.com/tensorflow/models/tree/master/syntaxnet).
* [TensorFlow: A system for large-scale machine learning](https://arxiv.org/abs/1605.08695) - This paper describes the TensorFlow dataflow model in contrast to existing systems and demonstrate the compelling performance


### tf ref

<li id="cite_note-Credits-1"><span class="mw-cite-backlink">^ <a href="#cite_ref-Credits_1-0"><sup><i><b>a</b></i></sup></a> <a href="#cite_ref-Credits_1-1"><sup><i><b>b</b></i></sup></a></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="http://tensorflow.org/about">"Credits"</a>. <i>TensorFlow.org</i><span class="reference-accessdate">. Retrieved <span class="nowrap">November 10,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=TensorFlow.org&amp;rft.atitle=Credits&amp;rft_id=http%3A%2F%2Ftensorflow.org%2Fabout&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-2"><span class="mw-cite-backlink"><b><a href="#cite_ref-2">^</a></b></span> <span class="reference-text"><cite class="citation news"><a rel="nofollow" class="external text" href="https://github.com/tensorflow/tensorflow/releases">"TensorFlow Release"</a><span class="reference-accessdate">. Retrieved <span class="nowrap">June 19,</span> 2017</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=article&amp;rft.atitle=TensorFlow+Release&amp;rft_id=https%3A%2F%2Fgithub.com%2Ftensorflow%2Ftensorflow%2Freleases&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-YoutubeClip-3"><span class="mw-cite-backlink">^ <a href="#cite_ref-YoutubeClip_3-0"><sup><i><b>a</b></i></sup></a> <a href="#cite_ref-YoutubeClip_3-1"><sup><i><b>b</b></i></sup></a> <a href="#cite_ref-YoutubeClip_3-2"><sup><i><b>c</b></i></sup></a></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://www.youtube.com/watch?v=oZikw5k_2FM">"TensorFlow: Open source machine learning"</a> "It is machine learning software being used for various kinds of perceptual and language understanding tasks" — Jeffrey Dean, minute 0:47 / 2:17 from Youtube clip</span></li>
<li id="cite_note-whitepaper2015-4"><span class="mw-cite-backlink">^ <a href="#cite_ref-whitepaper2015_4-0"><sup><i><b>a</b></i></sup></a> <a href="#cite_ref-whitepaper2015_4-1"><sup><i><b>b</b></i></sup></a></span> <span class="reference-text"><cite class="citation web"><a href="/wiki/Jeff_Dean_(computer_scientist)" title="Jeff Dean (computer scientist)">Dean, Jeff</a>; Monga, Rajat; et al. (November 9, 2015). <a rel="nofollow" class="external text" href="http://download.tensorflow.org/paper/whitepaper2015.pdf">"TensorFlow: Large-scale machine learning on heterogeneous systems"</a> <span style="font-size:85%;">(PDF)</span>. <i>TensorFlow.org</i>. Google Research<span class="reference-accessdate">. Retrieved <span class="nowrap">November 10,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=TensorFlow.org&amp;rft.atitle=TensorFlow%3A+Large-scale+machine+learning+on+heterogeneous+systems&amp;rft.date=2015-11-09&amp;rft.aulast=Dean&amp;rft.aufirst=Jeff&amp;rft.au=Monga%2C+Rajat&amp;rft.au=Ghemawat%2C+Sanjay&amp;rft_id=http%3A%2F%2Fdownload.tensorflow.org%2Fpaper%2Fwhitepaper2015.pdf&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-Metz-Nov9-5"><span class="mw-cite-backlink"><b><a href="#cite_ref-Metz-Nov9_5-0">^</a></b></span> <span class="reference-text"><cite class="citation web">Metz, Cade (November 9, 2015). <a rel="nofollow" class="external text" href="https://www.wired.com/2015/11/google-open-sources-its-artificial-intelligence-engine/">"Google Just Open Sourced TensorFlow, Its Artificial Intelligence Engine"</a>. <i><a href="/wiki/Wired_(website)" class="mw-redirect" title="Wired (website)">Wired</a></i><span class="reference-accessdate">. Retrieved <span class="nowrap">November 10,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Wired&amp;rft.atitle=Google+Just+Open+Sourced+TensorFlow%2C+Its+Artificial+Intelligence+Engine&amp;rft.date=2015-11-09&amp;rft.aulast=Metz&amp;rft.aufirst=Cade&amp;rft_id=https%3A%2F%2Fwww.wired.com%2F2015%2F11%2Fgoogle-open-sources-its-artificial-intelligence-engine%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-Perez-6"><span class="mw-cite-backlink"><b><a href="#cite_ref-Perez_6-0">^</a></b></span> <span class="reference-text"><cite class="citation web">Perez, Sarah (November 9, 2015). <a rel="nofollow" class="external text" href="https://techcrunch.com/2015/11/09/google-open-sources-the-machine-learning-tech-behind-google-photos-search-smart-reply-and-more/">"Google Open-Sources The Machine Learning Tech Behind Google Photos Search, Smart Reply And More"</a>. <i>TechCrunch</i><span class="reference-accessdate">. Retrieved <span class="nowrap">November 11,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=TechCrunch&amp;rft.atitle=Google+Open-Sources+The+Machine+Learning+Tech+Behind+Google+Photos+Search%2C+Smart+Reply+And+More&amp;rft.date=2015-11-09&amp;rft.aulast=Perez&amp;rft.aufirst=Sarah&amp;rft_id=https%3A%2F%2Ftechcrunch.com%2F2015%2F11%2F09%2Fgoogle-open-sources-the-machine-learning-tech-behind-google-photos-search-smart-reply-and-more%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-Oremus-7"><span class="mw-cite-backlink"><b><a href="#cite_ref-Oremus_7-0">^</a></b></span> <span class="reference-text"><cite class="citation web">Oremus, Will (November 11, 2015). <a rel="nofollow" class="external text" href="http://www.slate.com/blogs/future_tense/2015/11/09/google_s_tensorflow_is_open_source_and_it_s_about_to_be_a_huge_huge_deal.html">"What Is TensorFlow, and Why Is Google So Excited About It?"</a>. <i>Slate</i><span class="reference-accessdate">. Retrieved <span class="nowrap">November 11,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Slate&amp;rft.atitle=What+Is+TensorFlow%2C+and+Why+Is+Google+So+Excited+About+It%3F&amp;rft.date=2015-11-11&amp;rft.aulast=Oremus&amp;rft.aufirst=Will&amp;rft_id=http%3A%2F%2Fwww.slate.com%2Fblogs%2Ffuture_tense%2F2015%2F11%2F09%2Fgoogle_s_tensorflow_is_open_source_and_it_s_about_to_be_a_huge_huge_deal.html&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-Ward-Bailey-8"><span class="mw-cite-backlink"><b><a href="#cite_ref-Ward-Bailey_8-0">^</a></b></span> <span class="reference-text"><cite class="citation web">Ward-Bailey, Jeff (November 25, 2015). <a rel="nofollow" class="external text" href="http://www.csmonitor.com/Technology/2015/0914/Google-chairman-We-re-making-real-progress-on-artificial-intelligence">"Google chairman: We're making 'real progress' on artificial intelligence"</a>. <i>CSMonitor</i><span class="reference-accessdate">. Retrieved <span class="nowrap">November 25,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=CSMonitor&amp;rft.atitle=Google+chairman%3A+We%E2%80%99re+making+%27real+progress%27+on+artificial+intelligence&amp;rft.date=2015-11-25&amp;rft.aulast=Ward-Bailey&amp;rft.aufirst=Jeff&amp;rft_id=http%3A%2F%2Fwww.csmonitor.com%2FTechnology%2F2015%2F0914%2FGoogle-chairman-We-re-making-real-progress-on-artificial-intelligence&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-9"><span class="mw-cite-backlink"><b><a href="#cite_ref-9">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://github.com/tensorflow/tensorflow/blob/07bb8ea2379bd459832b23951fb20ec47f3fdbd4/RELEASE.md">"Tensorflow Release 1.0.0"</a>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Tensorflow+Release+1.0.0&amp;rft_id=https%3A%2F%2Fgithub.com%2Ftensorflow%2Ftensorflow%2Fblob%2F07bb8ea2379bd459832b23951fb20ec47f3fdbd4%2FRELEASE.md&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-Metz-Nov10-10"><span class="mw-cite-backlink"><b><a href="#cite_ref-Metz-Nov10_10-0">^</a></b></span> <span class="reference-text"><cite class="citation news">Metz, Cade (November 10, 2015). <a rel="nofollow" class="external text" href="https://www.wired.com/2015/11/googles-open-source-ai-tensorflow-signals-fast-changing-hardware-world/">"TensorFlow, Google's Open Source AI, Points to a Fast-Changing Hardware World"</a>. <i>Wired</i><span class="reference-accessdate">. Retrieved <span class="nowrap">November 11,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=article&amp;rft.jtitle=Wired&amp;rft.atitle=TensorFlow%2C+Google%27s+Open+Source+AI%2C+Points+to+a+Fast-Changing+Hardware+World&amp;rft.date=2015-11-10&amp;rft.aulast=Metz&amp;rft.aufirst=Cade&amp;rft_id=https%3A%2F%2Fwww.wired.com%2F2015%2F11%2Fgoogles-open-source-ai-tensorflow-signals-fast-changing-hardware-world%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-1500repo.27s-11"><span class="mw-cite-backlink"><b><a href="#cite_ref-1500repo.27s_11-0">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://www.youtube.com/watch?v=Rnm83GqgqPE">Machine Learning: Google I/O 2016 Minute 07:30/44:44</a> accessdate=2016-06-05</span></li>
<li id="cite_note-12"><span class="mw-cite-backlink"><b><a href="#cite_ref-12">^</a></b></span> <span class="reference-text"><cite class="citation web">Jouppi, Norm. <a rel="nofollow" class="external text" href="https://cloudplatform.googleblog.com/2016/05/Google-supercharges-machine-learning-tasks-with-custom-chip.html">"Google supercharges machine learning tasks with TPU custom chip"</a>. <i>Google Cloud Platform Blog</i><span class="reference-accessdate">. Retrieved <span class="nowrap">May 19,</span> 2016</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Google+Cloud+Platform+Blog&amp;rft.atitle=Google+supercharges+machine+learning+tasks+with+TPU+custom+chip&amp;rft.aulast=Jouppi&amp;rft.aufirst=Norm&amp;rft_id=https%3A%2F%2Fcloudplatform.googleblog.com%2F2016%2F05%2FGoogle-supercharges-machine-learning-tasks-with-custom-chip.html&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-13"><span class="mw-cite-backlink"><b><a href="#cite_ref-13">^</a></b></span> <span class="reference-text"><cite class="citation news"><a rel="nofollow" class="external text" href="https://www.blog.google/topics/google-cloud/google-cloud-offer-tpus-machine-learning/">"Build and train machine learning models on our new Google Cloud TPUs"</a>. <i>Google</i>. May 17, 2017<span class="reference-accessdate">. Retrieved <span class="nowrap">May 18,</span> 2017</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=article&amp;rft.jtitle=Google&amp;rft.atitle=Build+and+train+machine+learning+models+on+our+new+Google+Cloud+TPUs&amp;rft.date=2017-05-17&amp;rft_id=https%3A%2F%2Fwww.blog.google%2Ftopics%2Fgoogle-cloud%2Fgoogle-cloud-offer-tpus-machine-learning%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-14"><span class="mw-cite-backlink"><b><a href="#cite_ref-14">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://www.theverge.com/2017/5/17/15645908/google-ai-tensorflowlite-machine-learning-announcement-io-2017">Google’s new machine learning framework is going to put more AI on your phone</a></span></li>
<li id="cite_note-Byrne-15"><span class="mw-cite-backlink"><b><a href="#cite_ref-Byrne_15-0">^</a></b></span> <span class="reference-text"><cite class="citation web">Byrne, Michael (November 11, 2015). <a rel="nofollow" class="external text" href="http://motherboard.vice.com/en_uk/read/google-offers-up-its-entire-machine-learning-library-as-open-source">"Google Offers Up Its Entire Machine Learning Library as Open-Source Software"</a>. <i>Vice</i><span class="reference-accessdate">. Retrieved <span class="nowrap">November 11,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Vice&amp;rft.atitle=Google+Offers+Up+Its+Entire+Machine+Learning+Library+as+Open-Source+Software&amp;rft.date=2015-11-11&amp;rft.aulast=Byrne&amp;rft.aufirst=Michael&amp;rft_id=http%3A%2F%2Fmotherboard.vice.com%2Fen_uk%2Fread%2Fgoogle-offers-up-its-entire-machine-learning-library-as-open-source&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-Woollaston-16"><span class="mw-cite-backlink"><b><a href="#cite_ref-Woollaston_16-0">^</a></b></span> <span class="reference-text"><cite class="citation web">Woollaston, Victoria (November 25, 2015). <a rel="nofollow" class="external text" href="http://www.dailymail.co.uk/sciencetech/article-3311650/Google-releases-TensorFlow-Search-giant-makes-artificial-intelligence-software-available-public.html">"Google releases TensorFlow – Search giant makes its artificial intelligence software available to the public"</a>. <i>DailyMail</i><span class="reference-accessdate">. Retrieved <span class="nowrap">November 25,</span> 2015</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=DailyMail&amp;rft.atitle=Google+releases+TensorFlow+%E2%80%93+Search+giant+makes+its+artificial+intelligence+software+available+to+the+public&amp;rft.date=2015-11-25&amp;rft.aulast=Woollaston&amp;rft.aufirst=Victoria&amp;rft_id=http%3A%2F%2Fwww.dailymail.co.uk%2Fsciencetech%2Farticle-3311650%2FGoogle-releases-TensorFlow-Search-giant-makes-artificial-intelligence-software-available-public.html&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATensorFlow" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>

----------------------------------

### keras ref

- [keras.io](http://keras.io/) - Keras documentation
- [Getting started with the Sequential model](http://keras.io/getting-started/sequential-model-guide/)
- [Getting started with the functional API](http://keras.io/getting-started/functional-api-guide/)
- [Keras FAQ](http://keras.io/getting-started/faq/)
- [Quick start: the Iris dataset in Keras and scikit-learn](https://github.com/fastforwardlabs/keras-hello-world/blob/master/kerashelloworld.ipynb)
- [Using pre-trained word embeddings in a Keras model](http://blog.keras.io/using-pre-trained-word-embeddings-in-a-keras-model.html)
- [Building powerful image classification models using very little data](http://blog.keras.io/building-powerful-image-classification-models-using-very-little-data.html)
- [Building Autoencoders in Keras](http://blog.keras.io/building-autoencoders-in-keras.html)
- [A complete guide to using Keras as part of a TensorFlow workflow](http://blog.keras.io/keras-as-a-simplified-interface-to-tensorflow-tutorial.html)
- Introduction to Keras, from University of Waterloo: [video](https://www.youtube.com/watch?v=Tp3SaRbql4k) - [slides](https://uwaterloo.ca/data-science/sites/ca.data-science/files/uploads/files/keras_tutorial.pdf)
- Introduction to Deep Learning with Keras, from CERN: [video](http://cds.cern.ch/record/2157570?ln=en) - [slides](https://indico.cern.ch/event/506145/contributions/2132944/attachments/1258124/1858154/NNinKeras_MPaganini.pdf)
- [Installing Keras for deep learning](http://www.pyimagesearch.com/2016/07/18/installing-keras-for-deep-learning/)
- [Develop Your First Neural Network in Python With Keras Step-By-Step](http://machinelearningmastery.com/tutorial-first-neural-network-python-keras/)
- [Practical Neural Networks with Keras: Classifying Yelp Reviews](http://www.developintelligence.com/blog/2017/06/practical-neural-networks-keras-classifying-yelp-reviews/) (Shows basic classification and how to set up a GPU instance on AWS)
- [Understanding Stateful LSTM Recurrent Neural Networks in Python with Keras](http://machinelearningmastery.com/understanding-stateful-lstm-recurrent-neural-networks-python-keras/)
- [Time Series Prediction with LSTM Recurrent Neural Networks in Python with Keras](http://machinelearningmastery.com/time-series-prediction-lstm-recurrent-neural-networks-python-keras/)
- [Keras video tutorials from Dan Van Boxel](https://www.youtube.com/playlist?list=PLFxrZqbLojdKuK7Lm6uamegEFGW2wki6P)
- [Keras Deep Learning Tutorial for Kaggle 2nd Annual Data Science Bowl](https://github.com/jocicmarko/kaggle-dsb2-keras/)
- [Collection of tutorials setting up DNNs with Keras](http://ml4a.github.io/guides/)
- [Fast.AI - Practical Deep Learning For Coders, Part 1](http://course.fast.ai/) (great information on deep learning in general, heavily uses Keras for the labs)
- [Keras Tutorial: Content Based Image Retrieval Using a Convolutional Denoising Autoencoder](https://blog.sicara.com/keras-tutorial-content-based-image-retrieval-convolutional-denoising-autoencoder-dc91450cc511)
- [A Bit of Deep Learning and Keras](https://www.youtube.com/watch?v=UOEhojCzWrY&list=PLgJhDSE2ZLxaPX0jteHZG4skdj8ZrST9d): a multipart video introduction to deep learning and keras

-----------------------

### torch ref

<div class="reflist columns references-column-width" style="-moz-column-width: 30em; -webkit-column-width: 30em; column-width: 30em; list-style-type: decimal;">
<ol class="references">
<li id="cite_note-torch-modular-1"><span class="mw-cite-backlink"><b><a href="#cite_ref-torch-modular_1-0">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=CBB0C8A5FE34F6D6DAFF997F6B6A205A?doi=10.1.1.8.9850&amp;rep=rep1&amp;type=pdf">"Torch: a modular machine learning software library"</a>. 30 October 2002<span class="reference-accessdate">. Retrieved <span class="nowrap">24 April</span> 2014</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Torch%3A+a+modular+machine+learning+software+library&amp;rft.date=2002-10-30&amp;rft_id=http%3A%2F%2Fciteseerx.ist.psu.edu%2Fviewdoc%2Fdownload%3Bjsessionid%3DCBB0C8A5FE34F6D6DAFF997F6B6A205A%3Fdoi%3D10.1.1.8.9850%26rep%3Drep1%26type%3Dpdf&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATorch+%28machine+learning%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-2"><span class="mw-cite-backlink"><b><a href="#cite_ref-2">^</a></b></span> <span class="reference-text"><cite class="citation web">Collobert, Ronan. <a rel="nofollow" class="external text" href="http://torch.ch/">"Torch7"</a>. <i><a href="https://en.wikipedia.org/wiki/GitHub" title="GitHub">GitHub</a></i>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=GitHub&amp;rft.atitle=Torch7&amp;rft.aulast=Collobert&amp;rft.aufirst=Ronan&amp;rft_id=http%3A%2F%2Ftorch.ch%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATorch+%28machine+learning%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-nips-3"><span class="mw-cite-backlink"><b><a href="#cite_ref-nips_3-0">^</a></b></span> <span class="reference-text"><cite class="citation journal">Ronan Collobert; Koray Kavukcuoglu; Clement Farabet (2011). <a rel="nofollow" class="external text" href="http://ronan.collobert.com/pub/matos/2011_torch7_nipsw.pdf">"Torch7: A Matlab-like Environment for Machine Learning"</a> <span style="font-size:85%;">(PDF)</span>. <i>Neural Information Processing Systems</i>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=article&amp;rft.jtitle=Neural+Information+Processing+Systems&amp;rft.atitle=Torch7%3A+A+Matlab-like+Environment+for+Machine+Learning&amp;rft.date=2011&amp;rft.au=Ronan+Collobert&amp;rft.au=Koray+Kavukcuoglu&amp;rft.au=Clement+Farabet&amp;rft_id=http%3A%2F%2Fronan.collobert.com%2Fpub%2Fmatos%2F2011_torch7_nipsw.pdf&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATorch+%28machine+learning%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-4"><span class="mw-cite-backlink"><b><a href="#cite_ref-4">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="http://www.kdnuggets.com/2014/02/exclusive-yann-lecun-deep-learning-facebook-ai-lab.html">KDnuggets Interview with Yann LeCun, Deep Learning Expert, Director of Facebook AI Lab</a></span></li>
<li id="cite_note-5"><span class="mw-cite-backlink"><b><a href="#cite_ref-5">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://news.ycombinator.com/item?id=7928738">Hacker News</a></span></li>
<li id="cite_note-6"><span class="mw-cite-backlink"><b><a href="#cite_ref-6">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://www.facebook.com/yann.lecun/posts/10152077631217143?comment_id=10152089275552143&amp;offset=0&amp;total_comments=6">Yann Lecun's Facebook Page</a></span></li>
<li id="cite_note-7"><span class="mw-cite-backlink"><b><a href="#cite_ref-7">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://www.idiap.ch/scientific-research/resources/torch">IDIAP Research Institute&#160;: Torch</a></span></li>
<li id="cite_note-8"><span class="mw-cite-backlink"><b><a href="#cite_ref-8">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://github.com/soumith/torch-android">Torch-android GitHub repository</a></span></li>
<li id="cite_note-9"><span class="mw-cite-backlink"><b><a href="#cite_ref-9">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://github.com/clementfarabet/torch-ios">Torch-ios GitHub repository</a></span></li>
<li id="cite_note-10"><span class="mw-cite-backlink"><b><a href="#cite_ref-10">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="http://pub.clement.farabet.net/ecvw11.pdf">NeuFlow: A Runtime Reconﬁgurable Dataﬂow Processor for Vision</a></span></li>
<li id="cite_note-11"><span class="mw-cite-backlink"><b><a href="#cite_ref-11">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://www.wired.com/2015/01/facebook-open-sources-trove-ai-tools/">"Facebook Open-Sources a Trove of AI Tools"</a>. <i><a href="https://en.wikipedia.org/wiki/Wired_(website)" class="mw-redirect" title="Wired (website)">Wired</a></i>. 16 January 2015.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Wired&amp;rft.atitle=Facebook+Open-Sources+a+Trove+of+AI+Tools&amp;rft.date=2015-01-16&amp;rft_id=https%3A%2F%2Fwww.wired.com%2F2015%2F01%2Ffacebook-open-sources-trove-ai-tools%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATorch+%28machine+learning%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
</ol>
</div>

### Pytorch ref

<ul>
<li><a href="http://pytorch.org/" target="_blank">http://pytorch.org/</a></li>
<li><a href="http://pytorch.org/docs/index.html" target="_blank">http://pytorch.org/docs/index.html</a></li>
<li><a href="https://hackernoon.com/how-is-pytorch-different-from-tensorflow-2c90f44747d6" target="_blank">https://hackernoon.com/how-is-pytorch-different-from-tensorflow-2c90f44747d6</a></li>
<li><a href="https://blog.paperspace.com/adversarial-autoencoders-with-pytorch/" target="_blank">https://blog.paperspace.com/adversarial-autoencoders-with-pytorch/</a></li>
<li><a href="https://devblogs.nvidia.com/parallelforall/recursive-neural-networks-pytorch/" target="_blank">https://devblogs.nvidia.com/parallelforall/recursive-neural-networks-pytorch/</a></li>
<li><a href="http://blog.outcome.io/pytorch-quick-start-classifying-an-image/" target="_blank">http://blog.outcome.io/pytorch-quick-start-classifying-an-image/</a></li>
<li><a href="https://github.com/ritchieng/the-incredible-pytorch" target="_blank">https://github.com/ritchieng/the-incredible-pytorch</a></li>
<li><a href="https://www.youtube.com/watch?v=nbJ-2G2GXL0" target="_blank">https://www.youtube.com/watch?v=nbJ-2G2GXL0</a></li>
<li><a href="https://www.youtube.com/watch?v=4RzoFWre44Y&amp;t=7s" target="_blank">https://www.youtube.com/watch?v=4RzoFWre44Y&amp;t=7s</a></li>
<li><a href="https://www.youtube.com/watch?v=hiIqRUseouQ" target="_blank">https://www.youtube.com/watch?v=hiIqRUseouQ</a></li>
<li><a href="https://github.com/PythonWorkshop/Intro-to-TensorFlow-and-PyTorch/blob/master/PyTorch Tutorial.ipynb" target="_blank">https://github.com/PythonWorkshop/Intro-to-TensorFlow-and-PyTorch/blob/master/PyTorch%20Tutorial.ipynb</a></li>
<li><a href="https://github.com/PythonWorkshop/Intro-to-TensorFlow-and-PyTorch" target="_blank">https://github.com/PythonWorkshop/Intro-to-TensorFlow-and-PyTorch</a></li>
<li><a href="https://github.com/pytorch/examples" target="_blank">https://github.com/pytorch/examples</a></li>
<li><a href="http://pytorch.org/tutorials/" target="_blank">http://pytorch.org/tutorials/</a></li>
<li><a href="http://pytorch.org/tutorials/beginner/blitz/autograd_tutorial.html" target="_blank">http://pytorch.org/tutorials/beginner/blitz/autograd_tutorial.html</a></li>
<li><a href="http://www.cs.toronto.edu/~rgrosse/courses/csc321_2017/tutorials/tut4.pdf" target="_blank">http://www.cs.toronto.edu/~rgrosse/courses/csc321_2017/tutorials/tut4.pdf</a></li>
<li><a href="http://www.cs.toronto.edu/~rgrosse/courses/csc321_2017/slides/lec1.pdf" target="_blank">http://www.cs.toronto.edu/~rgrosse/courses/csc321_2017/slides/lec1.pdf</a></li>
<li><a href="https://discuss.pytorch.org/t/understanding-loss-function-gradients/771/5" target="_blank">https://discuss.pytorch.org/t/understanding-loss-function-gradients/771/5</a></li>
<li><a href="https://discuss.pytorch.org/t/visual-watcher-when-training-evaluating-or-tensorboard-equivalence/146/8" target="_blank">https://discuss.pytorch.org/t/visual-watcher-when-training-evaluating-or-tensorboard-equivalence/146/8</a></li>
<li><a href="https://github.com/jcjohnson/pytorch-examples" target="_blank">https://github.com/jcjohnson/pytorch-examples</a></li>
<li><a href="https://discuss.pytorch.org/t/print-autograd-graph/692/8" target="_blank">https://discuss.pytorch.org/t/print-autograd-graph/692/8</a></li>
<li><a href="https://discuss.pytorch.org/t/print-autograd-graph/692" target="_blank">https://discuss.pytorch.org/t/print-autograd-graph/692</a></li>
<li><a href="https://github.com/szagoruyko/functional-zoo/blob/master/visualize.py" target="_blank">https://github.com/szagoruyko/functional-zoo/blob/master/visualize.py</a></li>
<li><a href="https://github.com/szagoruyko/functional-zoo/blob/master/resnet-18-export.ipynb" target="_blank">https://github.com/szagoruyko/functional-zoo/blob/master/resnet-18-export.ipynb</a></li>
<li><a href="https://www.safaribooksonline.com/library/view/strata-hadoop/9781491976166/video302404.html" target="_blank">https://www.safaribooksonline.com/library/view/strata-hadoop/9781491976166/video302404.html</a></li>
<li><a href="https://discuss.pytorch.org/t/build-your-own-loss-function-in-pytorch/235" target="_blank">https://discuss.pytorch.org/t/build-your-own-loss-function-in-pytorch/235</a></li>
<li><a href="http://pytorch.org/docs/notes/extending.html#extending-torch-autograd" target="_blank">http://pytorch.org/docs/notes/extending.html#extending-torch-autograd</a></li>
<li><a href="http://blog.gaurav.im/2017/04/24/a-gentle-intro-to-pytorch/" target="_blank">http://blog.gaurav.im/2017/04/24/a-gentle-intro-to-pytorch/</a></li>
<li><a href="https://stackoverflow.com/questions/41924453/pytorch-how-to-use-dataloaders-for-custom-datasets" target="_blank">https://stackoverflow.com/questions/41924453/pytorch-how-to-use-dataloaders-for-custom-datasets</a></li>
<li><a href="https://discuss.pytorch.org/t/saving-and-loading-a-model-in-pytorch/2610/3" target="_blank">https://discuss.pytorch.org/t/saving-and-loading-a-model-in-pytorch/2610/3</a></li>
<li><a href="https://discuss.pytorch.org/t/load-a-saved-model/109" target="_blank">https://discuss.pytorch.org/t/load-a-saved-model/109</a></li>
<li><a href="https://discuss.pytorch.org/t/saving-torch-models/838" target="_blank">https://discuss.pytorch.org/t/saving-torch-models/838</a></li>
<li><a href="https://discuss.pytorch.org/t/saving-custom-models/621/4" target="_blank">https://discuss.pytorch.org/t/saving-custom-models/621/4</a></li>
<li><a href="https://github.com/jcjohnson/pytorch-examples" target="_blank">https://github.com/jcjohnson/pytorch-examples</a></li>
<li><a href="https://discuss.pytorch.org/t/build-your-own-loss-function-in-pytorch/235/19" target="_blank">https://discuss.pytorch.org/t/build-your-own-loss-function-in-pytorch/235/19</a></li>
<li><a href="https://github.com/pytorch/examples/blob/master/imagenet/main.py" target="_blank">https://github.com/pytorch/examples/blob/master/imagenet/main.py</a></li>
<li><a href="https://github.com/pytorch/examples/blob/master/mnist/main.py" target="_blank">https://github.com/pytorch/examples/blob/master/mnist/main.py</a></li>
<li><a href="https://discuss.pytorch.org/t/discussion-about-datasets-and-dataloaders/296" target="_blank">https://discuss.pytorch.org/t/discussion-about-datasets-and-dataloaders/296</a></li>
<li><a href="https://www.kaggle.com/mratsim/starting-kit-for-pytorch-deep-learning" target="_blank">https://www.kaggle.com/mratsim/starting-kit-for-pytorch-deep-learning</a></li>
<li><a href="https://iamtrask.github.io/2017/01/15/pytorch-tutorial/" target="_blank">https://iamtrask.github.io/2017/01/15/pytorch-tutorial/</a></li>
</ul>


-----------------------

### caffe ref


<div class="reflist" style="list-style-type: decimal;">
<div class="mw-references-wrap mw-references-columns">
<ol class="references">
<li id="cite_note-1"><span class="mw-cite-backlink"><b><a href="#cite_ref-1">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://github.com/BVLC/caffe/releases/tag/1.0">"Release 1.0"</a>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Release+1.0&amp;rft_id=https%3A%2F%2Fgithub.com%2FBVLC%2Fcaffe%2Freleases%2Ftag%2F1.0&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-2"><span class="mw-cite-backlink"><b><a href="#cite_ref-2">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://github.com/Microsoft/caffe">"Microsoft/caffe"</a>. <i>GitHub</i>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=GitHub&amp;rft.atitle=Microsoft%2Fcaffe&amp;rft_id=https%3A%2F%2Fgithub.com%2FMicrosoft%2Fcaffe&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-3"><span class="mw-cite-backlink"><b><a href="#cite_ref-3">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://github.com/BVLC/caffe/blob/master/LICENSE">"caffe/LICENSE at master"</a>. <i>GitHub</i>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=GitHub&amp;rft.atitle=caffe%2FLICENSE+at+master&amp;rft_id=https%3A%2F%2Fgithub.com%2FBVLC%2Fcaffe%2Fblob%2Fmaster%2FLICENSE&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-4"><span class="mw-cite-backlink"><b><a href="#cite_ref-4">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://github.com/BVLC/caffe/">"BVLC/caffe"</a>. <i>GitHub</i>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=GitHub&amp;rft.atitle=BVLC%2Fcaffe&amp;rft_id=https%3A%2F%2Fgithub.com%2FBVLC%2Fcaffe%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-5"><span class="mw-cite-backlink"><b><a href="#cite_ref-5">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://deeplearning4j.org/compare-dl4j-torch7-pylearn#caffe">"Comparing Frameworks: Deeplearning4j, Torch, Theano, TensorFlow, Caffe, Paddle, MxNet, Keras &amp; CNTK"</a>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Comparing+Frameworks%3A+Deeplearning4j%2C+Torch%2C+Theano%2C+TensorFlow%2C+Caffe%2C+Paddle%2C+MxNet%2C+Keras+%26+CNTK&amp;rft_id=https%3A%2F%2Fdeeplearning4j.org%2Fcompare-dl4j-torch7-pylearn%23caffe&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-6"><span class="mw-cite-backlink"><b><a href="#cite_ref-6">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="http://www.embedded-vision.com/industry-analysis/technical-articles/caffe-deep-learning-framework-interview-core-developers">"The Caffe Deep Learning Framework: An Interview with the Core Developers"</a>. Embedded Vision.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=The+Caffe+Deep+Learning+Framework%3A+An+Interview+with+the+Core+Developers&amp;rft.pub=Embedded+Vision&amp;rft_id=http%3A%2F%2Fwww.embedded-vision.com%2Findustry-analysis%2Ftechnical-articles%2Fcaffe-deep-learning-framework-interview-core-developers&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-7"><span class="mw-cite-backlink"><b><a href="#cite_ref-7">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://github.com/BVLC/caffe">"Caffe: a fast open framework for deep learning"</a>. GitHub.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Caffe%3A+a+fast+open+framework+for+deep+learning.&amp;rft.pub=GitHub&amp;rft_id=https%3A%2F%2Fgithub.com%2FBVLC%2Fcaffe&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-8"><span class="mw-cite-backlink"><b><a href="#cite_ref-8">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://web.archive.org/web/20170405073658/https://vision.princeton.edu/courses/COS598/2015sp/slides/Caffe/caffe_tutorial.pdf">"Caffe tutorial - vision.princeton.edu"</a> <span style="font-size:85%;">(PDF)</span>. Archived from <a rel="nofollow" class="external text" href="https://vision.princeton.edu/courses/COS598/2015sp/slides/Caffe/caffe_tutorial.pdf">the original</a> <span style="font-size:85%;">(PDF)</span> on April 5, 2017.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Caffe+tutorial+-+vision.princeton.edu&amp;rft_id=https%3A%2F%2Fvision.princeton.edu%2Fcourses%2FCOS598%2F2015sp%2Fslides%2FCaffe%2Fcaffe_tutorial.pdf&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-9"><span class="mw-cite-backlink"><b><a href="#cite_ref-9">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://devblogs.nvidia.com/parallelforall/deep-learning-computer-vision-caffe-cudnn/">"Deep Learning for Computer Vision with Caffe and cuDNN"</a>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Deep+Learning+for+Computer+Vision+with+Caffe+and+cuDNN&amp;rft_id=https%3A%2F%2Fdevblogs.nvidia.com%2Fparallelforall%2Fdeep-learning-computer-vision-caffe-cudnn%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-10"><span class="mw-cite-backlink"><b><a href="#cite_ref-10">^</a></b></span> <span class="reference-text"><cite class="citation news"><a rel="nofollow" class="external text" href="https://jaxenter.com/yahoo-enters-artificial-intelligence-race-with-caffeonspark-124324.html">"Yahoo enters artificial intelligence race with CaffeOnSpark"</a>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=article&amp;rft.atitle=Yahoo+enters+artificial+intelligence+race+with+CaffeOnSpark&amp;rft_id=https%3A%2F%2Fjaxenter.com%2Fyahoo-enters-artificial-intelligence-race-with-caffeonspark-124324.html&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-11"><span class="mw-cite-backlink"><b><a href="#cite_ref-11">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="http://caffe2.ai/blog/2017/04/18/caffe2-open-source-announcement.html">"Caffe2 Open Source Brings Cross Platform Machine Learning Tools to Developers"</a>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Caffe2+Open+Source+Brings+Cross+Platform+Machine+Learning+Tools+to+Developers&amp;rft_id=http%3A%2F%2Fcaffe2.ai%2Fblog%2F2017%2F04%2F18%2Fcaffe2-open-source-announcement.html&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ACaffe+%28software%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
</ol>
</div>
</div>

-----------------------------

### mxnet ref

<div class="mw-references-wrap">
<ol class="references">
<li id="cite_note-1"><span class="mw-cite-backlink"><b><a href="#cite_ref-1">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://blogs.technet.microsoft.com/machinelearning/2016/09/15/building-deep-neural-networks-in-the-cloud-with-azure-gpu-vms-mxnet-and-microsoft-r-server/">"Building Deep Neural Networks in the Cloud with Azure GPU VMs, MXNet and Microsoft R Server"</a><span class="reference-accessdate">. Retrieved <span class="nowrap">13 May</span> 2017</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Building+Deep+Neural+Networks+in+the+Cloud+with+Azure+GPU+VMs%2C+MXNet+and+Microsoft+R+Server&amp;rft_id=https%3A%2F%2Fblogs.technet.microsoft.com%2Fmachinelearning%2F2016%2F09%2F15%2Fbuilding-deep-neural-networks-in-the-cloud-with-azure-gpu-vms-mxnet-and-microsoft-r-server%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3AMXNet" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-2"><span class="mw-cite-backlink"><b><a href="#cite_ref-2">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://aws.amazon.com/mxnet/">"Apache MXNet on AWS - Deep Learning on the Cloud"</a>. <i>Amazon Web Services, Inc</i><span class="reference-accessdate">. Retrieved <span class="nowrap">13 May</span> 2017</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Amazon+Web+Services%2C+Inc.&amp;rft.atitle=Apache+MXNet+on+AWS+-+Deep+Learning+on+the+Cloud&amp;rft_id=https%3A%2F%2Faws.amazon.com%2Fmxnet%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3AMXNet" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-3"><span class="mw-cite-backlink"><b><a href="#cite_ref-3">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://blogs.technet.microsoft.com/machinelearning/2016/09/15/building-deep-neural-networks-in-the-cloud-with-azure-gpu-vms-mxnet-and-microsoft-r-server/">"Building Deep Neural Networks in the Cloud with Azure GPU VMs, MXNet and Microsoft R Server"</a>. <i>Microsoft TechNet Blogs</i><span class="reference-accessdate">. Retrieved <span class="nowrap">6 September</span> 2017</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Microsoft+TechNet+Blogs&amp;rft.atitle=Building+Deep+Neural+Networks+in+the+Cloud+with+Azure+GPU+VMs%2C+MXNet+and+Microsoft+R+Server.&amp;rft_id=https%3A%2F%2Fblogs.technet.microsoft.com%2Fmachinelearning%2F2016%2F09%2F15%2Fbuilding-deep-neural-networks-in-the-cloud-with-azure-gpu-vms-mxnet-and-microsoft-r-server%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3AMXNet" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-4"><span class="mw-cite-backlink"><b><a href="#cite_ref-4">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="http://www.allthingsdistributed.com/2016/11/mxnet-default-framework-deep-learning-aws.html">"MXNet - Deep Learning Framework of Choice at AWS - All Things Distributed"</a>. <i>www.allthingsdistributed.com</i><span class="reference-accessdate">. Retrieved <span class="nowrap">13 May</span> 2017</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=www.allthingsdistributed.com&amp;rft.atitle=MXNet+-+Deep+Learning+Framework+of+Choice+at+AWS+-+All+Things+Distributed&amp;rft_id=http%3A%2F%2Fwww.allthingsdistributed.com%2F2016%2F11%2Fmxnet-default-framework-deep-learning-aws.html&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3AMXNet" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-5"><span class="mw-cite-backlink"><b><a href="#cite_ref-5">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="http://fortune.com/2016/11/22/amazon-deep-learning-mxnet/">"Amazon Has Chosen This Framework to Guide Deep Learning Strategy"</a>. <i>Fortune</i><span class="reference-accessdate">. Retrieved <span class="nowrap">13 May</span> 2017</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Fortune&amp;rft.atitle=Amazon+Has+Chosen+This+Framework+to+Guide+Deep+Learning+Strategy&amp;rft_id=http%3A%2F%2Ffortune.com%2F2016%2F11%2F22%2Famazon-deep-learning-mxnet%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3AMXNet" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-6"><span class="mw-cite-backlink"><b><a href="#cite_ref-6">^</a></b></span> <span class="reference-text"><cite class="citation news"><a rel="nofollow" class="external text" href="http://techgenix.com/mxnet-amazon-apache-incubator/">"MXNet, Amazon's deep learning framework, gets accepted into Apache Incubator"</a><span class="reference-accessdate">. Retrieved <span class="nowrap">2017-03-08</span></span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=article&amp;rft.atitle=MXNet%2C+Amazon%E2%80%99s+deep+learning+framework%2C+gets+accepted+into+Apache+Incubator&amp;rft_id=http%3A%2F%2Ftechgenix.com%2Fmxnet-amazon-apache-incubator%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3AMXNet" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-7"><span class="mw-cite-backlink"><b><a href="#cite_ref-7">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://www.cs.cmu.edu/~muli/file/parameter_server_osdi14.pdf">"Scaling Distributed Machine Learning with the Parameter Server"</a> <span style="font-size:85%;">(PDF)</span><span class="reference-accessdate">. Retrieved <span class="nowrap">2014-10-08</span></span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Scaling+Distributed+Machine+Learning+with+the+Parameter+Server&amp;rft_id=https%3A%2F%2Fwww.cs.cmu.edu%2F~muli%2Ffile%2Fparameter_server_osdi14.pdf&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3AMXNet" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
</ol>
</div>



--------------------------

### DL on web ref

<ul>
<li><a rel="nofollow" class="external text" href="https://github.com/showcases/machine-learning">GitHub machine learning showcase</a></li>
<li><a rel="nofollow" class="external text" href="http://www.kdnuggets.com/2015/06/popular-deep-learning-tools.html">Popular Deep Learning Tools – a review</a></li>
<li><a rel="nofollow" class="external text" href="http://www.kdnuggets.com/2015/12/deep-learning-tools.html">50 Deep Learning Software Tools and Platforms</a></li>
<li><a rel="nofollow" class="external text" href="https://github.com/DL-Benchmarks/DL-Benchmarks">Comparative study of Caffe, Neon, TensorFlow, Theano, and Torch</a></li>
<li><a rel="nofollow" class="external text" href="http://deeplearning.net/software_links/">Software links</a></li>
<li><a rel="nofollow" class="external text" href="http://www.teglor.com/b/deep-learning-libraries-language-cm569/">Deep Learning Libraries by Language</a></li>
<li><a rel="nofollow" class="external text" href="http://deeplearning4j.org/compare-dl4j-torch7-pylearn.html">DL4J vs. Torch vs. Theano vs. Caffe vs. TensorFlow</a></li>
<li><a rel="nofollow" class="external text" href="https://github.com/zer0n/deepframeworks/blob/master/README.md">Evaluation of Deep Learning Toolkits</a>, an evaluation of Caffe, CNTK, TensorFlow, Theano, and Torch with ratings on different aspects</li>
<li><a rel="nofollow" class="external text" href="https://www.youtube.com/watch?v=Vf_-OkqbwPo">YouTube: CS231n Winter 2016: Lecture 12: Deep Learning libraries</a> – A comparison of Caffe, Torch, Theano and Tensorflow</li>
<li><a rel="nofollow" class="external text" href="http://blog.apcelent.com/most-popular-deep-learning-library-2015.html">10 Most Popular Deep Learning Libraries Started in 2015</a></li>
<li><a rel="nofollow" class="external text" href="http://www.infoworld.com/article/3026262/data-science/13-framewoks-for-mastering-machine-learning.html">13 frameworks for mastering machine learning</a></li>
<li><a rel="nofollow" class="external text" href="https://venturebeat.com/2015/11/14/deep-learning-frameworks/">Want an open-source deep learning framework? Take your pick</a></li>
<li><a rel="nofollow" class="external text" href="https://www.quora.com/What-is-the-best-deep-learning-library-at-the-current-stage-for-working-on-large-data">What is the best deep learning library at the current stage for working on large data?</a></li>
<li><a rel="nofollow" class="external text" href="https://github.com/josephmisiti/awesome-machine-learning">Awesome Machine Learning</a> – A large list of machine learning frameworks, libraries and software by language</li>
<li><a rel="nofollow" class="external text" href="http://www.datasciencecentral.com/profiles/blogs/here-are-15-libraries-in-various-languages-to-help-implement-your">15 Deep Learning Libraries</a> – 15 libraries in various languages</li>
<li><a rel="nofollow" class="external text" href="https://esciencegroup.com/2016/02/08/tensorflow-meets-microsofts-cntk/">TensorFlow Meets Microsoft’s CNTK</a> – Comparison of <a href="https://en.wikipedia.org/wiki/TensorFlow" title="TensorFlow">TensorFlow</a> and <a href="https://en.wikipedia.org/wiki/CNTK" class="mw-redirect" title="CNTK">CNTK</a></li>
<li><a rel="nofollow" class="external text" href="https://developer.nvidia.com/deep-learning-frameworks">Deep Learning Frameworks</a> – Short list of deep learning frameworks recommended by <a href="https://en.wikipedia.org/wiki/Nvidia" title="Nvidia">Nvidia</a></li>
<li><a rel="nofollow" class="external text" href="https://github.com/jtoy/awesome-tensorflow#libraries">Awesome TensorFlow – Libraries</a></li>
<li><a rel="nofollow" class="external text" href="http://deep-learning.sg.tn/index.php/2-non-categorise/5-popular-deep-learning-libraries">Popular Deep Learning Libraries</a></li>
</ul>

------------

### List of all specilized ai projects

<h3><span class="mw-headline" id="Brain-inspired">Brain-inspired</span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Blue_Brain_Project" title="Blue Brain Project">Blue Brain Project</a>, an attempt to create a synthetic brain by <a href="https://en.wikipedia.org/wiki/Reverse_engineering" title="Reverse engineering">reverse-engineering</a> the mammalian brain down to the molecular level.</li>
<li><a href="https://en.wikipedia.org/wiki/Google_Brain" title="Google Brain">Google Brain</a> A deep learning project part of <a href="https://en.wikipedia.org/wiki/Google_X" class="mw-redirect" title="Google X">Google X</a> attempting to have intelligence similar or equal to human-level.</li>
<li><a href="https://en.wikipedia.org/wiki/Numenta#The_NuPIC_Open_Source_Project" title="Numenta">NuPIC</a>, an open source implementation by <a href="https://en.wikipedia.org/wiki/Numenta" title="Numenta">Numenta</a> of its cortical learning algorithm.</li>
</ul>
<h3><span class="mw-headline" id="Cognitive_architectures">Cognitive architectures</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/4CAPS" title="4CAPS">4CAPS</a>, developed at <a href="https://en.wikipedia.org/wiki/Carnegie_Mellon_University" title="Carnegie Mellon University">Carnegie Mellon University</a> under <a href="https://en.wikipedia.org/wiki/Marcel_Just" title="Marcel Just">Marcel A. Just</a></li>
<li><a href="https://en.wikipedia.org/wiki/ACT-R" title="ACT-R">ACT-R</a>, developed at Carnegie Mellon University under <a href="https://en.wikipedia.org/wiki/John_Robert_Anderson_(psychologist)" title="John Robert Anderson (psychologist)">John R. Anderson</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/AIXI" title="AIXI">AIXI</a>, Universal Artificial Intelligence developed by <a href="https://en.wikipedia.org/wiki/Marcus_Hutter" title="Marcus Hutter">Marcus Hutter</a> at <a href="https://en.wikipedia.org/wiki/IDSIA" class="mw-redirect" title="IDSIA">IDSIA</a> and <a href="https://en.wikipedia.org/wiki/Australian_National_University" title="Australian National University">ANU</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/CALO" title="CALO">CALO</a>, a DARPA-funded, 25-institution effort to integrate many <a href="https://en.wikipedia.org/wiki/Artificial_intelligence" title="Artificial intelligence">artificial intelligence</a> approaches (<a href="https://en.wikipedia.org/wiki/Natural_language_processing" title="Natural language processing">natural language processing</a>, <a href="https://en.wikipedia.org/wiki/Speech_recognition" title="Speech recognition">speech recognition</a>, <a href="https://en.wikipedia.org/wiki/Machine_vision" title="Machine vision">machine vision</a>, <a href="https://en.wikipedia.org/wiki/Probabilistic_logic" title="Probabilistic logic">probabilistic logic</a>, <a href="https://en.wikipedia.org/wiki/Planning" title="Planning">planning</a>, <a href="https://en.wikipedia.org/wiki/Reasoning" class="mw-redirect" title="Reasoning">reasoning</a>, many forms of <a href="https://en.wikipedia.org/wiki/Machine_learning" title="Machine learning">machine learning</a>) into an AI assistant that learns to help manage your office environment.</li>
<li><a href="https://en.wikipedia.org/wiki/CHREST" title="CHREST">CHREST</a>, developed under <a href="https://en.wikipedia.org/wiki/Fernand_Gobet" title="Fernand Gobet">Fernand Gobet</a> at <a href="https://en.wikipedia.org/wiki/Brunel_University" class="mw-redirect" title="Brunel University">Brunel University</a> and Peter C. Lane at the <a href="https://en.wikipedia.org/wiki/University_of_Hertfordshire" title="University of Hertfordshire">University of Hertfordshire</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/CLARION_(cognitive_architecture)" title="CLARION (cognitive architecture)">CLARION</a> the cognitive architecture, developed under <a href="https://en.wikipedia.org/wiki/Ron_Sun" title="Ron Sun">Ron Sun</a> at <a href="https://en.wikipedia.org/wiki/Rensselaer_Polytechnic_Institute" title="Rensselaer Polytechnic Institute">Rensselaer Polytechnic Institute</a> and University of Missouri.</li>
<li><a href="https://en.wikipedia.org/wiki/JACK_Intelligent_Agents" title="JACK Intelligent Agents">CoJACK</a>, an <a href="https://en.wikipedia.org/wiki/ACT-R" title="ACT-R">ACT-R</a> inspired extension to the JACK multi-agent system that adds a cognitive architecture to the agents for eliciting more realistic (human-like) behaviors in virtual environments.</li>
<li><a href="https://en.wikipedia.org/wiki/Copycat_(software)" title="Copycat (software)">Copycat</a>, by <a href="https://en.wikipedia.org/wiki/Douglas_Hofstadter" title="Douglas Hofstadter">Douglas Hofstadter</a> and <a href="https://en.wikipedia.org/wiki/Melanie_Mitchell" title="Melanie Mitchell">Melanie Mitchell</a> at the <a href="/wiki/Indiana_University_(Bloomington)" class="mw-redirect" title="Indiana University (Bloomington)">Indiana University</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/DUAL_(cognitive_architecture)" title="DUAL (cognitive architecture)">DUAL</a>, developed at the <a href="https://en.wikipedia.org/wiki/New_Bulgarian_University" title="New Bulgarian University">New Bulgarian University</a> under <a href="https://en.wikipedia.org/wiki/Boicho_Kokinov" title="Boicho Kokinov">Boicho Kokinov</a>.</li>
<li>EPIC, developed under David E. Kieras and David E. Meyer (both <a href="https://en.wikipedia.org/wiki/University_of_Michigan" title="University of Michigan">University of Michigan</a> Ph.D. graduates) at the <a href="https://en.wikipedia.org/wiki/University_of_Michigan" title="University of Michigan">University of Michigan</a>.</li>
<li>The H-Cogaff architecture, which is a special case of the CogAff schema; see Taylor &amp; Sayda, and Sloman refs below.</li>
<li><a href="https://en.wikipedia.org/wiki/FORR" title="FORR">FORR</a> developed by Susan L. Epstein at <a href="https://en.wikipedia.org/wiki/The_City_University_of_New_York" class="mw-redirect" title="The City University of New York">The City University of New York</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/LIDA_(cognitive_architecture)" title="LIDA (cognitive architecture)">IDA and LIDA</a>, implementing <a href="https://en.wikipedia.org/wiki/Global_Workspace_Theory" class="mw-redirect" title="Global Workspace Theory">Global Workspace Theory</a>, developed under <a href="https://en.wikipedia.org/wiki/Stan_Franklin" title="Stan Franklin">Stan Franklin</a> at the <a href="https://en.wikipedia.org/wiki/University_of_Memphis" title="University of Memphis">University of Memphis</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/OpenCog" title="OpenCog">OpenCog</a> Prime, developed using the OpenCog Framework.</li>
<li><a href="https://en.wikipedia.org/wiki/Procedural_Reasoning_System" class="mw-redirect" title="Procedural Reasoning System">Procedural Reasoning System</a> (PRS), developed by <a href="https://en.wikipedia.org/wiki/Michael_Georgeff" title="Michael Georgeff">Michael Georgeff</a> and <a href="https://en.wikipedia.org/wiki/Amy_L._Lansky" title="Amy L. Lansky">Amy L. Lansky</a> at <a href="https://en.wikipedia.org/wiki/SRI_International" title="SRI International">SRI International</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Psi-Theory" class="mw-redirect" title="Psi-Theory">Psi-Theory</a> developed under <a href="https://en.wikipedia.org/wiki/Dietrich_D%C3%B6rner" title="Dietrich Dörner">Dietrich Dörner</a> at the <a href="https://en.wikipedia.org/wiki/Otto-Friedrich_University" class="mw-redirect" title="Otto-Friedrich University">Otto-Friedrich University</a> in <a href="https://en.wikipedia.org/wiki/Bamberg" title="Bamberg">Bamberg</a>, <a href="https://en.wikipedia.org/wiki/Germany" title="Germany">Germany</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/R-CAST" title="R-CAST">R-CAST</a>, developed at the <a href="https://en.wikipedia.org/wiki/Pennsylvania_State_University" title="Pennsylvania State University">Pennsylvania State University</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Soar_(cognitive_architecture)" title="Soar (cognitive architecture)">Soar</a>, developed under <a href="https://en.wikipedia.org/wiki/Allen_Newell" title="Allen Newell">Allen Newell</a> and <a href="https://en.wikipedia.org/wiki/John_E._Laird" title="John E. Laird">John Laird</a> at <a href="https://en.wikipedia.org/wiki/Carnegie_Mellon_University" title="Carnegie Mellon University">Carnegie Mellon University</a> and the <a href="https://en.wikipedia.org/wiki/University_of_Michigan" title="University of Michigan">University of Michigan</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Society_of_mind" class="mw-redirect" title="Society of mind">Society of mind</a> and its successor the <a href="/wiki/Emotion_machine" class="mw-redirect" title="Emotion machine">Emotion machine</a> proposed by <a href="https://en.wikipedia.org/wiki/Marvin_Minsky" title="Marvin Minsky">Marvin Minsky</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Subsumption_architecture" title="Subsumption architecture">Subsumption architectures</a>, developed e.g. by <a href="https://en.wikipedia.org/wiki/Rodney_Brooks" title="Rodney Brooks">Rodney Brooks</a> (though it could be argued whether they are <i>cognitive</i>).</li>
</ul>
<h3><span class="mw-headline" id="Games">Games</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/AlphaGo" title="AlphaGo">AlphaGo</a>, software developed by <a href="https://en.wikipedia.org/wiki/Google" title="Google">Google</a> that plays the Chinese board game Go.</li>
<li><a href="https://en.wikipedia.org/wiki/Chinook_(draughts_player)" title="Chinook (draughts player)">Chinook</a>, a computer program that plays <a href="https://en.wikipedia.org/wiki/English_draughts" title="English draughts">English draughts</a>; the first to win the world champion title in the competition against humans.</li>
<li><a href="https://en.wikipedia.org/wiki/Deep_Blue_(chess_computer)" title="Deep Blue (chess computer)">Deep Blue</a>, a chess-playing computer developed by <a href="https://en.wikipedia.org/wiki/IBM" title="IBM">IBM</a> which beat <a href="https://en.wikipedia.org/wiki/Garry_Kasparov" title="Garry Kasparov">Garry Kasparov</a> in 1997.</li>
<li><a href="https://en.wikipedia.org/wiki/Stockfish_(chess)" title="Stockfish (chess)">Stockfish AI</a>, an open source chess engine currently ranked the highest in many <a href="https://en.wikipedia.org/wiki/Chess_engine#Ratings" title="Chess engine">computer chess rankings</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/FreeHAL" title="FreeHAL">FreeHAL</a>, a self-learning conversation simulator (<a href="https://en.wikipedia.org/wiki/Chatterbot" class="mw-redirect" title="Chatterbot">chatterbot</a>) which uses semantic nets to organize its knowledge to imitate a very close human behavior within conversations.</li>
<li><a href="https://en.wikipedia.org/wiki/TD-Gammon" title="TD-Gammon">TD-Gammon</a>, a program that learned to play world-class <a href="https://en.wikipedia.org/wiki/Backgammon" title="Backgammon">backgammon</a> partly by playing against itself (<a href="https://en.wikipedia.org/wiki/Temporal_difference_learning" title="Temporal difference learning">temporal difference learning</a> with <a href="https://en.wikipedia.org/wiki/Neural_network" class="mw-redirect" title="Neural network">neural networks</a>).</li>
</ul>
<h3><span class="mw-headline" id="Knowledge_and_reasoning">Knowledge and reasoning</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Braina" title="Braina">Braina</a>, an <a href="https://en.wikipedia.org/wiki/Intelligent_personal_assistant" class="mw-redirect" title="Intelligent personal assistant">intelligent personal assistant</a> application with a voice interface for <a href="https://en.wikipedia.org/wiki/Windows_OS" class="mw-redirect" title="Windows OS">Windows OS</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Cyc" title="Cyc">Cyc</a>, an attempt to assemble an <a href="https://en.wikipedia.org/wiki/Ontology_(information_science)" title="Ontology (information science)">ontology</a> and database of everyday knowledge, enabling <a href="https://en.wikipedia.org/wiki/Commonsense_reasoning" title="Commonsense reasoning">human-like reasoning</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Eurisko" title="Eurisko">Eurisko</a>, a language by <a href="https://en.wikipedia.org/wiki/Douglas_Lenat" title="Douglas Lenat">Douglas Lenat</a> for solving problems which consists of <a href="https://en.wikipedia.org/wiki/Heuristic_algorithm" class="mw-redirect" title="Heuristic algorithm">heuristics</a>, including some for how to use and change its heuristics.</li>
<li><a href="https://en.wikipedia.org/wiki/Google_Now" title="Google Now">Google Now</a>, an <a href="https://en.wikipedia.org/wiki/Intelligent_personal_assistant" class="mw-redirect" title="Intelligent personal assistant">intelligent personal assistant</a> with a voice interface in <a href="https://en.wikipedia.org/wiki/Google" title="Google">Google</a>'s <a href="https://en.wikipedia.org/wiki/Android_(operating_system)" title="Android (operating system)">Android</a> and <a href="https://en.wikipedia.org/wiki/Apple_Inc." title="Apple Inc.">Apple Inc.</a>'s <a href="https://en.wikipedia.org/wiki/IOS" title="IOS">iOS</a>, as well as <a href="https://en.wikipedia.org/wiki/Google_Chrome" title="Google Chrome">Google Chrome</a> web browser on personal computers.</li>
<li><a href="/w/index.php?title=James_(intelligent_assistant)&amp;action=edit&amp;redlink=1" class="new" title="James (intelligent assistant) (page does not exist)">James</a>, an <a href="https://en.wikipedia.org/wiki/Intelligent_personal_assistant" class="mw-redirect" title="Intelligent personal assistant">intelligent personal assistant</a> application that understand questions in several languages and with mixed languages in same question.</li>
<li><a href="https://en.wikipedia.org/wiki/Microsoft_Cortana" class="mw-redirect" title="Microsoft Cortana">Microsoft Cortana</a>, an <a href="https://en.wikipedia.org/wiki/Intelligent_personal_assistant" class="mw-redirect" title="Intelligent personal assistant">intelligent personal assistant</a> with a voice interface in <a href="https://en.wikipedia.org/wiki/Microsoft" title="Microsoft">Microsoft</a>'s various <a href="https://en.wikipedia.org/wiki/Windows_10_editions" title="Windows 10 editions">Windows 10 editions</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Mycin" title="Mycin">Mycin</a>, an early medical expert system.</li>
<li><a href="/w/index.php?title=Open_Assistant&amp;action=edit&amp;redlink=1" class="new" title="Open Assistant (page does not exist)">Open Assistant</a>, an evolving open source artificial intelligence agent able to interact in basic conversation and automate an increasing number of tasks.</li>
<li><a href="https://en.wikipedia.org/wiki/Open_Mind_Common_Sense" title="Open Mind Common Sense">Open Mind Common Sense</a>, a project based at the <a href="https://en.wikipedia.org/wiki/MIT_Media_Lab" title="MIT Media Lab">MIT Media Lab</a> to build a large common sense <a href="https://en.wikipedia.org/wiki/Knowledge_base" title="Knowledge base">knowledge base</a> from online contributions.</li>
<li><a href="https://en.wikipedia.org/wiki/P.A.N." title="P.A.N.">P.A.N.</a>, a publicly available text analyzer.</li>
<li><a href="https://en.wikipedia.org/wiki/Siri" title="Siri">Siri</a>, an <a href="https://en.wikipedia.org/wiki/Intelligent_personal_assistant" class="mw-redirect" title="Intelligent personal assistant">intelligent personal assistant</a> and <a href="https://en.wikipedia.org/wiki/Knowledge_Navigator" title="Knowledge Navigator">knowledge navigator</a> with a voice-interface in <a href="https://en.wikipedia.org/wiki/Apple_Inc." title="Apple Inc.">Apple Inc.</a>'s <a href="https://en.wikipedia.org/wiki/IOS" title="IOS">iOS</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/SNePS" title="SNePS">SNePS</a>, a simultaneously a <a href="https://en.wikipedia.org/wiki/Logic" title="Logic">logic</a>-based, <a href="/wiki/Frame_language" title="Frame language">frame</a>-based, and <a href="https://en.wikipedia.org/wiki/Semantic_network" title="Semantic network">network</a>-based knowledge representation, reasoning, and acting system.</li>
<li><a href="https://en.wikipedia.org/wiki/Viv_(software)" title="Viv (software)">Viv (software)</a> a new AI invented by the creators of <a href="https://en.wikipedia.org/wiki/Siri" title="Siri">Siri</a></li>
<li><a href="https://en.wikipedia.org/wiki/Holmes_(computer)" title="Holmes (computer)">Holmes</a> a new AI created by <a href="https://en.wikipedia.org/wiki/Wipro" title="Wipro">Wipro</a></li>
<li><a href="https://en.wikipedia.org/wiki/Watson_(computer)" title="Watson (computer)">Watson</a>, a <a href="https://en.wikipedia.org/wiki/Question_answering_system" class="mw-redirect" title="Question answering system">question answering system</a> developed by <a href="https://en.wikipedia.org/wiki/IBM" title="IBM">IBM</a>. Has played the <a href="https://en.wikipedia.org/wiki/Jeopardy!" title="Jeopardy!">Jeopardy!</a> game show.</li>
<li><a href="https://en.wikipedia.org/wiki/Wolfram_Alpha" title="Wolfram Alpha">Wolfram Alpha</a>, an online service that answers queries by computing the answer from structured data.</li>
</ul>
<h3><span class="mw-headline" id="Motion_and_manipulation">Motion and manipulation</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Cog_(project)" title="Cog (project)">Cog</a>, a robot developed by <a href="https://en.wikipedia.org/wiki/Massachusetts_Institute_of_Technology" title="Massachusetts Institute of Technology">MIT</a> to study theories of <a href="https://en.wikipedia.org/wiki/Cognitive_science" title="Cognitive science">cognitive science</a> and artificial intelligence, now discontinued.</li>
<li><a href="https://en.wikipedia.org/wiki/AIBO" title="AIBO">AIBO</a>, the robot pet for the home, grew out of Sony's Computer Science Laboratory (CSL).</li>
</ul>
<h3><span class="mw-headline" id="Music">Music</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Melomics" title="Melomics">Melomics</a>, a bioinspired technology for music composition and synthetisation of music, where computers do not mimic musicians, but develop their own style.</li>
</ul>
<h3><span class="mw-headline" id="Natural_language_processing">Natural language processing</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/AIML" title="AIML">AIML</a>, an <a href="https://en.wikipedia.org/wiki/XML" title="XML">XML</a> dialect for creating <a href="https://en.wikipedia.org/wiki/Natural_language" title="Natural language">natural language</a> software agents.</li>
<li><a rel="nofollow" class="external text" href="https://cwiki.apache.org/confluence/display/JOSHUA/Apache+Joshua+%28Incubating%29+Home">Apache Joshua</a>, a statistical machine translation decoder for phrase-based, hierarchical, and syntax-based machine translation, written in Java.</li>
<li><a href="https://en.wikipedia.org/wiki/Apache_Lucene" title="Apache Lucene">Apache Lucene</a>, a high-performance, full-featured text search engine library written entirely in Java.</li>
<li><a href="https://en.wikipedia.org/wiki/OpenNLP" class="mw-redirect" title="OpenNLP">Apache OpenNLP</a>, a machine learning based toolkit for the processing of natural language text. It supports the most common NLP tasks, such as tokenization, sentence segmentation, part-of-speech tagging, named entity extraction, chunking and parsing.</li>
<li><a href="https://en.wikipedia.org/wiki/Artificial_Linguistic_Internet_Computer_Entity" title="Artificial Linguistic Internet Computer Entity">Artificial Linguistic Internet Computer Entity</a> (A.L.I.C.E.), an award-winning <a href="https://en.wikipedia.org/wiki/Natural_language_processing" title="Natural language processing">natural language processing</a> <a href="https://en.wikipedia.org/wiki/Chatterbot" class="mw-redirect" title="Chatterbot">chatterbot</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Cleverbot" title="Cleverbot">Cleverbot</a>, successor to Jabberwacky, now with 170m lines of conversation, Deep Context, fuzziness and parallel processing.Cleverbot learns from around 2 million user interactions per month.</li>
<li><a href="https://en.wikipedia.org/wiki/ELIZA" title="ELIZA">ELIZA</a>, a famous 1966 computer program by <a href="https://en.wikipedia.org/wiki/Joseph_Weizenbaum" title="Joseph Weizenbaum">Joseph Weizenbaum</a>, which parodied <a href="/wiki/Person-centered_therapy" title="Person-centered therapy">person-centered therapy</a>.</li>
<li>InfoTame, a text analysis search engine originally developed by the <a href="https://en.wikipedia.org/wiki/KGB" title="KGB">KGB</a> for sorting communications intercepts.</li>
<li><a href="/wiki/Jabberwacky" title="Jabberwacky">Jabberwacky</a>, a chatterbot by <a href="https://en.wikipedia.org/wiki/Rollo_Carpenter" title="Rollo Carpenter">Rollo Carpenter</a>, aiming to simulate a natural human chat.</li>
<li><a href="https://en.wikipedia.org/wiki/Mycroft_(software)" title="Mycroft (software)">Mycroft</a>, a free and open-source intelligent personal assistant that uses a natural language user interface.</li>
<li><a href="https://en.wikipedia.org/wiki/PARRY" title="PARRY">PARRY</a>, another early chatterbot, written in 1972 by Kenneth Colby, attempting to simulate a paranoid schizophrenic.</li>
<li><a href="https://en.wikipedia.org/wiki/SHRDLU" title="SHRDLU">SHRDLU</a>, an early natural language processing computer program developed by <a href="/wiki/Terry_Winograd" title="Terry Winograd">Terry Winograd</a> at <a href="https://en.wikipedia.org/wiki/Massachusetts_Institute_of_Technology" title="Massachusetts Institute of Technology">MIT</a> from 1968 to 1970.</li>
<li><a href="/w/index.php?title=Snatchbot.me&amp;action=edit&amp;redlink=1" class="new" title="Snatchbot.me (page does not exist)">Snatchbot.me</a>, a 2015 start-up, aspire to 'crowd-source' AI in chatbots via the public creation of hundreds of thousands of chatbots.<sup id="cite_ref-1" class="reference"><a href="#cite_note-1">[1]</a></sup></li>
<li><a href="https://en.wikipedia.org/wiki/SYSTRAN" title="SYSTRAN">SYSTRAN</a>, a <a href="https://en.wikipedia.org/wiki/Machine_translation" title="Machine translation">machine translation</a> technology by a company of the same name, used by <a href="https://en.wikipedia.org/wiki/Yahoo!" title="Yahoo!">Yahoo!</a>, <a href="https://en.wikipedia.org/wiki/AltaVista" title="AltaVista">AltaVista</a> and <a href="https://en.wikipedia.org/wiki/Google" title="Google">Google</a>, among others.</li>
</ul>
<h3><span class="mw-headline" id="Other">Other</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Synthetic_Environment_for_Analysis_and_Simulations" title="Synthetic Environment for Analysis and Simulations">Synthetic Environment for Analysis and Simulations</a> (SEAS), a model of the real world used by <a href="https://en.wikipedia.org/wiki/Homeland_security" title="Homeland security">Homeland security</a> and the <a href="https://en.wikipedia.org/wiki/United_States_Department_of_Defense" title="United States Department of Defense">United States Department of Defense</a> that uses <a href="https://en.wikipedia.org/wiki/Simulation" title="Simulation">simulation</a> and AI to predict and evaluate future events and courses of action.<sup id="cite_ref-register_2-0" class="reference"><a href="#cite_note-register-2">[2]</a></sup></li>
</ul>
<h2><span class="mw-headline" id="Multipurpose_projects">Multipurpose projects</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Deeplearning4j" title="Deeplearning4j">Deeplearning4j</a>, an open-source, distributed <a href="https://en.wikipedia.org/wiki/Deep_learning" title="Deep learning">deep learning</a> framework written for the JVM.</li>
<li><a href="https://en.wikipedia.org/wiki/Apache_Mahout" title="Apache Mahout">Mahout</a>, a library of scalable <a href="https://en.wikipedia.org/wiki/Machine_learning" title="Machine learning">machine learning</a> algorithms.</li>
<li><a href="https://en.wikipedia.org/wiki/OpenNN" title="OpenNN">OpenNN</a>, a comprehensive C++ library implementing <a href="https://en.wikipedia.org/wiki/Neural_network" class="mw-redirect" title="Neural network">neural networks</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/TensorFlow" title="TensorFlow">TensorFlow</a>, an open-source software library for machine learning.</li>
<li><a href="https://en.wikipedia.org/wiki/Torch_(machine_learning)" title="Torch (machine learning)">Torch</a>, an open-source software library for machine learning.</li>
<li><a href="https://en.wikipedia.org/wiki/PyTorch" title="PyTorch">pyTorch</a>, an open-source Tensors and Dynamic neural networks in Python</li>
</ul>
<h3><span class="mw-headline" id="GUI_frameworks">GUI frameworks</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Neural_Designer" title="Neural Designer">Neural Designer</a>, a commercial <a href="https://en.wikipedia.org/wiki/Deep_learning" title="Deep learning">deep learning</a> tool for <a href="https://en.wikipedia.org/wiki/Predictive_analytics" title="Predictive analytics">predictive analytics</a>.</li>
<li><a href="https://en.wikipedia.org/wiki/Neuroph" title="Neuroph">Neuroph</a>, a Java <a href="https://en.wikipedia.org/wiki/Neural_network" class="mw-redirect" title="Neural network">neural network</a> framework.</li>
<li><a href="https://en.wikipedia.org/wiki/OpenCog" title="OpenCog">OpenCog</a>, a GPL-licensed framework for <a href="https://en.wikipedia.org/wiki/Artificial_intelligence" title="Artificial intelligence">artificial intelligence</a> written in C++, Python and Scheme.</li>
<li><a href="https://en.wikipedia.org/wiki/RapidMiner" title="RapidMiner">RapidMiner</a>, an environment for <a href="https://en.wikipedia.org/wiki/Machine_learning" title="Machine learning">machine learning</a> and <a href="https://en.wikipedia.org/wiki/Data_mining" title="Data mining">data mining</a>, now developed commercially.</li>
<li><a href="https://en.wikipedia.org/wiki/Weka_(machine_learning)" title="Weka (machine learning)">Weka</a>, a free implementation of many <a href="https://en.wikipedia.org/wiki/Machine_learning" title="Machine learning">machine learning</a> algorithms in Java.</li>
</ul>
<h3><span class="mw-headline" id="Cloud_services">Cloud services</span></span></h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Data_Applied" title="Data Applied">Data Applied</a>, a web based <a href="https://en.wikipedia.org/wiki/Data_mining" title="Data mining">data mining</a> environment.</li>
<li><a href="https://en.wikipedia.org/wiki/Grok_(company)" class="mw-redirect" title="Grok (company)">Grok</a>, a service that ingests data streams and creates actionable predictions in real time.</li>
<li><a rel="nofollow" class="external text" href="https://www.microsoft.com/cognitive-services">Microsoft Cognitive Services</a>, cloud-based APIs that you can embed into your apps for computer vision, <a href="https://en.wikipedia.org/wiki/Natural_language_processing" title="Natural language processing">NLP</a>, search, and more.</li>
<li><a href="https://en.wikipedia.org/wiki/Watson_(computer)" title="Watson (computer)">Watson</a>, a pilot service by <a href="https://en.wikipedia.org/wiki/IBM" title="IBM">IBM</a> to uncover and share data-driven insights, and to spur cognitive applications.</li>
</ul>


### list of dl libraries-wiki ref

<ul>
<li><a rel="nofollow" class="external text" href="https://github.com/dritchie/adnn">adnn</a> – Javascript neural networks</li>
<li><a rel="nofollow" class="external text" href="https://github.com/mila-udem/blocks">Blocks</a> – Theano framework for building and training neural networks</li>
<li><a rel="nofollow" class="external text" href="https://caffe2.ai/">Caffe2</a> – Deep learning framework built on <a href="https://en.wikipedia.org/wiki/Caffe_(software)" title="Caffe (software)">Caffe</a>, developed by <a href="https://en.wikipedia.org/wiki/Facebook" title="Facebook">Facebook</a> in cooperation with <a href="https://en.wikipedia.org/wiki/NVIDIA" class="mw-redirect" title="NVIDIA">NVIDIA</a>, <a href="https://en.wikipedia.org/wiki/Qualcomm" title="Qualcomm">Qualcomm</a>, <a href="https://en.wikipedia.org/wiki/Intel" title="Intel">Intel</a>, <a href="https://en.wikipedia.org/wiki/Amazon.com" class="mw-redirect" title="Amazon.com">Amazon</a>, and <a href="https://en.wikipedia.org/wiki/Microsoft" title="Microsoft">Microsoft</a></li>
<li><a rel="nofollow" class="external text" href="https://github.com/yahoo/CaffeOnSpark">CaffeOnSpark</a> – Scalable deep learning package running Caffe on <a href="https://en.wikipedia.org/wiki/Apache_Spark" title="Apache Spark">Spark</a> and <a href="https://en.wikipedia.org/wiki/Apache_Hadoop" title="Apache Hadoop">Hadoop</a> clusters with <a href="https://en.wikipedia.org/wiki/Peer-to-peer" title="Peer-to-peer">peer-to-peer</a> communication</li>
<li><a rel="nofollow" class="external text" href="http://arxiv.org/abs/1606.06234">CNNLab</a> – Deep learning framework using GPU and FPGA-based accelerators</li>
<li><a rel="nofollow" class="external text" href="http://cs.stanford.edu/people/karpathy/convnetjs/">ConvNetJS</a> – Javascript library for training deep learning models entirely in a web browser</li>
<li><a rel="nofollow" class="external text" href="https://github.com/rdevon/cortex">Cortex</a> – Theano-based deep learning toolbox for neuroimaging</li>
<li><a rel="nofollow" class="external text" href="https://developer.nvidia.com/cudnn">cuDNN</a> – Optimized deep learning computation primitives implemented in CUDA</li>
<li><a rel="nofollow" class="external text" href="https://sourceforge.net/projects/currennt/">CURRENNT</a> – CUDA-accelerated toolkit for deep Long Short-Term Memory (LSTM) RNN architectures supporting large data sets not fitting into main memory.</li>
<li><a rel="nofollow" class="external text" href="https://pjreddie.com/darknet/">Darknet</a> - Darknet is an open source neural network framework written in C and CUDA, and supports CPU and GPU computation.</li>
<li><a rel="nofollow" class="external text" href="https://github.com/hughperkins/DeepCL">DeepCL</a> – OpenCL library to train deep convolutional networks, with APIs for C++, Python and the command line</li>
<li><a rel="nofollow" class="external text" href="https://pair-code.github.io/deeplearnjs/">deeplearn.js</a> – Hardware-accelerated deep learning library for the web browser</li>
<li><a rel="nofollow" class="external text" href="http://deeplearningkit.org/">DeepLearningKit</a> – Open source deep learning framework for iOS, OS X and tvOS</li>
<li><a rel="nofollow" class="external text" href="https://github.com/rasmusbergpalm/DeepLearnToolbox">DeepLearnToolbox</a> – Matlab/Octave toolbox for deep learning (deprecated)</li>
<li><a rel="nofollow" class="external text" href="http://niclane.org/pubs/deepx_ipsn.pdf">DeepX</a> – Software accelerator for deep learning execution aimed towards mobile devices</li>
<li><a rel="nofollow" class="external text" href="https://github.com/zomux/deepy">deepy</a> – Extensible deep learning framework based on Theano</li>
<li><a rel="nofollow" class="external text" href="https://github.com/amznlabs/amazon-dsstne">DSSTNE</a> (Deep Scalable Sparse Tensor Network Engine) – <a href="https://en.wikipedia.org/wiki/Amazon.com" class="mw-redirect" title="Amazon.com">Amazon</a> developed library for building deep learning models</li>
<li><a rel="nofollow" class="external text" href="https://github.com/yandex/faster-rnnlm">Faster RNNLM (HS/NCE) toolkit</a> – An rnnlm implementation for training on huge datasets and very large vocabularies and usage in real-world ASR and MT problems</li>
<li><a rel="nofollow" class="external text" href="https://www.gnu.org/software/gneuralnetwork/">GNU Gneural Network</a> – GNU package which implements a programmable neural network</li>
<li><a rel="nofollow" class="external text" href="https://github.com/01org/idlf">IDLF</a> – <a href="https://en.wikipedia.org/wiki/Intel" title="Intel">Intel</a>® Deep Learning Framework; supports OpenCL (deprecated)</li>
<li>Intel <a href="https://en.wikipedia.org/wiki/Math_Kernel_Library" title="Math Kernel Library">Math Kernel Library</a> (Intel MKL), library of optimized math routines, including optimized deep learning computation primitives</li>
<li><a rel="nofollow" class="external text" href="http://keras.io/">Keras</a> – Deep Learning library for Theano and TensorFlow</li>
<li><a rel="nofollow" class="external text" href="http://lasagne.readthedocs.org/en/latest/">Lasagne</a> – Lightweight library to build and train neural networks in Theano</li>
<li><a rel="nofollow" class="external text" href="https://github.com/autumnai/leaf">Leaf</a> – "The Hacker's Machine Learning Engine"; supports OpenCL (official development suspended)</li>
<li><a rel="nofollow" class="external text" href="http://arxiv.org/abs/1605.02766">LightNet</a> – MATLAB-based environment for deep learning</li>
<li><a rel="nofollow" class="external text" href="http://www.vlfeat.org/matconvnet/">MatConvNet</a> – CNNs for MATLAB</li>
<li><a rel="nofollow" class="external text" href="https://github.com/abhinavvishnu/matex">MaTEx</a> – Distributed TensorFlow with MPI by <a href="https://en.wikipedia.org/wiki/PNNL" class="mw-redirect" title="PNNL">PNNL</a></li>
<li><a rel="nofollow" class="external text" href="https://github.com/pluskid/Mocha.jl">Mocha</a> – Deep learning framework for <a href="https://en.wikipedia.org/wiki/Julia_(programming_language)" title="Julia (programming language)">Julia</a>, inspired by Caffe</li>
<li><a rel="nofollow" class="external text" href="https://github.com/NervanaSystems/neon">neon</a> – Nervana's Python based Deep Learning framework</li>
<li><a rel="nofollow" class="external text" href="http://fr.mathworks.com/products/neural-network/">Neural Network Toolbox</a> – MATLAB toolbox for neural network creation, training and simulation</li>
<li><a rel="nofollow" class="external text" href="https://github.com/PaddlePaddle/paddle">PaddlePaddle</a> – "PArallel Distributed Deep LEarning", deep learning platform</li>
<li><a rel="nofollow" class="external text" href="https://github.com/purine/purine2">Purine</a> – Bi-graph based deep learning framework</li>
<li><a rel="nofollow" class="external text" href="http://deeplearning.net/software/pylearn2/">Pylearn2</a> – Machine learning library mainly built on top of Theano</li>
<li><a rel="nofollow" class="external text" href="http://pytorch.org">Pytorch</a> - Python based implementation of Torch API, allows for dynamic graph construction</li>
<li><a rel="nofollow" class="external text" href="https://scikit-neuralnetwork.readthedocs.org/">scikit-neuralnetwork</a> – Multi-layer perceptrons as a wrapper for Pylearn2</li>
<li><a rel="nofollow" class="external text" href="https://github.com/sklearn-theano/sklearn-theano">sklearn-theano</a> – Scikit-learn compatible tools using theano</li>
<li><a rel="nofollow" class="external text" href="https://github.com/cgarciae/tensorbuilder">Tensor Builder</a> – Lightweight extensible library for easy creation of deep neural networks using functions from "any Tensor-based library" (requires TensorFlow) through an API based on the Builder Pattern</li>
<li><a rel="nofollow" class="external text" href="https://github.com/hycis/TensorGraph">TensorGraph</a> – Framework for building any models based on TensorFlow</li>
<li><a rel="nofollow" class="external text" href="https://tenso.rs/">TensorFire</a> – Neural networks framework for the web browser, accelerated by WebGL</li>
<li><a rel="nofollow" class="external text" href="https://github.com/tensorflow/tensorflow/tree/master/tensorflow/contrib/learn/python/learn">TF Learn (Scikit Flow)</a> – Simplified interface for TensorFlow</li>
<li><a rel="nofollow" class="external text" href="https://research.googleblog.com/2016/08/tf-slim-high-level-library-to-define.html">TF-Slim</a> – High level library to define complex models in TensorFlow</li>
<li><a rel="nofollow" class="external text" href="http://tflearn.org/">TFLearn</a> – Deep learning library featuring a higher-level API for TensorFlow</li>
<li><a rel="nofollow" class="external text" href="https://github.com/Ivaylo-Popov/Theano-Lights">Theano-Lights</a> – Deep learning research framework based on Theano</li>
<li><a rel="nofollow" class="external text" href="https://github.com/nyanp/tiny-dnn">tiny-dnn</a> – Header only, dependency-free deep learning framework in C++11</li>
<li><a rel="nofollow" class="external text" href="https://github.com/torchnet/torchnet">torchnet</a> – Torch framework providing a set of abstractions aiming at encouraging code re-use as well as encouraging modular programming</li>
<li><a rel="nofollow" class="external text" href="https://github.com/Samsung/veles">Veles</a> – Distributed machine learning platform by <a href="https://en.wikipedia.org/wiki/Samsung" title="Samsung">Samsung</a></li>
</ul>
<ul>
<li><a rel="nofollow" class="external text" href="https://github.com/yosinski/deep-visualization-toolbox">Deep Visualization Toolbox</a> – Software tool for "probing" DNNs by feeding them image data and watching the reaction of every neuron, and for visualizing what a specific neuron "wants to see the most"</li>
<li><a rel="nofollow" class="external text" href="http://lstm.seas.harvard.edu/">LSTMVis</a> – A visual analysis tool for recurrent neural networks</li>
<li><a rel="nofollow" class="external text" href="https://github.com/rewonc/pastalog">pastalog</a> – Simple, realtime visualization of neural network training performance</li>
</ul>

<br>

### Comparision of deeplearning frameworks

<table class="wikitable sortable" style="text-align: center; font-size: 85%; width: auto; table-layout: fixed;">
<tr>
<th style="width: 12em">Software</th>
<th>Creator</th>
<th>Software license</th>
<th>Open source</th>
<th>Platform</th>
<th>Written in</th>
<th>Interface</th>
<th><a href="https://en.wikipedia.org/wiki/OpenMP" title="OpenMP">OpenMP</a> support</th>
<th><a href="https://en.wikipedia.org/wiki/OpenCL" title="OpenCL">OpenCL</a> support</th>
<th><a href="https://en.wikipedia.org/wiki/CUDA" title="CUDA">CUDA</a> support</th>
<th><a href="https://en.wikipedia.org/wiki/Automatic_differentiation" title="Automatic differentiation">Automatic differentiation</a></th>
<th>Has pretrained models</th>
<th><a href="https://en.wikipedia.org/wiki/Recurrent_neural_network" title="Recurrent neural network">Recurrent nets</a></th>
<th><a href="https://en.wikipedia.org/wiki/Convolutional_neural_network" title="Convolutional neural network">Convolutional nets</a></th>
<th><a href="https://en.wikipedia.org/wiki/Restricted_Boltzmann_machine" title="Restricted Boltzmann machine">RBM</a>/<a href="https://en.wikipedia.org/wiki/Deep_belief_network" title="Deep belief network">DBNs</a></th>
<th>Parallel execution (multi node)</th>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Caffe_(software)" title="Caffe (software)">Caffe</a></td>
<td>Berkeley Vision and Learning Center</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/BSD_license" class="mw-redirect" title="BSD license">BSD license</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Microsoft_Windows" title="Microsoft Windows">Windows</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a>, <a href="https://en.wikipedia.org/wiki/MATLAB" title="MATLAB">MATLAB</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background: #FED; color: black; vertical-align: middle; text-align: center;" class="depends table-depends">Under development</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background: #ececec; color: #2C2C2C; font-size: smaller; vertical-align: middle; text-align: center;" class="unknown table-unknown">?</td>
</tr>
<tr>
<td><a href="/w/index.php?title=Caffe2_(software)&amp;action=edit&amp;redlink=1" class="new" title="Caffe2 (software) (page does not exist)">Caffe2</a></td>
<td>Facebook</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Apache_2.0" class="mw-redirect" title="Apache 2.0">Apache 2.0</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="/wiki/Microsoft_Windows" title="Microsoft Windows">Windows</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a>, <a href="https://en.wikipedia.org/wiki/MATLAB" title="MATLAB">MATLAB</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background: #FED; color: black; vertical-align: middle; text-align: center;" class="depends table-depends">Under development</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Deeplearning4j" title="Deeplearning4j">Deeplearning4j</a></td>
<td>Skymind engineering team; Deeplearning4j community; originally <a href="https://en.wikipedia.org/wiki/Adam_Gibson_(computer_scientist)" title="Adam Gibson (computer scientist)">Adam Gibson</a></td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Apache_2.0" class="mw-redirect" title="Apache 2.0">Apache 2.0</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Windows" class="mw-redirect" title="Windows">Windows</a>, <a href="https://en.wikipedia.org/wiki/Android_(operating_system)" title="Android (operating system)">Android</a> (<a href="/wiki/Cross-platform" title="Cross-platform">Cross-platform</a>)</td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="/wiki/Java_(programming_language)" title="Java (programming language)">Java</a></td>
<td><a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>, <a href="https://en.wikipedia.org/wiki/Scala_(programming_language)" title="Scala (programming language)">Scala</a>, <a href="https://en.wikipedia.org/wiki/Clojure_(programming_language)" class="mw-redirect" title="Clojure (programming language)">Clojure</a>, <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a> (<a href="https://en.wikipedia.org/wiki/Keras" title="Keras">Keras</a>), <a href="https://en.wikipedia.org/wiki/Kotlin_(programming_language)" title="Kotlin (programming language)">Kotlin</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">On roadmap</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Computational Graph</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Dlib" title="Dlib">Dlib</a></td>
<td>Davis King</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Boost_Software_License" class="mw-redirect" title="Boost Software License">Boost Software License</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Cross-platform" title="Cross-platform">Cross-Platform</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Gensim" title="Gensim">Gensim</a></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Keras" title="Keras">Keras</a></td>
<td>François Chollet</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/MIT_license" class="mw-redirect" title="MIT license">MIT license</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Windows" class="mw-redirect" title="Windows">Windows</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a>, <a href="https://en.wikipedia.org/wiki/R_(programming_language)" title="R (programming language)">R</a></td>
<td style="background: #FED; color: black; vertical-align: middle; text-align: center;" class="depends table-depends">Only if using Theano or MXNet as backend</td>
<td style="background: #FED; color: black; vertical-align: middle; text-align: center;" class="depends table-depends">Under development for the Theano backend (and on roadmap for the TensorFlow backend)</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="/w/index.php?title=MatConvNet&amp;action=edit&amp;redlink=1" class="new" title="MatConvNet (page does not exist)">MatConvNet</a></td>
<td><a href="/w/index.php?title=Andrea_Vedaldi&amp;action=edit&amp;redlink=1" class="new" title="Andrea Vedaldi (page does not exist)">Andrea Vedaldi</a>, <a href="/w/index.php?title=Karel_Lenc&amp;action=edit&amp;redlink=1" class="new" title="Karel Lenc (page does not exist)">Karel Lenc</a></td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/BSD_license" class="mw-redirect" title="BSD license">BSD license</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Microsoft_Windows" title="Microsoft Windows">Windows</a>, <a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a> (<a href="https://en.wikipedia.org/wiki/OSX" class="mw-redirect" title="OSX">OSX</a> via Docker on roadmap)</td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td><a href="https://en.wikipedia.org/wiki/MATLAB" title="MATLAB">MATLAB</a>, <a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>,</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Microsoft_Cognitive_Toolkit" title="Microsoft Cognitive Toolkit">Microsoft Cognitive Toolkit</a></td>
<td><a href="https://en.wikipedia.org/wiki/Microsoft_Research" title="Microsoft Research">Microsoft Research</a></td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/MIT_license" class="mw-redirect" title="MIT license">MIT license</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Microsoft_Windows" title="Microsoft Windows">Windows</a>, <a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a> (<a href="https://en.wikipedia.org/wiki/OSX" class="mw-redirect" title="OSX">OSX</a> via Docker on roadmap)</td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python (</a><a href="https://en.wikipedia.org/wiki/Keras" title="Keras">Keras</a>), <a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Command_line" class="mw-redirect" title="Command line">Command line</a>,</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/MXNet" title="MXNet">MXNet</a></td>
<td>Distributed (Deep) Machine Learning Community</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Apache_2.0" class="mw-redirect" title="Apache 2.0">Apache 2.0</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Windows" class="mw-redirect" title="Windows">Windows</a>, <a href="https://en.wikipedia.org/wiki/Amazon_Web_Services" title="Amazon Web Services">AWS</a>, <a href="https://en.wikipedia.org/wiki/Android_(operating_system)" title="Android (operating system)">Android</a>,</td>
<td>Small <a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a> core library</td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a>, <a href="https://en.wikipedia.org/wiki/Julia_(programming_language)" title="Julia (programming language)">Julia</a>, <a href="https://en.wikipedia.org/wiki/Matlab" class="mw-redirect" title="Matlab">Matlab</a>, <a href="https://en.wikipedia.org/wiki/JavaScript" title="JavaScript">JavaScript</a>, <a href="https://en.wikipedia.org/wiki/Go_(programming_language)" title="Go (programming language)">Go</a>, <a href="https://en.wikipedia.org/wiki/R_(programming_language)" title="R (programming language)">R</a>, <a href="https://en.wikipedia.org/wiki/Scala_(programming_language)" title="Scala (programming language)">Scala</a>, <a href="https://en.wikipedia.org/wiki/Perl_(programming_language)" class="mw-redirect" title="Perl (programming language)">Perl</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">On roadmap</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Neural_Designer" title="Neural Designer">Neural Designer</a></td>
<td>Artelnics</td>
<td style="background: #ddf; vertical-align: middle; text-align: center;" class="table-proprietary"><a href="https://en.wikipedia.org/wiki/Proprietary_software" title="Proprietary software">Proprietary</a></td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Microsoft_Windows" title="Microsoft Windows">Windows</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td><a href="https://en.wikipedia.org/wiki/Graphical_user_interface" title="Graphical user interface">Graphical user interface</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background: #ececec; color: #2C2C2C; font-size: smaller; vertical-align: middle; text-align: center;" class="unknown table-unknown">?</td>
<td style="background: #ececec; color: #2C2C2C; font-size: smaller; vertical-align: middle; text-align: center;" class="unknown table-unknown">?</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background: #ececec; color: #2C2C2C; font-size: smaller; vertical-align: middle; text-align: center;" class="unknown table-unknown">?</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/OpenNN" title="OpenNN">OpenNN</a></td>
<td>Artelnics</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License" title="GNU Lesser General Public License">GNU LGPL</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Cross-platform" title="Cross-platform">Cross-platform</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background: #ececec; color: #2C2C2C; font-size: smaller; vertical-align: middle; text-align: center;" class="unknown table-unknown">?</td>
<td style="background: #ececec; color: #2C2C2C; font-size: smaller; vertical-align: middle; text-align: center;" class="unknown table-unknown">?</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background: #ececec; color: #2C2C2C; font-size: smaller; vertical-align: middle; text-align: center;" class="unknown table-unknown">?</td>
</tr>
<tr>
<td>Paddle</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>Pytorch</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Apache_SINGA" title="Apache SINGA">Apache SINGA</a></td>
<td><a href="https://en.wikipedia.org/wiki/Apache_Incubator" title="Apache Incubator">Apache Incubator</a></td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Apache_2.0" class="mw-redirect" title="Apache 2.0">Apache 2.0</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Windows" class="mw-redirect" title="Windows">Windows</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a>, <a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a></td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background: #ececec; color: #2C2C2C; font-size: smaller; vertical-align: middle; text-align: center;" class="unknown table-unknown">?</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/TensorFlow" title="TensorFlow">TensorFlow</a></td>
<td><a href="https://en.wikipedia.org/wiki/Google_Brain" title="Google Brain">Google Brain</a> team</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/Apache_2.0" class="mw-redirect" title="Apache 2.0">Apache 2.0</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Microsoft_Windows" title="Microsoft Windows">Windows</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a> (<a href="https://en.wikipedia.org/wiki/Keras" title="Keras">Keras</a>), <a href="https://en.wikipedia.org/wiki/C_(programming_language)" title="C (programming language)">C</a>/<a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>, <a href="https://en.wikipedia.org/wiki/Java_(programming_language)" title="Java (programming language)">Java</a>, <a href="https://en.wikipedia.org/wiki/Go_(programming_language)" title="Go (programming language)">Go</a>, <a href="https://en.wikipedia.org/wiki/R_(programming_language)" title="R (programming language)">R</a></td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background: #FED; color: black; vertical-align: middle; text-align: center;" class="depends table-depends">On roadmap support</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Theano_(software)" title="Theano (software)">Theano</a></td>
<td><a href="https://en.wikipedia.org/wiki/Universit%C3%A9_de_Montr%C3%A9al" title="Université de Montréal">Université de Montréal</a></td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/BSD_Licenses" class="mw-redirect" title="BSD Licenses">BSD license</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Cross-platform" title="Cross-platform">Cross-platform</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a></td>
<td><a href="https://en.wikipedia.org/wiki/Python_(programming_language)" title="Python (programming language)">Python</a> (<a href="https://en.wikipedia.org/wiki/Keras" title="Keras">Keras</a>)</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background: #FED; color: black; vertical-align: middle; text-align: center;" class="depends table-depends">Under development</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background: #FED; color: black; vertical-align: middle; text-align: center;" class="depends table-depends">Through Lasagne's model zoo</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Torch_(machine_learning)" title="Torch (machine learning)">Torch</a></td>
<td>Ronan Collobert, Koray Kavukcuoglu, Clement Farabet</td>
<td style="background: #9FF; color: black; vertical-align: middle; text-align: center;" class="free table-free"><a href="https://en.wikipedia.org/wiki/BSD_Licenses" class="mw-redirect" title="BSD Licenses">BSD license</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td><a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Microsoft_Windows" title="Microsoft Windows">Windows</a>, <a href="/wiki/IOS" title="IOS">iOS</a></td>
<td><a href="https://en.wikipedia.org/wiki/C_(programming_language)" title="C (programming language)">C</a>, <a href="https://en.wikipedia.org/wiki/Lua_(programming_language)" title="Lua (programming language)">Lua</a></td>
<td><a href="https://en.wikipedia.org/wiki/Lua_(programming_language)" title="Lua (programming language)">Lua</a>, <a href="https://en.wikipedia.org/wiki/Lua_(programming_language)" title="Lua (programming language)">LuaJIT</a>, <a href="https://en.wikipedia.org/wiki/C_(programming_language)" title="C (programming language)">C</a>, utility library for <a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a>/<a href="https://en.wikipedia.org/wiki/OpenCL" title="OpenCL">OpenCL</a></td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background: #FED; color: black; vertical-align: middle; text-align: center;" class="depends table-depends">Third party implementations</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
<tr>
<td><a href="https://en.wikipedia.org/wiki/Wolfram_Mathematica" title="Wolfram Mathematica">Wolfram Mathematica</a></td>
<td><a href="https://en.wikipedia.org/wiki/Wolfram_Research" title="Wolfram Research">Wolfram Research</a></td>
<td style="background: #ddf; vertical-align: middle; text-align: center;" class="table-proprietary"><a href="https://en.wikipedia.org/wiki/Proprietary_software" title="Proprietary software">Proprietary</a></td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td><a href="https://en.wikipedia.org/wiki/Microsoft_Windows" title="Microsoft Windows">Windows</a>, <a href="https://en.wikipedia.org/wiki/Mac_OS_X" class="mw-redirect" title="Mac OS X">Mac OS X</a>, <a href="https://en.wikipedia.org/wiki/Linux" title="Linux">Linux</a>, <a href="https://en.wikipedia.org/wiki/Cloud_computing" title="Cloud computing">Cloud computing</a></td>
<td><a href="https://en.wikipedia.org/wiki/C%2B%2B" title="C++">C++</a></td>
<td><a href="https://en.wikipedia.org/wiki/Wolfram_Language" title="Wolfram Language">Wolfram Language</a></td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#F99;vertical-align:middle;text-align:center;" class="table-no">No</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
<td style="background:#9F9;vertical-align:middle;text-align:center;" class="table-yes">Yes</td>
</tr>
</table>

--------------------


