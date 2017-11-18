<h2 class="entry-title"><a href="https://yunmingzhang.wordpress.com/2015/01/19/how-to-create-your-own-layer-in-deep-learning-framework-caffe/" rel="bookmark">How to create your own layer in deep learning framework&nbsp;CAFFE</a></h2>					
					<div class="entry-meta">
						<span class="meta-prep meta-prep-author">Posted on</span> <a href="https://yunmingzhang.wordpress.com/2015/01/19/how-to-create-your-own-layer-in-deep-learning-framework-caffe/" title="8:07 pm" rel="bookmark"><span class="entry-date">January 19, 2015</span></a>						<span class="by-author"><span class="sep">by</span> <span class="author vcard"><a class="url fn n" href="https://yunmingzhang.wordpress.com/author/yunmingzhang17/" title="View all posts by yunmingzhang17" rel="author">yunmingzhang17</a></span> </span>					</div><!-- .entry-meta -->

					<div class="entry-content">
						<p>This is a post outlining the steps you need to take to create your own layer in CAFFE, a popular framework for writing convolutional neural networks. The post focuses on the latest version of CAFE as of Jan 2015.</p>
<p><span id="more-803"></span></p>
<p>NOTES:</p>
<ul>
<li>I use $CAFFEROOT and /caffe/ interchangeably, this is simply the root directory of the caffe installation.</li>
</ul>
<p>A general and slightly outdated tutorial can be found here (<a href="https://github.com/BVLC/caffe/wiki/Development" rel="nofollow">https://github.com/BVLC/caffe/wiki/Development</a>).</p>
<ol>
<li>Create the definition a new class in one of the .hpp files located in $CAFFEROOT/include/caffe/ . In my case, I am writing a customized convolution layer. As a result, I modify the vision_layers.hpp to add a definition of myConvLayer.</li>
<li>Next we need to create a myConvLayer.cpp file in the following path $CAFFEROOT/src/caffe/myConvLayer.cpp .
<ol>
<li>Implement the virtual methods required of the class. In my case, I needed to implement the required &#8220;LayerSetUp&#8221;, &#8220;Reshape&#8221;,&#8221;ForwardCPU&#8221; and &#8220;BackwardCPU&#8221;.</li>
</ol>
</li>
<li>Choose a name for your layer and write it in caffe/src/caffe/proto/caffe.proto
<ol>
<li>Find a message called LayerParameter</li>
<li>Find the latest unoccupied number, there should be a comment above the message declaration saying &#8220;the next available ID when you create&#8230;.&#8221;, use the smallestUnoccupiedNumber</li>
<li>Add your layer to the LayerType enum, for example, I add &#8220;MYCONVOLUTIONLAYER = 38&#8221;</li>
</ol>
</li>
<li>If you have completed step 1 and step 2, you should be able to just compile the entire CAFFE directory fine. The next steps will require you to actually write a network and run it to get the protobuf set up right. To do this, I recommend simply use an existing network. I chose MNIST LENET and replaced the convolution layer in (/caffe/examples/mnist_modified/lenet_train_test.protxt). To get it to run with my own set up, I
<ol>
<li>Created a modified directory(mint_modified) that copies minist in examples.</li>
<li>Change the lent_solver.prototxt to use my own file. CAFFE used hardcoded path, when it should have used relative path to find the training configuration set up.
<ol>
<li>TYPE = MYCONVOLUTION (depending on your declaration in the protobuf file in the previous step)</li>
</ol>
</li>
<li>Once you are done getting your own layer running within an existing network, it will crash immediately because we haven&#8217;t worked on getting</li>
</ol>
</li>
<li>Dealing with protobuf and layer_factory
<ol>
<li>Now you should see an error massage saying &#8220;unknown type 38&#8221; from a file called &#8220;layer_factory.cpp&#8221;. You can find the file at caffe/src/caffe/layer_factory.cpp. The error message tells you that currently CAFFE cannot recognize the parameter specified in the protobuf file &#8220;myconvolution&#8221;. To do this, you simply need to add a new case statement at the end of &#8220;layer_factory.cpp&#8221; file.</li>
<li>  case LayerParameter_LayerType_MYCONVOLUTION:return new MyConvolutionLayer&lt;Dtype&gt;(param);</li>
<li>This statement tells the system to use layer_factory to create the class whenever that parameter is being read</li>
</ol>
</li>
<li>The last part is to make sure that your own layers is using the parameters that you want.
<ol>
<li>An interesting note here is that the parameter has no fixed paring. The way it is specified in protobuf file for example, is nesting a parameter type within a layer type. As a result, you can switch the parameters among different layers. That is I could have used the original convolution_parameter inside MyConvolution layer.</li>
<li>To use my own set of parameter, I went back to caffe/src/caffe/proto/caffe.proto file
<ol>
<li>Define a new parameter type
<ol>
<li>&#8220;myconvolution_param = 42&#8221;</li>
</ol>
</li>
<li>Define a new message class
<ol>
<li>MyConvolutionPoolingParameter { optional uint32 num_output =1; &#8230;. }</li>
</ol>
</li>
<li>Then go back to the lenet_train_test.protxt file and set your layer to use the my convolution parameter in myconvolutionpooling layer.
<ol>
<li>An example layers { name:&#8217;myconv1&#8242; type:MYCONVOLUTION; &#8230;.. myconvolution_param { num_output: 20 kernel_size &#8230;.}}</li>
</ol>
</li>
<li>One last step is modifying the $CAFFEROOT/src/caffe/myConvLayer.cpp to use the my convolution_param. You can access the parameters by coding             &#8220;ConvolutionPoolingParameter convpool_param =                                                    this-&gt;layer_param_.convolutionpooling_param();&#8221;</li>
</ol>
</li>
</ol>
</li>
</ol>
<p>Now, you have fully functional customized layer with its own parameters! This tutorial applies not only to some modified convolution layer but can be used for any kind of new layer.</p>
<p>Cheers!</p>
