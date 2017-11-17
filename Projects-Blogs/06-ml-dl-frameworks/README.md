## case study: ml-dl frameworks(an architectural overview)

* Tensorflow
* Theano
* Keras
* Caffe + caffe2
* Torch + pytorch
* Deeplearning4j
* MXNet
* Microsoft Cognitive Toolkit
* Lasagne
* BigDL
* scikit-learn
* chainer

********************************
whitepapers

| [TensorFlow(2015)](http://download.tensorflow.org/paper/whitepaper2015.pdf) | [Theano(2010)](http://www.iro.umontreal.ca/~lisa/pointeurs/theano_scipy2010.pdf) + [Theano(2016)](https://arxiv.org/pdf/1605.02688v1.pdf) | [Caffe(2014)](https://arxiv.org/pdf/1408.5093.pdf) + [Caffe2](http://www.zdnet.com/article/caffe2-deep-learning-wide-ambitions-flexibility-scalability-and-advocacy/) |


### tf papers

* [TensorFlow: Large-Scale Machine Learning on Heterogeneous Distributed Systems](http://download.tensorflow.org/paper/whitepaper2015.pdf) - This paper describes the TensorFlow interface and an implementation of that interface that we have built at Google
* [TF.Learn: TensorFlow's High-level Module for Distributed Machine Learning](https://arxiv.org/abs/1612.04251)
* [Comparative Study of Deep Learning Software Frameworks](http://arxiv.org/abs/1511.06435) - The study is performed on several types of deep learning architectures and we evaluate the performance of the above frameworks when employed on a single machine for both (multi-threaded) CPU and GPU (Nvidia Titan X) settings
* [Distributed TensorFlow with MPI](http://arxiv.org/abs/1603.02339) - In this paper, we extend recently proposed Google TensorFlow for execution on large scale clusters using Message Passing Interface (MPI)
* [Globally Normalized Transition-Based Neural Networks](http://arxiv.org/abs/1603.06042) - This paper describes the models behind [SyntaxNet](https://github.com/tensorflow/models/tree/master/syntaxnet).
* [TensorFlow: A system for large-scale machine learning](https://arxiv.org/abs/1605.08695) - This paper describes the TensorFlow dataflow model in contrast to existing systems and demonstrate the compelling performance

## keras ref

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

### torch ref

<div class="reflist columns references-column-width" style="-moz-column-width: 30em; -webkit-column-width: 30em; column-width: 30em; list-style-type: decimal;">
<ol class="references">
<li id="cite_note-torch-modular-1"><span class="mw-cite-backlink"><b><a href="#cite_ref-torch-modular_1-0">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=CBB0C8A5FE34F6D6DAFF997F6B6A205A?doi=10.1.1.8.9850&amp;rep=rep1&amp;type=pdf">"Torch: a modular machine learning software library"</a>. 30 October 2002<span class="reference-accessdate">. Retrieved <span class="nowrap">24 April</span> 2014</span>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Abook&amp;rft.genre=unknown&amp;rft.btitle=Torch%3A+a+modular+machine+learning+software+library&amp;rft.date=2002-10-30&amp;rft_id=http%3A%2F%2Fciteseerx.ist.psu.edu%2Fviewdoc%2Fdownload%3Bjsessionid%3DCBB0C8A5FE34F6D6DAFF997F6B6A205A%3Fdoi%3D10.1.1.8.9850%26rep%3Drep1%26type%3Dpdf&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATorch+%28machine+learning%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-2"><span class="mw-cite-backlink"><b><a href="#cite_ref-2">^</a></b></span> <span class="reference-text"><cite class="citation web">Collobert, Ronan. <a rel="nofollow" class="external text" href="http://torch.ch/">"Torch7"</a>. <i><a href="/wiki/GitHub" title="GitHub">GitHub</a></i>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=GitHub&amp;rft.atitle=Torch7&amp;rft.aulast=Collobert&amp;rft.aufirst=Ronan&amp;rft_id=http%3A%2F%2Ftorch.ch%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATorch+%28machine+learning%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-nips-3"><span class="mw-cite-backlink"><b><a href="#cite_ref-nips_3-0">^</a></b></span> <span class="reference-text"><cite class="citation journal">Ronan Collobert; Koray Kavukcuoglu; Clement Farabet (2011). <a rel="nofollow" class="external text" href="http://ronan.collobert.com/pub/matos/2011_torch7_nipsw.pdf">"Torch7: A Matlab-like Environment for Machine Learning"</a> <span style="font-size:85%;">(PDF)</span>. <i>Neural Information Processing Systems</i>.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=article&amp;rft.jtitle=Neural+Information+Processing+Systems&amp;rft.atitle=Torch7%3A+A+Matlab-like+Environment+for+Machine+Learning&amp;rft.date=2011&amp;rft.au=Ronan+Collobert&amp;rft.au=Koray+Kavukcuoglu&amp;rft.au=Clement+Farabet&amp;rft_id=http%3A%2F%2Fronan.collobert.com%2Fpub%2Fmatos%2F2011_torch7_nipsw.pdf&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATorch+%28machine+learning%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
<li id="cite_note-4"><span class="mw-cite-backlink"><b><a href="#cite_ref-4">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="http://www.kdnuggets.com/2014/02/exclusive-yann-lecun-deep-learning-facebook-ai-lab.html">KDnuggets Interview with Yann LeCun, Deep Learning Expert, Director of Facebook AI Lab</a></span></li>
<li id="cite_note-5"><span class="mw-cite-backlink"><b><a href="#cite_ref-5">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://news.ycombinator.com/item?id=7928738">Hacker News</a></span></li>
<li id="cite_note-6"><span class="mw-cite-backlink"><b><a href="#cite_ref-6">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://www.facebook.com/yann.lecun/posts/10152077631217143?comment_id=10152089275552143&amp;offset=0&amp;total_comments=6">Yann Lecun's Facebook Page</a></span></li>
<li id="cite_note-7"><span class="mw-cite-backlink"><b><a href="#cite_ref-7">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://www.idiap.ch/scientific-research/resources/torch">IDIAP Research Institute&#160;: Torch</a></span></li>
<li id="cite_note-8"><span class="mw-cite-backlink"><b><a href="#cite_ref-8">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://github.com/soumith/torch-android">Torch-android GitHub repository</a></span></li>
<li id="cite_note-9"><span class="mw-cite-backlink"><b><a href="#cite_ref-9">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="https://github.com/clementfarabet/torch-ios">Torch-ios GitHub repository</a></span></li>
<li id="cite_note-10"><span class="mw-cite-backlink"><b><a href="#cite_ref-10">^</a></b></span> <span class="reference-text"><a rel="nofollow" class="external text" href="http://pub.clement.farabet.net/ecvw11.pdf">NeuFlow: A Runtime Reconﬁgurable Dataﬂow Processor for Vision</a></span></li>
<li id="cite_note-11"><span class="mw-cite-backlink"><b><a href="#cite_ref-11">^</a></b></span> <span class="reference-text"><cite class="citation web"><a rel="nofollow" class="external text" href="https://www.wired.com/2015/01/facebook-open-sources-trove-ai-tools/">"Facebook Open-Sources a Trove of AI Tools"</a>. <i><a href="/wiki/Wired_(website)" class="mw-redirect" title="Wired (website)">Wired</a></i>. 16 January 2015.</cite><span title="ctx_ver=Z39.88-2004&amp;rft_val_fmt=info%3Aofi%2Ffmt%3Akev%3Amtx%3Ajournal&amp;rft.genre=unknown&amp;rft.jtitle=Wired&amp;rft.atitle=Facebook+Open-Sources+a+Trove+of+AI+Tools&amp;rft.date=2015-01-16&amp;rft_id=https%3A%2F%2Fwww.wired.com%2F2015%2F01%2Ffacebook-open-sources-trove-ai-tools%2F&amp;rfr_id=info%3Asid%2Fen.wikipedia.org%3ATorch+%28machine+learning%29" class="Z3988"><span style="display:none;">&#160;</span></span></span></li>
</ol>
</div>


<div class="section" id="scientific-computing-tools-for-python">
<span id="content"></span><h2>Scientific Computing Tools for Python<a class="headerlink" href="#scientific-computing-tools-for-python" title="Permalink to this headline">¶</a></h2>
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
<h3>The SciPy ecosystem<a class="headerlink" href="#the-scipy-ecosystem" title="Permalink to this headline">¶</a></h3>
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

***************************
