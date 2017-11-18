 <h1 class="post-title">So you decided to write a machine learning library (bad advice)</h1>
    <p class="post-meta">Oct 15, 2015 • Alex Rogozhnikov</p>
  </header>

  <article class="post-content">
    <p>So, you decided to write a brand new library of machine learning.
This one will be much better than everything you have seen before. 
It will be fast, easy-to-use, even-easier-to-extend, flexible, with support of multi-core computations and many more.</p>

<p>There are traditions which most of developers of ML libraries are trying to follow and
I decided to collect those together.</p>

<p>Most of the experience came from developing <a href="https://github.com/yandex/rep">yandex/REP</a>
and browsing code / experimenting with different classifiers.</p>

<p>Treat this as ‘awful advice collection’.</p>

<p><img src="/images/etc/bad_advice.jpg" style="margin: 20px 200px; width: 400px;" alt="bad advice ahead" /></p>

<ol>
  <li>
    <p><strong>Your library is the start and end point in user’s research.</strong>
That’s the key point in doing everything bad.
There is nothing else user should pay attention to.
Following point is consequence of this simple rule.</p>
  </li>
  <li>
    <p><strong>Never care about whether other libraries exist.</strong>
Why actually you shall worry that there are other libraries of machine learning and how many of them are already on the github?
Definitely, the one written by you will be times better.
Speed benchmarks? Forget.
New algorithms? No, never.
Building tests to compare accuracy on public data is also nothing but wasted time.</p>
  </li>
  <li>
    <p><strong>Invent new interface.</strong>
Users expect the structure and examples of usage to be simple?
Bad idea. You have studied OOP, so now you can complex APIs!</p>

    <p>Special class trainer. Special class dataset.
Also you need class supervised dataset.
And special class for sampling from supervised dataset.</p>

    <p>Probably you’ll never implement one more sampler, such organization of code is definitely needed for the sake of OOP.</p>
  </li>
  <li>
    <p><strong>Use your own format.</strong> Any successful library has it’s own format.
Currently used formats are not universal. You need a new one.
Binary formats (like HDF5, FITS and ROOT) are definitely bad, because you can’t write a parser for those in 10 lines.</p>

    <p>There should be something special about your format.
Like csv, but with custom separator.
Also, you will not add column names there, since algorithm doesn’t require it
(also, I would recommend not to check number of columns at prediction time, this would allow user to make less obvious mistakes).</p>
  </li>
  <li>
    <p><strong>Don’t use random seed.</strong> At least don’t do it in the way users expect. There are various options:</p>

    <ol>
      <li>simply never set seed, so debugging would be almost impossible. If algorithm didn’t converge 10 times, that’s because of a bad luck.</li>
      <li>set global random seed. Let reproducibility fail during multithreading</li>
      <li>finally, introduce a special parameter <code class="highlighter-rouge">random_seed</code> and ignore it. Haha!</li>
    </ol>

    <!-- theanets, nolearn, pybrain, neurolab -->
  </li>
  <li>
    <p><strong>Write in C++ or CUDA</strong>. You heard there are other languages,
but everyone knows that ML needs efficient implementations.
Anything being written in C++ is the fastest possible.</p>

    <p>Don’t use any vector language / tool. Code in C++ is very clear. Also ignore parallel primitives.</p>

    <p>Never use BLAS operations. Don’t use numpy, theano, octave or fortran90+, otherwise other developers will be able to understand your code!</p>

    <!-- PyBrain  -->

    <p>Also remember to create ‘for the purposes of efficiency’ a god-object and put all the data there.
While reading your code, side programmer will not be able to get what information is used by each method.</p>
  </li>
  <li>
    <p><strong>Write lots of logs to output!</strong>.
Remember the starting point? There is nothing else user shall remember of, only about your library?</p>

    <p>Every step of algorithm shall print some useless information (better if accompanied by ASCII art).
Don’t allow your algorithm to be run silently (so avoid verbosity parameter).
It should always return code 0 (whatever happens) ans print errors in stdout (not stderr!).</p>

    <p>Never use verbose parameter.</p>

    <!-- LibFM as well as many nnets -->
  </li>
  <li>
    <p>There are definitely very few <strong>libraries of neural networks and deep learning!</strong>
We need more!
You’ll write a new and a better one (though start from simple things, of course).</p>

    <p>Did I say that you should ignore theano?</p>
  </li>
  <li>
    <p><strong>SGD is a fresh idea!</strong> Adaptive SGD is even better. Online learning is the new mainstream. 
That’s the way to go. Learning representation? Use SGD! Logistic regression? SGD! Factorization? SGD! Using Rprop? SGD!</p>

    <!-- theanets -->
  </li>
  <li>
    <p>Write <strong>your own map-reduce system.</strong>
Optimization of algorithm is an annoying process.
It’s better to use 100 machines and solve the same problem faster, right?</p>

    <p>Everyone (just everyone) today has a good cluster.
Setting up distributed environment with same collection of libraries is very simple.</p>

    <p>Finally, there is always some user who wants ‘distributed’ option
(but never will be able to use it for different reasons).</p>

    <!-- early xgboost -->
  </li>
  <li>
    <p>Change interface all the time.<br />
Drop the support as soon as someone starts using your library.
<!-- pybrain, nolearn.dbn --></p>

    <p>You’ll find a new area to write your-next-best-open-library.</p>

    <!-- theanets, lasagne -->
  </li>
</ol>

<p>Ok, I think it’s enough.
If I convinced you that there is no need in new libraries, but you still wish to do something useful in ML,
there are projects which you can help.</p>

<p>Firstly, those are:</p>

<ul>
  <li>theano (looks there are ~3-4 active contributors)</li>
  <li>numpy (parallel operations in numpy are very needed there, as well as optimization of existing code)</li>
  <li>scikit-learn (which in some cases lacks multi-threading)</li>
</ul>

<p>Even minor contribution to those projects is of more help, because lots of software relies on them.
Writing wrappers to projects you’re using is also a good idea.</p>

<p>If you still feel that you want to write a new library, spend much time with scikit-learn first.
Understand it’s interface, how Bagging/AdaBoost work as meta-estimators.
How grid-search for such meta-algorithms is done.
Probably, read the sources.</p>

<p>Then start writing. Leave least dependencies and write simple code (using numpy or so). 
If it is required, you’ll rewrite it to optimize for speed. Make sure your library is installed via package manager
(pip for python, most languages today also have their package managers).</p>
