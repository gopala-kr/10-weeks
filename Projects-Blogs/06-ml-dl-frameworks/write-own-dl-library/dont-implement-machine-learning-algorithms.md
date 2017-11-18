<h1 class="title entry-title">Stop Coding Machine Learning Algorithms From Scratch</h1>	</header>
<div class="post-meta"><span class="small">By</span> <span class="author vcard"><span class="fn"><a href="https://machinelearningmastery.com/author/jasonb/" title="Posts by Jason Brownlee" rel="author">Jason Brownlee</a></span></span> <span class="small">on</span> <abbr class="date time published updated" title="2016-10-05T05:00:00+1100">October 5, 2016</abbr>  <span class="small">in</span> <span class="categories"><a href="https://machinelearningmastery.com/category/machine-learning-algorithms/" title="View all items in Machine Learning Algorithms">Machine Learning Algorithms</a></span>  </div>
	<section class="entry">
<div class='apss-social-share apss-theme-4 clearfix'>


				<div class='apss-twitter apss-single-icon'>
					<a rel='nofollow'  onclick="apss_open_in_popup_window(event, 'https://twitter.com/intent/tweet?text=Stop%20Coding%20Machine%20Learning%20Algorithms%20From%20Scratch&amp;url=https%3A%2F%2Fmachinelearningmastery.com%2Fdont-implement-machine-learning-algorithms%2F&amp;');" href='javascript:void(0);'  title="Share on Twitter" target=''>
						<div class='apss-icon-block clearfix'>
							<i class='fa fa-twitter'></i>
							<span class='apss-social-text'>Share on Twitter</span><span class='apss-share'>Tweet</span>
						</div>
											</a>
				</div>
								<div class='apss-facebook apss-single-icon'>
					<a rel='nofollow'  onclick="apss_open_in_popup_window(event, 'https://www.facebook.com/sharer/sharer.php?u=https://machinelearningmastery.com/dont-implement-machine-learning-algorithms/');"  title="Share on Facebook" target='' href='https://www.facebook.com/sharer/sharer.php?u=https://machinelearningmastery.com/dont-implement-machine-learning-algorithms/'>
						<div class='apss-icon-block clearfix'>
							<i class='fa fa-facebook'></i>
							<span class='apss-social-text'>Share on Facebook</span>
							<span class='apss-share'>Share</span>
						</div>
											</a>
				</div>
				
				<div class='apss-linkedin apss-single-icon'>
					<a rel='nofollow'  onclick="apss_open_in_popup_window(event, 'http://www.linkedin.com/shareArticle?mini=true&amp;title=Stop%20Coding%20Machine%20Learning%20Algorithms%20From%20Scratch&amp;url=https://machinelearningmastery.com/dont-implement-machine-learning-algorithms/&amp;summary=You+Don%27t+Have+To+Implement+Algorithms%0D%0A...if+you%E2%80%99re+a+beginner+and+just+getting+started.%0D%0AStop.%0D%0A...');"  title="Share on LinkedIn" target='' href='http://www.linkedin.com/shareArticle?mini=true&amp;title=Stop%20Coding%20Machine%20Learning%20Algorithms%20From%20Scratch&amp;url=https://machinelearningmastery.com/dont-implement-machine-learning-algorithms/&amp;summary=You+Don%27t+Have+To+Implement+Algorithms%0D%0A...if+you%E2%80%99re+a+beginner+and+just+getting+started.%0D%0AStop.%0D%0A...'>
						<div class='apss-icon-block clearfix'><i class='fa fa-linkedin'></i>
							<span class='apss-social-text'>Share on LinkedIn</span>
							<span class='apss-share'>Share</span>
						</div>
											</a>
				</div>
								<div class='apss-google-plus apss-single-icon'>
					<a rel='nofollow'  onclick="apss_open_in_popup_window(event, 'https://plus.google.com/share?url=https://machinelearningmastery.com/dont-implement-machine-learning-algorithms/');"  title="Share on Google Plus" target='' href='https://plus.google.com/share?url=https://machinelearningmastery.com/dont-implement-machine-learning-algorithms/'>
						<div class='apss-icon-block clearfix'>
							<i class='fa fa-google-plus'></i>
							<span class='apss-social-text'>Share on Google Plus</span>
							<span class='apss-share'>Share</span>
						</div>
											</a>
				</div>
				</div><h3 style="text-align: center;">You Don&#8217;t Have To Implement Algorithms<br />
&#8230;<em>if you’re a beginner and just getting started.</em></h3>
<p>Stop.</p>
<p>Are you implementing a machine learning algorithm at the moment?</p>
<p>Why?</p>
<p>Implementing algorithms from scratch is one of the biggest mistakes I see beginners make.</p>
<p>In this post you will discover:</p>
<ul>
<li>The algorithm implementation trap that beginners fall into.</li>
<li>The very real difficulty of engineering world-class implementations of machine learning algorithms.</li>
<li>Why you should be using off-the-shelf implementations.</li>
</ul>
<p>Let&#8217;s get started.</p>
<div id="attachment_3282" style="max-width: 650px" class="wp-caption aligncenter"><img class="size-full wp-image-3282" src="https://3qeqpr26caki16dnhd19sv6by6v-wpengine.netdna-ssl.com/wp-content/uploads/2016/10/Dont-Implement-Machine-Learning-Algorithms-1.jpg" alt="Don't Implement Machine Learning Algorithms" width="640" height="424" srcset="https://3qeqpr26caki16dnhd19sv6by6v-wpengine.netdna-ssl.com/wp-content/uploads/2016/10/Dont-Implement-Machine-Learning-Algorithms-1.jpg 640w, https://3qeqpr26caki16dnhd19sv6by6v-wpengine.netdna-ssl.com/wp-content/uploads/2016/10/Dont-Implement-Machine-Learning-Algorithms-1-300x199.jpg 300w" sizes="(max-width: 640px) 100vw, 640px" /><p class="wp-caption-text">Don&#8217;t Implement Machine Learning Algorithms<br />Photo by <a href="https://www.flickr.com/photos/kirandulo/16555448595/">kirandulo</a>, some rights reserved.</p></div>
<h2>Caught In The Implementation Trap</h2>
<p>Here&#8217;s a snippet of an email I received:</p>
<blockquote><p>&#8230; I am really struggling. Why do I have to implement algorithms from scratch?</p></blockquote>
<p>It seems that a lot of developers get caught in this challenge.</p>
<p>They are told or imply that:</p>
<p style="text-align: center;"><strong>Algorithms must be implemented<br />
before being used.</strong></p>
<p>Or that:</p>
<p style="text-align: center;"><strong>You can only learn machine learning by<br />
implementing algorithms.</strong></p>
<p>Here are some similar questions I stumbled across:</p>
<ul>
<li><em>Why is there a need to manually implement machine learning algorithms when there are many advanced APIs like </em>tensorflow<em> available?</em> (<a href="https://www.quora.com/Why-is-there-a-need-to-manually-implement-machine-learning-algorithms-when-there-are-many-advanced-APIs-like-tensorflow-available">on Quora</a>)</li>
<li><em>Is there any value implementing machine learning algorithms by yourself or should you use libraries?</em> (<a href="https://www.quora.com/Is-there-any-value-implementing-machine-learning-algorithms-by-yourself-or-should-you-use-libraries">on Quora</a>)</li>
<li><em>Is it useful to implement machine learning algorithms?</em> (<a href="https://www.quora.com/Is-it-useful-to-implement-machine-learning-algorithms">on Quora</a>)</li>
<li><em>Which programming language should I use to implement Machine Learning algorithms?</em> (<a href="https://www.quora.com/Which-programming-language-should-I-use-to-implement-Machine-Learning-algorithms">on Quora</a>)</li>
<li><em>Why do you and other people sometimes implement machine learning algorithms from scratch?</em> (<a href="https://github.com/rasbt/python-machine-learning-book/blob/master/faq/implementing-from-scratch.md">on GitHub</a>)</li>
</ul>
<h2>You&#8217;re Probably Doing it Wrong</h2>
<p>You don&#8217;t have to implement machine learning algorithms from scratch.</p>
<p>This is a part of the bottom-up approach traditionally used to teach machine learning.</p>
<ol>
<li>Learn Math.</li>
<li>Learn Theory.</li>
<li>Implement Algorithm From Scratch.</li>
<li><em>??? (magic happens here</em>).</li>
<li>Apply Machine Learning.</li>
</ol>
<p>It is a lot easier to apply machine learning algorithms to a problem and get a result than it is to implement them from scratch.</p>
<p style="text-align: center;"><strong>A Lot Easier!</strong></p>
<p>Learning how to use an algorithm rather than implement an algorithm is not only easier, it is a more valuable skill. A skill that you can start using to make a real impact very quickly.</p>
<p>There&#8217;s a lot of low-hanging fruit that you can pick with applied machine learning.</p>
<h2>Implementing Machine Learning Algorithms Well<br />
&#8230;is Really Hard!</h2>
<p>Algorithms that you use to solve business problems need to be <strong>fast</strong> and <strong>correct</strong>.</p>
<h3>Fast Algorithms</h3>
<p>The more sophisticated nonlinear methods require a lot more data than their linear counterparts.</p>
<p>This means they need to do a lot of work, which may take a long time.</p>
<p>Algorithms need to be fast to process through all of this data. Especially, at scale.</p>
<p>This may require a re-interpretation of the linear algebra that underlies the method in such a way that best suits a specific matrix operation in an underlying library.</p>
<p>It may require specialized knowledge of caching to make the most of your hardware.</p>
<p>These are not ad hoc tricks that come together after you get a &#8220;<em>hello world</em>&#8221; implementation working. These are engineering challenges that encompass the algorithm implementation project.</p>
<h3>Correct Algorithms</h3>
<p>Machine learning algorithms will give you a result, even when their implementation is crippled.</p>
<p>You get a number. An output. A prediction.</p>
<p>Sometimes the prediction is correct and sometimes it is not.</p>
<p>Machine learning algorithms use randomness. <a href="http://machinelearningmastery.com/randomness-in-machine-learning/">They are stochastic algorithms</a>.</p>
<p>This is not just a matter of unit tests, it is a matter of having a deep understanding of the technique and devising cases to prove the implementation is as expected and edge cases are handled.</p>
<h2>Use An Off-The-Shelf Implementation</h2>
<p>You may be an excellent engineer.</p>
<p>But your &#8220;<em>hello world</em>&#8221; implementation of an algorithm will probably not cut-it when compared to an off-the-shelf implementation.</p>
<p>Your implementation will probably be based on a textbook description, meaning it will be naive and slow. And you may or may not have the expertise to devise tests to ensure the correctness of your implementation.</p>
<p>Off-the-shelf implementations in open source libraries are built for speed and/or robustness.</p>
<p style="text-align: center;"><strong>How could you not use a standard machine learning library?</strong></p>
<p>They may be tailored to a very narrow problem type intended to be as fast as possible. They may also be intended for general purpose use, ensuring they operate correctly on a wide range of problems, beyond those you have considered.</p>
<h3>Libraries Are Not All Created Equal</h3>
<p>Not all algorithm implementations you download off the Internet are created equal.</p>
<p>The code snippet from GitHub maybe a grad students &#8220;<em>hello world</em>&#8221; implementation, or it may be the highly optimized implementation contributed to by the entire research team at a large organization.</p>
<p>You need to evaluate the source of the code you are using. Some sources are better or more reliable than others.</p>
<p>General purposes libraries are often more robust at the cost of some speed.</p>
<p>Lighting fast implementations by hacker-engineers often suffer poor documentation and are highly pedantic when it comes to their expectations.</p>
<p>Consider this when you pick your implementation.</p>
<h3>Recommendations</h3>
<p>When asked, I typically recommend one of three platforms:</p>
<ol>
<li><strong>Weka</strong>. A graphical user interface that does not require any code. Perfect if you want to focus on the machine learning first and learning how to work through problems.</li>
<li><strong>Python</strong>. The ecosystem including pandas and scikit-learn. Excellent for stitching together a solution to a machine learning problem in development that is robust enough to also be deployed into operations.</li>
<li><strong>R</strong>. The more advanced platform that although has an esoteric language and sometimes buggy packages, offers access to state-of-the-art methods written directly by academics. Great for one-off projects and R&amp;D.</li>
</ol>
<p>These are just my recommendations, there are many more machine learning platforms to choose from.</p>
<h2>Sometimes You Must Implement</h2>
<p>You do not have to implement machine learning algorithms when getting started in machine learning.</p>
<p>But you can.</p>
<p>And there can be very good reasons for doing so.</p>
<p>For example here are 3 big reasons:</p>
<ul>
<li>You want to implement to learn how the algorithm works.</li>
<li>There is no available implementation of the algorithm you need.</li>
<li>There is no suitable (fast enough, etc.) implementation of the algorithm you need.</li>
</ul>
<p>The first is my favorite. It&#8217;s the one that may have confused you.</p>
<p>You can implement machine learning algorithms to learn how they work. I recommend it. It&#8217;s very efficient for developers to learn this way.</p>
<p>But.</p>
<p>You do not have to <strong>start</strong> by implementing machine learning algorithms. You will build your confidence and skill in machine learning a lot faster by learning how to use machine learning algorithms before implementing them.</p>
<p>The implementation and any research required to complete the implementation would then be an improvement on your understanding. An addition that would help you to get better results the next time you used that algorithm.</p>
<h2>Summary</h2>
<p>In this post, you discovered that beginners fall into the trap of implementing machine learning algorithms from scratch.</p>
<p style="text-align: center;"><strong>They are told that it&#8217;s the only way.</strong></p>
<p>You discovered that engineering fast and robust implementations of machine learning algorithms is a tough challenge.</p>
<p>You learned that it is much easier and more desirable to learn how to use machine learning algorithms before implementing them. You also learned that implementing algorithms is a great way to learn more about how they work and get more from them, but only after you know how to use them.</p>
<p style="text-align: center;"><strong>Have you been caught in this trap?</strong><br />
<em>Share your experiences in the comments.</em></p>
<h3>Further Reading</h3>
<ul>
<li><a href="http://machinelearningmastery.com/mistakes-programmers-make-when-starting-in-machine-learning/">5 Mistakes Programmers Make when Starting in Machine Learning</a></li>
<li><a href="http://machinelearningmastery.com/understand-machine-learning-algorithms-by-implementing-them-from-scratch/">Understand Machine Learning Algorithms By Implementing Them From Scratch</a></li>
<li><a href="http://machinelearningmastery.com/benefits-of-implementing-machine-learning-algorithms-from-scratch/">Benefits of Implementing Machine Learning Algorithms From Scratch</a></li>
</ul>
<div class="awac-wrapper"><div class="awac widget text-36">			<div class="textwidget"><p><div class="woo-sc-hr"></div><br />
<center></p>
<h2 style="text-align: center;">Frustrated With Machine Learning Math?</h2>
<p><a href="/master-machine-learning-algorithms/"><img style="border: 0;" src="https://3qeqpr26caki16dnhd19sv6by6v-wpengine.netdna-ssl.com/wp-content/uploads/2016/03/MasterMachineLearningAlgorithms-small.png" alt="Mater Machine Learning Algorithms" align="left" /></a></p>
<h4 style="text-align: center;">See How Algorithms Work in Minutes</h4>
<p style="text-align: center;">&#8230;with just arithmetic and simple examples</p>
<p style="text-align: center;">Discover how in my new Ebook: <a href="/master-machine-learning-algorithms/">Master Machine Learning Algorithms</a></p>
<p style="text-align: center;">It covers <strong>explanations</strong> and <strong>examples</strong> of <strong>10 top algorithms</strong>, like:<br /><em>Linear Regression</em>, <em>k-Nearest Neighbors</em>, <em>Support Vector Machines</em> and much more&#8230;</p>
<h4 style="text-align: center;">Finally, Pull Back the Curtain on <br />Machine Learning Algorithms</h4>
<p style="text-align: center;">Skip the Academics. Just Results.</p>
<p style="text-align: center;"><a href="/master-machine-learning-algorithms/">Click to learn more</a>.</p>
<p></center><br />
<div class="woo-sc-hr"></div></p>
