<h1 id="implement-custom-layer">Way to implement custom Layer for Deep Learning framework</h1>
    <p>
          Posted on 2017/01/07 in <a href="https://luoyetx.github.io/category/machine-learning.html">Machine Learning</a>


    </p>
  </header>


  <div>
    <p>It's a common situation that we may need to implement a custom operator or layer for the Deep Learning framework we are using. When I mean implement a Layer or Operator for the framework, it's because the framework doesn't offer us the Operation we want. Sometimes, awesome paper appears with strange functions that not supported by the framework. Sometimes, you want to change the behavior of traditional Layer implementation that can suits your demand. But mostly, you may want to create a new function to adapt it to the neural network that can help you get better result. As a result, you may need to create a Layer or Operator for the framework you use.</p>
<h3>Difference between Operator and Layer</h3>
<p>DL frameworks like <a href="https://github.com/BVLC/caffe">Caffe</a> and <a href="http://torch.ch/">Torch</a> use Layer for their basic network components while <a href="https://github.com/dmlc/mxnet">MXNet</a> and <a href="https://www.tensorflow.org/">TensorFlow</a> use Operator. There is little difference between Operator and Layer if you only focus on the implementation of Forward and Backward operation. Layer usually holds the learnable parameters by themselves while Operator only focus on the operation and let other part of the framework to consider about the parameters. We can abstract these two conception easily using the following Python code.</p>
<div class="highlight"><pre><span></span><span class="k">class</span> <span class="nc">Layer</span><span class="p">(</span><span class="nb">object</span><span class="p">):</span>
    <span class="sd">&#39;&#39;&#39;an example for Layer</span>
<span class="sd">    &#39;&#39;&#39;</span>

    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">initializer</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;initialize learnable parameters</span>

<span class="sd">        Parameters</span>
<span class="sd">        ----------</span>
<span class="sd">        initializer: way to initialize parameters</span>
<span class="sd">        &#39;&#39;&#39;</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">params</span> <span class="o">=</span> <span class="p">{</span>
            <span class="s1">&#39;weight&#39;</span><span class="p">:</span> <span class="n">initializer</span><span class="p">(</span><span class="s1">&#39;layer_weight&#39;</span><span class="p">),</span>
        <span class="p">}</span>

    <span class="k">def</span> <span class="nf">forward</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">is_train</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;perform forward</span>

<span class="sd">        Parameters</span>
<span class="sd">        ----------</span>
<span class="sd">        is_train: train or test</span>
<span class="sd">        in_data: input data to this layer</span>
<span class="sd">        out_data: output data of this layer</span>
<span class="sd">        &#39;&#39;&#39;</span>
        <span class="k">pass</span>

    <span class="k">def</span> <span class="nf">backward</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">,</span> <span class="n">in_grad</span><span class="p">,</span> <span class="n">out_grad</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;perform backward</span>

<span class="sd">        Parameters</span>
<span class="sd">        ----------</span>
<span class="sd">        in_data: input data to this layer</span>
<span class="sd">        out_data: output data of this layer</span>
<span class="sd">        in_grad: gradient w.r.t. to in_data, backprop to former layers</span>
<span class="sd">        out_grad: gradient w.r.t. to out_data, backprop from latter layers</span>
<span class="sd">        &#39;&#39;&#39;</span>
        <span class="k">pass</span>

    <span class="k">def</span> <span class="nf">update</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">updater</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;update learnable parameters</span>

<span class="sd">        Parameters</span>
<span class="sd">        ----------</span>
<span class="sd">        updater: updater using different optimize strategy to update parameters</span>
<span class="sd">        &#39;&#39;&#39;</span>
        <span class="n">updater</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">params</span><span class="p">)</span>


<span class="k">class</span> <span class="nc">Operator</span><span class="p">(</span><span class="nb">object</span><span class="p">):</span>
    <span class="sd">&#39;&#39;&#39;an example for Operator</span>
<span class="sd">    &#39;&#39;&#39;</span>

    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;initialize operator</span>
<span class="sd">        &#39;&#39;&#39;</span>
        <span class="k">pass</span>

    <span class="k">def</span> <span class="nf">forward</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">is_train</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;perform forward</span>

<span class="sd">        Parameters</span>
<span class="sd">        ----------</span>
<span class="sd">        is_train: train or test</span>
<span class="sd">        in_data: input data to this layer including learnable parameters attached to this Operator</span>
<span class="sd">        out_data: output data of this layer</span>
<span class="sd">        &#39;&#39;&#39;</span>
        <span class="k">pass</span>

    <span class="k">def</span> <span class="nf">backward</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">,</span> <span class="n">in_grad</span><span class="p">,</span> <span class="n">out_grad</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;perform backward</span>

<span class="sd">        Parameters</span>
<span class="sd">        ----------</span>
<span class="sd">        in_data: input data to this layer</span>
<span class="sd">        out_data: output data of this layer</span>
<span class="sd">        in_grad: gradient w.r.t. to in_data, backprop to former layers</span>
<span class="sd">        out_grad: gradient w.r.t. to out_data, backprop from latter layers</span>
<span class="sd">        &#39;&#39;&#39;</span>
        <span class="k">pass</span>

    <span class="k">def</span> <span class="nf">infer_shape</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">in_shape</span><span class="p">,</span> <span class="n">out_shape</span><span class="p">):</span>
        <span class="sd">&#39;&#39;&#39;infer data shape of in_data and out_data</span>
<span class="sd">        this helps framework to collect the information about operator</span>

<span class="sd">        Parameters</span>
<span class="sd">        ----------</span>
<span class="sd">        in_shape: in_data shape</span>
<span class="sd">        out_shape: out_data shape</span>
<span class="sd">        &#39;&#39;&#39;</span>
        <span class="k">pass</span>
</pre></div>


<p>Since Layer holds the parameters themselves, they may need initializer and updater to initialize and update them. However, for most frameworks, Layer holds the parameters don't need to care about the parameters update, all they need to do is put the gradients w.r.t. parameters in some place where the framework can fetch. Actually, the initialization part can also do in this way. Somehow, there seems little difference between Layer and Operator, as Layer accesses its parameters in its own class member while Operator accesses the parameters through <code>in_data</code>. But just because of this little difference, Layers are not easy (but still possible) to share parameters between each other while Operator can easily do it. It's important for RNN but not a common case for CNN. And that's a reason why frameworks like MXNet and TensorFlow use Operator instead of Layer as their basic network component.</p>
<p>Regardless of the difference between Layer and Operator, we still need to implement Forward and Backward for them. There's nothing difference or special. They go the same way. So we will use Layer for the next part, but it reads parameters from <code>in_data</code> which like a Operator.</p>
<h3>Write down formulas</h3>
<p>Before we write any code, the first thing we need to do is to figure out all the formula that our Layer need. Let's consider a function which acts like a fully connected Layer, but will modify output result at some location. This function is adapted from paper <a href="https://arxiv.org/pdf/1612.02295.pdf">Large-Margin Softmax Loss for Convolutional Neural Networks</a>. The original function is kind of complex, I simplify it for the demonstration.</p>
<p>We define the function below.</p>
<div class="math">$$ f_{i, j} = w_j^T \cdot x_i \quad j \neq y_i $$</div>
<div class="math">$$
\begin{eqnarray}
f_{i, y_i} =
\begin{cases}
w_{y_i}^T \cdot x_i &amp; w_{y_i}^T \cdot x_i &lt; 0 \\
k * w_{y_i}^T \cdot x_i &amp; w_{y_i}^T \cdot x_i &gt; 0
\end{cases}
\end{eqnarray}
$$</div>
<p>It's the same thing as fully connected layer does except <span class="math">\(f_{i, y_i}\)</span> will be smaller than original one if <span class="math">\(f_{i, yi} &gt; 0\)</span>. What's more, <span class="math">\(0 &lt; k &lt; 1\)</span> is a hyperparameter of this Layer. We also omit bias term. Then we need to calculate the derivatives for <span class="math">\(x\)</span> and <span class="math">\(w\)</span>.</p>
<div class="math">$$ \frac {\partial f_{i, j}} {\partial x_i} = w_j \quad j \neq y_i $$</div>
<div class="math">$$
\begin{eqnarray}
\frac {\partial f_{i, y_i}} {\partial x_i} =
\begin{cases}
w_{y_i} &amp; w_{y_i} \cdot x_i &lt; 0 \\
k * w_{y_i} &amp; w_{y_i} \cdot x_i &gt; 0
\end{cases}
\end{eqnarray}
$$</div>
<p><span class="math">\(w\)</span> goes the same way.</p>
<div class="math">$$ \frac {\partial f_{i, j}} {\partial w_j} = x_i \quad j \neq y_i $$</div>
<div class="math">$$
\begin{eqnarray}
\frac {\partial f_{i, y_i}} {\partial w_{y_i}} =
\begin{cases}
x_i &amp; w_{y_i} \cdot x_i &lt; 0 \\
k * x_i &amp; w_{y_i} \cdot x_i &gt; 0
\end{cases}
\end{eqnarray}
$$</div>
<p>It's time to bring Loss <span class="math">\(J\)</span> in. Then we can write gradient w.r.t. <span class="math">\(x\)</span> and <span class="math">\(w\)</span>.</p>
<div class="math">$$
\begin{eqnarray}
\frac {\partial J} {\partial x_i} &amp;=&amp; \sum_j \frac {\partial J} {\partial f_{i, j}} \frac {\partial f_{i, j}} {\partial x_i} \\
&amp;=&amp; \sum_{j, j \neq y_i} \frac {\partial J} {\partial f_{i, j}} w_j + \frac {\partial J} {\partial f_{i, y_i}} \frac {\partial f_{i, y_i}} {\partial x_i}
\end{eqnarray}
$$</div>
<div class="math">$$
\begin{eqnarray}
\frac {\partial J} {\partial w_j} &amp;=&amp; \sum_i \frac {\partial J} {\partial f_{i, j}} \frac {\partial f_{i, j}} {\partial w_j} \\
&amp;=&amp; \sum_{i, j \neq y_i} \frac {\partial J} {\partial f_{i, j}} x_i + \sum_{i, j = y_i} \frac {\partial J} {\partial f_{i, y_i}} \frac {\partial f_{i, y_i}} {\partial w_{y_i}}
\end{eqnarray}
$$</div>
<p>With the above formulas, we now know how the Forward and Backward of our Layer should do.</p>
<h3>Implement the Layer</h3>
<p>Let's implement Forward and Backward in Python. It's your choice to pick a programming language to implement. I happens to use Python a lot and most deep learning framework have support for Python. It's a good idea to choose a language that the framework you use supports. You can easily wrap it after you finish the implementation. In this step, we really don't need to consider the performance of implementation as long as it can work.</p>
<div class="highlight"><pre><span></span><span class="k">def</span> <span class="nf">forword</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">is_train</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">):</span>
    <span class="n">X</span> <span class="o">=</span> <span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;X&#39;</span><span class="p">]</span>
    <span class="n">W</span> <span class="o">=</span> <span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;W&#39;</span><span class="p">]</span>
    <span class="n">label</span> <span class="o">=</span> <span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;label&#39;</span><span class="p">]</span>
    <span class="c1"># traditional fully connected layer</span>
    <span class="n">out</span> <span class="o">=</span> <span class="n">X</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">W</span><span class="o">.</span><span class="n">T</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">is_train</span><span class="p">:</span>
        <span class="c1"># some modification</span>
        <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">X</span><span class="p">)):</span>
            <span class="n">yi</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">label</span><span class="p">[</span><span class="n">i</span><span class="p">])</span>
            <span class="k">if</span> <span class="n">out</span><span class="p">[</span><span class="n">i</span><span class="p">,</span> <span class="n">yi</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">:</span>
                <span class="n">out</span><span class="p">[</span><span class="n">i</span><span class="p">,</span> <span class="n">yi</span><span class="p">]</span> <span class="o">*=</span> <span class="bp">self</span><span class="o">.</span><span class="n">k</span>
    <span class="n">out_data</span><span class="p">[</span><span class="s1">&#39;output&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">out</span>
</pre></div>


<p>The Forward function is easy since it's normally a fully connected layer that may modify the output <span class="math">\(f_{i,y_i}\)</span>. <code>is_train</code> is used to indicate whether current context is train or test. We only want to modify <span class="math">\(f_{i, y_i}\)</span> during training.</p>
<div class="highlight"><pre><span></span><span class="k">def</span> <span class="nf">backward</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">,</span> <span class="n">in_grad</span><span class="p">,</span> <span class="n">out_grad</span><span class="p">):</span>
    <span class="n">X</span> <span class="o">=</span> <span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;X&#39;</span><span class="p">]</span>
    <span class="n">W</span> <span class="o">=</span> <span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;W&#39;</span><span class="p">]</span>
    <span class="n">label</span> <span class="o">=</span> <span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;label&#39;</span><span class="p">]</span>
    <span class="n">out</span> <span class="o">=</span> <span class="n">out_data</span><span class="p">[</span><span class="s1">&#39;output&#39;</span><span class="p">]</span>
    <span class="n">o_grad</span> <span class="o">=</span> <span class="n">out_grad</span><span class="p">[</span><span class="s1">&#39;output&#39;</span><span class="p">]</span>
    <span class="c1"># traditional fully connected</span>
    <span class="n">x_grad</span> <span class="o">=</span> <span class="n">o_grad</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">W</span><span class="p">)</span>
    <span class="n">w_grad</span> <span class="o">=</span> <span class="n">o_grad</span><span class="o">.</span><span class="n">T</span><span class="o">.</span><span class="n">dot</span><span class="p">(</span><span class="n">X</span><span class="p">)</span>
    <span class="c1"># gradient w.r.t. X</span>
    <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">X</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]):</span>
        <span class="n">yi</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">label</span><span class="p">[</span><span class="n">i</span><span class="p">])</span>
        <span class="k">if</span> <span class="n">out</span><span class="p">[</span><span class="n">i</span><span class="p">,</span> <span class="n">yi</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">:</span>
            <span class="n">x_grad</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">+=</span> <span class="bp">self</span><span class="o">.</span><span class="n">k</span> <span class="o">*</span> <span class="n">W</span><span class="p">[</span><span class="n">yi</span><span class="p">]</span> <span class="o">-</span> <span class="n">W</span><span class="p">[</span><span class="n">yi</span><span class="p">]</span>
    <span class="c1"># gradient w.r.t W</span>
    <span class="k">for</span> <span class="n">j</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">W</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]):</span>
        <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">X</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">]):</span>
            <span class="n">yi</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">label</span><span class="p">[</span><span class="n">i</span><span class="p">])</span>
            <span class="k">if</span> <span class="n">yi</span> <span class="o">==</span> <span class="n">j</span> <span class="ow">and</span> <span class="n">out</span><span class="p">[</span><span class="n">i</span><span class="p">,</span> <span class="n">yi</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">:</span>
                <span class="n">w_grad</span> <span class="o">+=</span> <span class="bp">self</span><span class="o">.</span><span class="n">k</span> <span class="o">*</span> <span class="n">X</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">-</span> <span class="n">X</span><span class="p">[</span><span class="n">i</span><span class="p">]</span>
    <span class="n">in_grad</span><span class="p">[</span><span class="s1">&#39;X&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">x_grad</span>
    <span class="n">in_grad</span><span class="p">[</span><span class="s1">&#39;W&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">w_grad</span>
</pre></div>


<p>Backward is a little tricky, we can reuse the output result of <code>out</code> to know if we have modify <span class="math">\(f_{i, y_i}\)</span>. Also we can reuse the result of fully connected layer's backward operation.</p>
<div class="math">$$
\frac {\partial J} {\partial x_i} = \sum_j \frac {\partial J} {\partial f_{i, j}} w_j + \frac {\partial J} {\partial f_{i, y_i}} (\frac {\partial f_{i, y_i}} {\partial x_i} - w_{y_i})
$$</div>
<div class="math">$$
\frac {\partial J} {\partial w_j} = \sum_i \frac {\partial J} {\partial f_{i, j}} x_i + \sum_{i, j = y_i} \frac {\partial J} {\partial f_{i, y_i}} (\frac {\partial f_{i, y_i}} {\partial w_{y_i}} - x_i)
$$</div>
<p>the first part of two formulas is exactly what fully connected layer does.</p>
<h3>Gradient Check</h3>
<p>Once you have write done the code, gradient check is important for you to verify the correctness of your implementation. The key idea is below.</p>
<div class="math">$$ f'(x) = \frac {f(x + \Delta x) - f(x - \Delta x)} {2 \Delta x} $$</div>
<p>The formula evaluate the derivative at <code>X</code>. In this way, we can evaluate the gradient of data and parameter using Layer's Forward. We can also calculate this derivative using Layer's Backward we implement. For example, we can choose one element from <code>X</code>, we call Layer's Forward and Backward, and get the gradient from <code>grad</code> for this one element. Next, we modify this element to <code>x-eps</code> and <code>x+eps</code>, call Forward twice and get two <code>f</code> values. then we can evaluate the gradient. The calculated and evaluated gradient can be different but shouldn't differ to much.</p>
<p>The problem here is what if my Layer doesn't output a single value but a multi-dimension array, and where comes the gradient w.r.t. my Layer's output. The key is to plug a loss function to the output of the Layer. The most simple loss function we can choose is the L2 function.</p>
<div class="math">$$ J = \frac {1} {2} \sum_i x_i^2 $$</div>
<p><span class="math">\(J\)</span> is easy to calculate and the derivative too.</p>
<div class="math">$$ \frac {\partial J} {\partial x_i} = x_i $$</div>
<div class="math">$$ \frac {\partial J} {\partial X} = X $$</div>
<p>Thus, we can simply plug in this loss function to whatever the output of your Layer may output. The following Python code show an easy way to do gradient check on a Layer.</p>
<div class="highlight"><pre><span></span><span class="k">def</span> <span class="nf">gradient_check</span><span class="p">(</span><span class="n">layer</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">,</span> <span class="n">in_grad</span><span class="p">,</span> <span class="n">out_grad</span><span class="p">):</span>
    <span class="sd">&#39;&#39;&#39;do gradient check for parameter X</span>
<span class="sd">    &#39;&#39;&#39;</span>
    <span class="c1"># loss function</span>
    <span class="n">loss_it</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">np</span><span class="o">.</span><span class="n">square</span><span class="p">(</span><span class="n">x</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span> <span class="o">/</span> <span class="mi">2</span>

    <span class="c1"># suppose X is a 2 dimension array</span>
    <span class="n">eps</span> <span class="o">=</span> <span class="mf">1e-4</span>
    <span class="n">threshold</span> <span class="o">=</span> <span class="mf">1e-2</span>
    <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;X&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]):</span>
        <span class="k">for</span> <span class="n">j</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;X&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">]):</span>
            <span class="c1"># calculate gradient</span>
            <span class="n">layer</span><span class="o">.</span><span class="n">forward</span><span class="p">(</span><span class="n">is_train</span><span class="o">=</span><span class="bp">True</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">)</span>
            <span class="n">out_grad</span><span class="p">[</span><span class="s1">&#39;output&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">out_data</span><span class="p">[</span><span class="s1">&#39;output&#39;</span><span class="p">]</span>
            <span class="n">layer</span><span class="o">.</span><span class="n">backward</span><span class="p">(</span><span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">,</span> <span class="n">in_grad</span><span class="p">,</span> <span class="n">out_grad</span><span class="p">)</span>
            <span class="n">gradient</span> <span class="o">=</span> <span class="n">in_grad</span><span class="p">[</span><span class="s1">&#39;X&#39;</span><span class="p">][</span><span class="n">i</span><span class="p">,</span> <span class="n">j</span><span class="p">]</span>

            <span class="c1"># evaluate gradient</span>
            <span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;X&#39;</span><span class="p">][</span><span class="n">i</span><span class="p">,</span> <span class="n">j</span><span class="p">]</span> <span class="o">-=</span> <span class="n">eps</span>
            <span class="n">layer</span><span class="o">.</span><span class="n">forward</span><span class="p">(</span><span class="n">is_train</span><span class="o">=</span><span class="bp">True</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">)</span>
            <span class="n">J1</span> <span class="o">=</span> <span class="n">loss_it</span><span class="p">(</span><span class="n">out_grad</span><span class="p">[</span><span class="s1">&#39;output&#39;</span><span class="p">])</span>
            <span class="n">in_data</span><span class="p">[</span><span class="s1">&#39;X&#39;</span><span class="p">][</span><span class="n">i</span><span class="p">,</span> <span class="n">j</span><span class="p">]</span> <span class="o">+=</span> <span class="mi">2</span> <span class="o">*</span> <span class="n">eps</span>
            <span class="n">layer</span><span class="o">.</span><span class="n">forward</span><span class="p">(</span><span class="n">is_train</span><span class="o">=</span><span class="bp">True</span><span class="p">,</span> <span class="n">in_data</span><span class="p">,</span> <span class="n">out_data</span><span class="p">)</span>
            <span class="n">J2</span> <span class="o">=</span> <span class="n">loss_it</span><span class="p">(</span><span class="n">out_grad</span><span class="p">[</span><span class="s1">&#39;output&#39;</span><span class="p">])</span>
            <span class="n">gradient_expect</span> <span class="o">=</span> <span class="p">(</span><span class="n">J2</span> <span class="o">-</span> <span class="n">J1</span><span class="p">)</span> <span class="o">/</span> <span class="p">(</span><span class="mi">2</span> <span class="o">*</span> <span class="n">eps</span><span class="p">)</span>

            <span class="c1"># calculate relative error</span>
            <span class="n">error</span> <span class="o">=</span> <span class="nb">abs</span><span class="p">(</span><span class="n">gradient_expect</span> <span class="o">-</span> <span class="n">gradient</span><span class="p">)</span> <span class="o">/</span> <span class="p">(</span><span class="nb">abs</span><span class="p">(</span><span class="n">gradient</span><span class="p">)</span> <span class="o">+</span> <span class="nb">abs</span><span class="p">(</span><span class="n">gradient_expect</span><span class="p">))</span>
            <span class="k">if</span> <span class="n">error</span> <span class="o">&gt;</span> <span class="n">threshold</span><span class="p">:</span>
                <span class="k">print</span> <span class="s1">&#39;gradient check failed on X[</span><span class="si">%d</span><span class="s1">, </span><span class="si">%d</span><span class="s1">]&#39;</span><span class="o">%</span><span class="p">(</span><span class="n">i</span><span class="p">,</span> <span class="n">j</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="k">print</span> <span class="s1">&#39;gradient check pass&#39;</span>
</pre></div>


<p>You can refer to cs231n course note <a href="http://cs231n.github.io/neural-networks-3/">here</a> for more information about gradient check.</p>
<h3>Test within a toy model</h3>
<p>After your implementation pass the gradient check, you should put your Layer into the DL framework you use. This brings other important things in. How to develop a new Layer for the DL framework? Most DL frameworks shall have documents about how to write custom Layer or Operator. They also may offer a demonstration of writing the Layer in Python or C++. Read the document and the code, you also need to understand how the framework process the data and basic idea of how the framework run your Layer. If you want to write the code in C++/CUDA, the best way you can go is to read the source code of Layer implementation in the framework. They're the best examples you can refer to.</p>
<p>It's also important that you should use a small network and data set to verify the efficiency of your implementation. Sometimes, passing the gradient check doesn't really mean your Layer implementation is perfect. The gradient check can't cover all situation. There might be bugs that only happens in a rarely situation. Or for some of your Layer inputs, your implementation may have some numeric issue like float underflow which cause the result wrong. Since gradient check is not perfect, it's always a good idea to deploy your Layer implementation on a toy model and see if it works the way your want (at least it shouldn't give you the wrong result).</p>
<h3>Optimize your implementation</h3>
<p>Once you verify the correctness and efficiency of your Layer implementation, you may want to optimize it to get a better performance. Since most framework support using Python to implement the Layer, you can still stick to Python and optimize the code more vectorized. Then, you may want to implement it using CUDA which makes your Layer can run on GPUs. Nowadays, we depends so much on GPUs to run deep learning framework to train neural networks. You should learn some knowledge about <a href="https://developer.nvidia.com/cuda-zone">CUDA</a> if you want the implementation of your Layer gets better performance.</p>
<h3>Summary</h3>
<p>In a summary, If you need to implement a custom Layer for the deep learning framework, you should implement it using Python or some other language you are familiar and easy to debug. Do gradient check to verify the correctness of your implementation. Next, you need to put the Layer into the DL framework you use, this requires much that you also need to know how the framework handle and represent the Layer and Data. Train a toy network after your Layer can work with the framework to verify the efficiency. After all, if the performance is poor, you may need to optimize the Layer using CUDA which makes your Layer run on GPUs. You can take a look at <a href="https://github.com/luoyetx/mx-lsoftmax">luoyetx/mx-lsoftmax</a> for a reference. It's follow the pipeline I described above.</p>
<h3>References</h3>
<ul>
<li><a href="https://github.com/dmlc/mxnet">MXNet</a></li>
<li><a href="https://github.com/BVLC/caffe">Caffe</a></li>
<li><a href="https://www.tensorflow.org/">TensorFlow</a></li>
<li><a href="http://torch.ch/">Torch</a></li>
<li><a href="http://cs231n.stanford.edu/">cs231n</a></li>
<li><a href="https://github.com/luoyetx/mx-lsoftmax">mx-lsoftmax</a></li>
</ul>
