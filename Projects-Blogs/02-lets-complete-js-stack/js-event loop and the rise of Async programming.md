 <div class="postArticle-content js-postField js-notesSource js-trackedPost" data-post-id="2f077c4438b5" data-source="post_page" data-collection-id="12d1b859d4e4" data-tracking-context="postPage">
                            <section name="f002" class="section section--body section--first section--last">
                                <div class="section-divider">
                                    <hr class="section-divider">
                                </div>
                                <div class="section-content">
                                    <div class="section-inner sectionLayout--insetColumn">
                                        <h1 name="e04e" id="e04e" class="graf graf--h3 graf--leading graf--title">Event loop and the rise of Async programming + 5 ways to better coding with async/await</h1>
                                        <p name="f653" id="f653" class="graf graf--p graf-after--h3">Welcome to post # 4 of the series dedicated to exploring JavaScript and its building components. In the process of identifying and describing the core elements, we also share some rules of thumb we use when building <a href="https://www.sessionstack.com/" data-href="https://www.sessionstack.com/" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">SessionStack</a>, a JavaScript application that has to be robust and highly-performant in order to stay competitive.</p>
                                        <p name="fbf6" id="fbf6" class="graf graf--p graf-after--p">Did you miss the first three chapters? You can find them here:</p>
                                        <ol class="postList">
                                            <li name="7709" id="7709" class="graf graf--li graf-after--p"><a href="https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf?source=collection_home---2------1----------------" data-href="https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf?source=collection_home---2------1----------------" class="markup--anchor markup--li-anchor" target="_blank">An overview of the engine, the runtime, and the call stack</a></li>
                                            <li name="3598" id="3598" class="graf graf--li graf-after--li"><a href="https://blog.sessionstack.com/how-javascript-works-inside-the-v8-engine-5-tips-on-how-to-write-optimized-code-ac089e62b12e?source=collection_home---2------2----------------" data-href="https://blog.sessionstack.com/how-javascript-works-inside-the-v8-engine-5-tips-on-how-to-write-optimized-code-ac089e62b12e?source=collection_home---2------2----------------" class="markup--anchor markup--li-anchor" target="_blank">Inside Google’s V8 engine + 5 tips on how to write optimized code</a></li>
                                            <li name="272a" id="272a" class="graf graf--li graf-after--li"><a href="https://blog.sessionstack.com/how-javascript-works-memory-management-how-to-handle-4-common-memory-leaks-3f28b94cfbec?source=collection_home---2------0----------------" data-href="https://blog.sessionstack.com/how-javascript-works-memory-management-how-to-handle-4-common-memory-leaks-3f28b94cfbec?source=collection_home---2------0----------------" class="markup--anchor markup--li-anchor" target="_blank">Memory management + how to handle 4 common memory leaks</a></li>
                                        </ol>
                                        <p name="f139" id="f139" class="graf graf--p graf-after--li">This time we’ll expand on our first post by reviewing the drawbacks to programming in a single-threaded environment and how to overcome them to build stunning JavaScript UIs. As the tradition goes, at the end of the article we’ll share 5 tips on how to write cleaner code with async/await.</p>
                                        <h4 name="98f1" id="98f1" class="graf graf--h4 graf-after--p"><strong class="markup--strong markup--h4-strong">Why having a single thread is a limitation?</strong></h4>
                                        <p name="7279" id="7279" class="graf graf--p graf-after--h4">In the <a href="https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf" data-href="https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf" class="markup--anchor markup--p-anchor" target="_blank">first post</a> we launched, we pondered over the question <em class="markup--em markup--p-em">what happens when you have function calls in the Call Stack that take a huge amount of time to be processed</em>.</p>
                                        <p name="4203" id="4203" class="graf graf--p graf-after--p">Imagine, for example, a complex image transformation algorithm that’s running in the browser.</p>
                                        <p name="2239" id="2239" class="graf graf--p graf-after--p">While the Call Stack has functions to execute, the browser can’t do anything else — it’s being blocked. This means that the browser can’t render, it can’t run any other code, it’s just stuck. And here comes the problem — your app UI is no longer efficient and pleasing.</p>
                                        <p name="7998" id="7998" class="graf graf--p graf-after--p">Your app <strong class="markup--strong markup--p-strong">is stuck</strong>.</p>
                                        <p name="2029" id="2029" class="graf graf--p graf-after--p">In some cases, this might not be such a critical issue. But hey — here’s an even bigger problem. Once your browser starts processing too many tasks in the Call Stack, it may stop being responsive for a long time. At that point, a lot of browsers would take action by raising an error, asking whether they should terminate the page:</p>
                                        <p name="cde0" id="cde0" class="graf graf--p graf-after--p">It’s ugly, and it completely ruins your UX:</p>
                                        <figure name="0810" id="0810" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 461px; max-height: 283px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 61.4%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*MCt4ZC0dMVhJsgo1u6lpYw.jpeg" data-width="461" data-height="283"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*MCt4ZC0dMVhJsgo1u6lpYw.jpeg?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*MCt4ZC0dMVhJsgo1u6lpYw.jpeg">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*MCt4ZC0dMVhJsgo1u6lpYw.jpeg"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <h4 name="5851" id="5851" class="graf graf--h4 graf-after--figure"><strong class="markup--strong markup--h4-strong">The building blocks of a JavaScript program</strong></h4>
                                        <p name="5b39" id="5b39" class="graf graf--p graf-after--h4">You may be writing your JavaScript application in a single .js file, but your program is almost certainly comprised of several blocks, only one of which is going to execute <em class="markup--em markup--p-em">now</em>, and the rest will execute <em class="markup--em markup--p-em">later</em>. The most common block unit is the function.</p>
                                        <p name="edb4" id="edb4" class="graf graf--p graf-after--p">The problem most developers new to JavaScript seem to have is understanding that <em class="markup--em markup--p-em">later</em> doesn’t necessarily happen strictly and immediately after <em class="markup--em markup--p-em">now</em>. In other words, tasks that cannot complete <em class="markup--em markup--p-em">now</em> are, by definition, going to complete asynchronously, which means you won’t have the above-mentioned blocking behavior as you might have subconsciously expected or hoped for.</p>
                                        <p name="31f3" id="31f3" class="graf graf--p graf-after--p">Let’s take a look at the following example:</p>
                                        <figure name="f0df" id="f0df" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/6bdbdb8c4c88020df1d3f931693c130f?postId=2f077c4438b5" data-media-id="6bdbdb8c4c88020df1d3f931693c130f" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/6bdbdb8c4c88020df1d3f931693c130f?postId=2f077c4438b5" data-media-id="6bdbdb8c4c88020df1d3f931693c130f" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="2292" id="2292" class="graf graf--p graf-after--figure">You’re probably aware that standard Ajax requests don’t complete synchronously, which means that at the time of code execution the ajax(..) function does not yet have any value to return back to be assigned to a response variable.</p>
                                        <p name="8886" id="8886" class="graf graf--p graf-after--p">A simple way of “waiting” for an asynchronous function to return its result is to use a function called <strong class="markup--strong markup--p-strong">callback:</strong></p>
                                        <figure name="39e9" id="39e9" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/c34c238d7ddeed529537915638aa8779?postId=2f077c4438b5" data-media-id="c34c238d7ddeed529537915638aa8779" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/c34c238d7ddeed529537915638aa8779?postId=2f077c4438b5" data-media-id="c34c238d7ddeed529537915638aa8779" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="e0f4" id="e0f4" class="graf graf--p graf-after--figure">Just a note: you can actually make <strong class="markup--strong markup--p-strong">synchronous</strong> Ajax requests. Never, ever do that. If you make a synchronous Ajax request, the UI of your JavaScript app will be blocked — the user won’t be able to click, enter data, navigate, or scroll. This would prevent any user interaction. It’s a terrible practice.</p>
                                        <p name="5588" id="5588" class="graf graf--p graf-after--p">This is how it looks like, but please, never do this — don’t ruin the web:</p>
                                        <figure name="50bf" id="50bf" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/0e69697a76a00fde24b088503e82732c?postId=2f077c4438b5" data-media-id="0e69697a76a00fde24b088503e82732c" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/0e69697a76a00fde24b088503e82732c?postId=2f077c4438b5" data-media-id="0e69697a76a00fde24b088503e82732c" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="2ba4" id="2ba4" class="graf graf--p graf-after--figure">We used an Ajax request just as an example. You can have any chunk of code execute asynchronously.</p>
                                        <p name="0264" id="0264" class="graf graf--p graf-after--p">This can be done with the <code class="markup--code markup--p-code">setTimeout(callback, milliseconds)</code> function. What the <code class="markup--code markup--p-code">setTimeout</code> function does is to set up an event (a timeout) to happen later. Let’s take a look:</p>
                                        <figure name="84de" id="84de" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/4113c6ccb03f5ae398ff8a0beb905955?postId=2f077c4438b5" data-media-id="4113c6ccb03f5ae398ff8a0beb905955" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/4113c6ccb03f5ae398ff8a0beb905955?postId=2f077c4438b5" data-media-id="4113c6ccb03f5ae398ff8a0beb905955" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="2317" id="2317" class="graf graf--p graf-after--figure">The output in the console will be the following:</p><pre name="a8dd" id="a8dd" class="graf graf--pre graf-after--p">first<br>third<br>second</pre>
                                        <h4 name="4156" id="4156" class="graf graf--h4 graf-after--pre"><strong class="markup--strong markup--h4-strong">Dissecting the Event Loop</strong></h4>
                                        <p name="572e" id="572e" class="graf graf--p graf-after--h4">We’ll start with a somewhat of an odd claim — despite allowing async JavaScript code (like the <code class="markup--code markup--p-code">setTimeout</code> we just discussed), until ES6, JavaScript itself has actually never had any direct notion of asynchrony built into it. The JavaScript engine has never done anything more than executing a single chunk of your program at any given moment.</p>
                                        <p name="a479" id="a479" class="graf graf--p graf-after--p">For more details on how JavaScript engines work (Google’s V8 specifically), check one of our <a href="https://blog.sessionstack.com/how-javascript-works-inside-the-v8-engine-5-tips-on-how-to-write-optimized-code-ac089e62b12e" data-href="https://blog.sessionstack.com/how-javascript-works-inside-the-v8-engine-5-tips-on-how-to-write-optimized-code-ac089e62b12e" class="markup--anchor markup--p-anchor" target="_blank">previous articles</a> on the topic.</p>
                                        <p name="9e3c" id="9e3c" class="graf graf--p graf-after--p">So, who tells the JS Engine to execute chunks of your program? In reality, the JS Engine doesn’t run in isolation — it runs inside a <em class="markup--em markup--p-em">hosting</em>environment, which for most developers is the typical web browser or Node.js. Actually, nowadays, JavaScript gets embedded into all kinds of devices, from robots to light bulbs. Every single device represents a different type of hosting environment for the JS Engine.</p>
                                        <p name="ef5e" id="ef5e" class="graf graf--p graf-after--p">The common denominator in all environments is a built-in mechanism called the <strong class="markup--strong markup--p-strong">event loop, </strong>which handles the execution of multiple chunks of your program over time, each time invoking the JS Engine.</p>
                                        <p name="4e3d" id="4e3d" class="graf graf--p graf-after--p">This means that the JS Engine is just an on-demand execution environment for any arbitrary JS code. It’s the surrounding environment that schedules the events (the JS code executions).</p>
                                        <p name="e4f0" id="e4f0" class="graf graf--p graf-after--p">So, for example, when your JavaScript program makes an Ajax request to fetch some data from the server, you set up the “response” code in a function (the “callback”), and the JS Engine tells the hosting environment:
                                            <br>“Hey, I’m going to suspend execution for now, but whenever you finish with that network request, and you have some data, please <em class="markup--em markup--p-em">call</em> this function <em class="markup--em markup--p-em">back</em>.”</p>
                                        <p name="1301" id="1301" class="graf graf--p graf-after--p">The browser is then set up to listen for the response from the network, and when it has something to return to you, it will schedule the callback function to be executed by inserting it into the <em class="markup--em markup--p-em">event loop</em>.</p>
                                        <p name="3b0e" id="3b0e" class="graf graf--p graf-after--p">Let’s look at the below diagram:</p>
                                        <figure name="cbbe" id="cbbe" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*FA9NGxNB6-v1oI2qGEtlRQ.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*FA9NGxNB6-v1oI2qGEtlRQ.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*FA9NGxNB6-v1oI2qGEtlRQ.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*FA9NGxNB6-v1oI2qGEtlRQ.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*FA9NGxNB6-v1oI2qGEtlRQ.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="42b2" id="42b2" class="graf graf--p graf-after--figure">You can read more about the Memory Heap and the Call Stack in our <a href="https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf" data-href="https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf" class="markup--anchor markup--p-anchor" target="_blank">previous article</a>.</p>
                                        <p name="6630" id="6630" class="graf graf--p graf-after--p">And what are these Web APIs? In essence, they are threads that you can’t access, you can just make calls to them. They are the pieces of the browser in which concurrency kicks in. If you’re a Node.js developer, these are the C++ APIs.</p>
                                        <p name="1698" id="1698" class="graf graf--p graf-after--p">So what is the <em class="markup--em markup--p-em">event loop after all</em>?</p>
                                        <figure name="086e" id="086e" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 478px; max-height: 162px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 33.900000000000006%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*KGBiAxjeD9JT2j6KDo0zUg.png" data-width="478" data-height="162"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*KGBiAxjeD9JT2j6KDo0zUg.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*KGBiAxjeD9JT2j6KDo0zUg.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*KGBiAxjeD9JT2j6KDo0zUg.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="2281" id="2281" class="graf graf--p graf-after--figure">The Event Loop has one simple job — to monitor the Call Stack and the Callback Queue. If the Call Stack is empty, it will take the first event from the queue and will push it to the Call Stack, which effectively runs it.</p>
                                        <p name="d321" id="d321" class="graf graf--p graf-after--p">Such an iteration is called a <strong class="markup--strong markup--p-strong">tick </strong>in the Event Loop. Each event is just a function callback.</p>
                                        <figure name="a04e" id="a04e" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/c2fc5c01fc6e08de757a1798d29b373b?postId=2f077c4438b5" data-media-id="c2fc5c01fc6e08de757a1798d29b373b" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/c2fc5c01fc6e08de757a1798d29b373b?postId=2f077c4438b5" data-media-id="c2fc5c01fc6e08de757a1798d29b373b" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="0b64" id="0b64" class="graf graf--p graf-after--figure">Let’s “execute” this code and see what happens:</p>
                                        <ol class="postList">
                                            <li name="b3a1" id="b3a1" class="graf graf--li graf-after--p">The state is clear. The browser console is clear, and the Call Stack is empty.</li>
                                        </ol>
                                        <figure name="4ccb" id="4ccb" class="graf graf--figure graf-after--li">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*9fbOuFXJHwhqa6ToCc_v2A.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*9fbOuFXJHwhqa6ToCc_v2A.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*9fbOuFXJHwhqa6ToCc_v2A.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*9fbOuFXJHwhqa6ToCc_v2A.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*9fbOuFXJHwhqa6ToCc_v2A.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="d56e" id="d56e" class="graf graf--p graf-after--figure">2. <code class="markup--code markup--p-code">console.log(&#39;Hi&#39;)</code> is added to the Call Stack.</p>
                                        <figure name="1d1f" id="1d1f" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*dvrghQCVQIZOfNC27Jrtlw.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*dvrghQCVQIZOfNC27Jrtlw.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*dvrghQCVQIZOfNC27Jrtlw.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*dvrghQCVQIZOfNC27Jrtlw.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*dvrghQCVQIZOfNC27Jrtlw.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="4a06" id="4a06" class="graf graf--p graf-after--figure">3. <code class="markup--code markup--p-code">console.log(&#39;Hi&#39;)</code> is executed.</p>
                                        <figure name="5fcc" id="5fcc" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*yn9Y4PXNP8XTz6mtCAzDZQ.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*yn9Y4PXNP8XTz6mtCAzDZQ.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*yn9Y4PXNP8XTz6mtCAzDZQ.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*yn9Y4PXNP8XTz6mtCAzDZQ.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*yn9Y4PXNP8XTz6mtCAzDZQ.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="20b3" id="20b3" class="graf graf--p graf-after--figure">4. <code class="markup--code markup--p-code">console.log(&#39;Hi&#39;)</code> is removed from the Call Stack.</p>
                                        <figure name="0520" id="0520" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*iBedryNbqtixYTKviPC1tA.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*iBedryNbqtixYTKviPC1tA.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*iBedryNbqtixYTKviPC1tA.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*iBedryNbqtixYTKviPC1tA.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*iBedryNbqtixYTKviPC1tA.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="5c37" id="5c37" class="graf graf--p graf-after--figure">5. <code class="markup--code markup--p-code">setTimeout(function cb1() { ... })</code> is added to the Call Stack.</p>
                                        <figure name="a1ae" id="a1ae" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*HIn-BxIP38X6mF_65snMKg.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*HIn-BxIP38X6mF_65snMKg.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*HIn-BxIP38X6mF_65snMKg.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*HIn-BxIP38X6mF_65snMKg.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*HIn-BxIP38X6mF_65snMKg.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="d37c" id="d37c" class="graf graf--p graf-after--figure">6. <code class="markup--code markup--p-code">setTimeout(function cb1() { ... })</code> is executed. The browser creates a timer as part of the Web APIs. It is going to handle the countdown for you.</p>
                                        <figure name="3d4b" id="3d4b" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*vd3X2O_qRfqaEpW4AfZM4w.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*vd3X2O_qRfqaEpW4AfZM4w.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*vd3X2O_qRfqaEpW4AfZM4w.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*vd3X2O_qRfqaEpW4AfZM4w.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*vd3X2O_qRfqaEpW4AfZM4w.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="b724" id="b724" class="graf graf--p graf-after--figure">7. The <code class="markup--code markup--p-code">setTimeout(function cb1() { ... })</code> itself is complete and is removed from the Call Stack.</p>
                                        <figure name="9dc4" id="9dc4" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*_nYLhoZPKD_HPhpJtQeErA.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*_nYLhoZPKD_HPhpJtQeErA.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*_nYLhoZPKD_HPhpJtQeErA.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*_nYLhoZPKD_HPhpJtQeErA.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*_nYLhoZPKD_HPhpJtQeErA.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="1a2a" id="1a2a" class="graf graf--p graf-after--figure">8. <code class="markup--code markup--p-code">console.log(&#39;Bye&#39;)</code> is added to the Call Stack.</p>
                                        <figure name="b686" id="b686" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*1NAeDnEv6DWFewX_C-L8mg.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*1NAeDnEv6DWFewX_C-L8mg.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*1NAeDnEv6DWFewX_C-L8mg.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*1NAeDnEv6DWFewX_C-L8mg.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*1NAeDnEv6DWFewX_C-L8mg.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="9739" id="9739" class="graf graf--p graf-after--figure">9. <code class="markup--code markup--p-code">console.log(&#39;Bye&#39;)</code> is executed.</p>
                                        <figure name="ba8c" id="ba8c" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*UwtM7DmK1BmlBOUUYEopGQ.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*UwtM7DmK1BmlBOUUYEopGQ.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*UwtM7DmK1BmlBOUUYEopGQ.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*UwtM7DmK1BmlBOUUYEopGQ.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*UwtM7DmK1BmlBOUUYEopGQ.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="dc8c" id="dc8c" class="graf graf--p graf-after--figure">10. <code class="markup--code markup--p-code">console.log(&#39;Bye&#39;)</code> is removed from the Call Stack.</p>
                                        <figure name="2875" id="2875" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*-vHNuJsJVXvqq5dLHPt7cQ.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*-vHNuJsJVXvqq5dLHPt7cQ.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*-vHNuJsJVXvqq5dLHPt7cQ.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*-vHNuJsJVXvqq5dLHPt7cQ.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*-vHNuJsJVXvqq5dLHPt7cQ.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="09f7" id="09f7" class="graf graf--p graf-after--figure">11. After at least 5000 ms, the timer completes and it pushes the <code class="markup--code markup--p-code">cb1</code> callback to the Callback Queue.</p>
                                        <figure name="6818" id="6818" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*eOj6NVwGI2N78onh6CuCbA.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*eOj6NVwGI2N78onh6CuCbA.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*eOj6NVwGI2N78onh6CuCbA.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*eOj6NVwGI2N78onh6CuCbA.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*eOj6NVwGI2N78onh6CuCbA.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="4a4c" id="4a4c" class="graf graf--p graf-after--figure">12. The Event Loop takes <code class="markup--code markup--p-code">cb1</code> from the Callback Queue and pushes it to the Call Stack.</p>
                                        <figure name="0d90" id="0d90" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*jQMQ9BEKPycs2wFC233aNg.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*jQMQ9BEKPycs2wFC233aNg.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*jQMQ9BEKPycs2wFC233aNg.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*jQMQ9BEKPycs2wFC233aNg.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*jQMQ9BEKPycs2wFC233aNg.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="d154" id="d154" class="graf graf--p graf-after--figure">13. <code class="markup--code markup--p-code">cb1</code> is executed and adds <code class="markup--code markup--p-code">console.log(&#39;Inside cb1&#39;)</code> to the Call Stack.</p>
                                        <figure name="708d" id="708d" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*hpyVeL1zsaeHaqS7mU4Qfw.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*hpyVeL1zsaeHaqS7mU4Qfw.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*hpyVeL1zsaeHaqS7mU4Qfw.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*hpyVeL1zsaeHaqS7mU4Qfw.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*hpyVeL1zsaeHaqS7mU4Qfw.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="7e35" id="7e35" class="graf graf--p graf-after--figure">14. <code class="markup--code markup--p-code">console.log(&#39;cb1&#39;)</code> is executed.</p>
                                        <figure name="d331" id="d331" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*lvOtCg75ObmUTOxIS6anEQ.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*lvOtCg75ObmUTOxIS6anEQ.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*lvOtCg75ObmUTOxIS6anEQ.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*lvOtCg75ObmUTOxIS6anEQ.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*lvOtCg75ObmUTOxIS6anEQ.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="2fd9" id="2fd9" class="graf graf--p graf-after--figure">15. <code class="markup--code markup--p-code">console.log(&#39;cb1&#39;)</code> is removed from the Call Stack.</p>
                                        <figure name="0ee6" id="0ee6" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*Jyyot22aRkKMF3LN1bgE-w.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*Jyyot22aRkKMF3LN1bgE-w.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*Jyyot22aRkKMF3LN1bgE-w.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*Jyyot22aRkKMF3LN1bgE-w.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*Jyyot22aRkKMF3LN1bgE-w.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="259d" id="259d" class="graf graf--p graf-after--figure">16. <code class="markup--code markup--p-code">cb1</code> is removed from the Call Stack.</p>
                                        <figure name="1bb2" id="1bb2" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*t2Btfb_tBbBxTvyVgKX0Qg.png" data-width="1024" data-height="768" data-action="zoom" data-action-value="1*t2Btfb_tBbBxTvyVgKX0Qg.png"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*t2Btfb_tBbBxTvyVgKX0Qg.png?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*t2Btfb_tBbBxTvyVgKX0Qg.png">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*t2Btfb_tBbBxTvyVgKX0Qg.png"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="ff5a" id="ff5a" class="graf graf--p graf-after--figure">A quick recap:</p>
                                        <figure name="911d" id="911d" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 525px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 75%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="1*TozSrkk92l8ho6d8JxqF_w.gif" data-width="808" data-height="606" data-is-featured="true" data-action="zoom" data-action-value="1*TozSrkk92l8ho6d8JxqF_w.gif"><img src="https://cdn-images-1.medium.com/freeze/max/30/1*TozSrkk92l8ho6d8JxqF_w.gif?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/1*TozSrkk92l8ho6d8JxqF_w.gif">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/1*TozSrkk92l8ho6d8JxqF_w.gif"></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="aec2" id="aec2" class="graf graf--p graf-after--figure">It’s interesting to note that ES6 specifies how the event loop should work, meaning that technically it’s within the scope of the JS engine’s responsibilities, which is no longer playing just a hosting environment role. One main reason for this change is the introduction of Promises in ES6 because the latter require access to a direct, fine-grained control over scheduling operations on the event loop queue (we’ll discuss them in a greater detail later).</p>
                                        <h4 name="ca8b" id="ca8b" class="graf graf--h4 graf-after--p">How setTimeout(…) works</h4>
                                        <p name="7c23" id="7c23" class="graf graf--p graf-after--h4">It’s important to note that <code class="markup--code markup--p-code">setTimeout(…)</code> doesn’t automatically put your callback on the event loop queue. It sets up a timer. When the timer expires, the environment places your callback into the event loop, so that some future tick will pick it up and execute it.Take a look at this code:</p>
                                        <figure name="2303" id="2303" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/a9a7bc97f73f4e95803f796a53cd287d?postId=2f077c4438b5" data-media-id="a9a7bc97f73f4e95803f796a53cd287d" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/a9a7bc97f73f4e95803f796a53cd287d?postId=2f077c4438b5" data-media-id="a9a7bc97f73f4e95803f796a53cd287d" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="4a63" id="4a63" class="graf graf--p graf-after--figure">That doesn’t mean that <code class="markup--code markup--p-code">myCallback</code> will be executed in 1,000 ms but rather that, in 1,000 ms, <code class="markup--code markup--p-code">myCallback</code> will be added to the queue. The queue, however, might have other events that have been added earlier — your callback will have to wait.</p>
                                        <p name="aa5f" id="aa5f" class="graf graf--p graf-after--p">There are quite a few articles and tutorials on getting started with async code in JavaScript that suggest doing a setTimeout(callback, 0). Well, now you know what the Event Loop does and how setTimeout works: calling setTimeout with 0 as a second argument just defers the callback until the Call Stack is clear.</p>
                                        <p name="61e6" id="61e6" class="graf graf--p graf-after--p">Take a look at the following code:</p>
                                        <figure name="435e" id="435e" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/87e06fcad92ac7b8cf42928f17e47107?postId=2f077c4438b5" data-media-id="87e06fcad92ac7b8cf42928f17e47107" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/87e06fcad92ac7b8cf42928f17e47107?postId=2f077c4438b5" data-media-id="87e06fcad92ac7b8cf42928f17e47107" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="3454" id="3454" class="graf graf--p graf-after--figure">Although the wait time is set to 0 ms, the result in the browser console will be the following:</p><pre name="d68c" id="d68c" class="graf graf--pre graf-after--p">Hi<br>Bye<br>callback</pre>
                                        <h4 name="8cd8" id="8cd8" class="graf graf--h4 graf-after--pre">What are Jobs in ES6 ?</h4>
                                        <p name="3293" id="3293" class="graf graf--p graf-after--h4">A new concept called the “Job Queue” was introduced in ES6. It’s a layer on top of the Event Loop queue. You are most likely to bump into it when dealing with the asynchronous behavior of Promises (we’ll talk about them too).</p>
                                        <p name="a3af" id="a3af" class="graf graf--p graf-after--p">We’ll just touch on the concept now so that when we discuss async behavior with Promises, later on, you understand how those actions are being scheduled and processed.</p>
                                        <p name="1773" id="1773" class="graf graf--p graf-after--p">Imagine it like this: the Job Queue is a queue that’s attached to the end of every tick in the Event Loop queue. Certain async actions that may occur during a tick of the event loop will not cause a whole new event to be added to the event loop queue, but will instead add an item (aka Job) to the end of the current tick’s Job queue.</p>
                                        <p name="d32d" id="d32d" class="graf graf--p graf-after--p">This means that you can add another functionality to be executed later, and you can rest assured that it will be executed right after, before anything else.</p>
                                        <p name="235f" id="235f" class="graf graf--p graf-after--p">A Job can also cause more Jobs to be added to the end of the same queue. In theory, it’s possible for a Job “loop” (a Job that keeps adding other Jobs, etc.) to spin indefinitely, thus starving the program of the necessary resources needed to move on to the next event loop tick. Conceptually, this would be similar to just expressing a long-running or infinite loop (like <code class="markup--code markup--p-code">while (true)</code> ..) in your code.</p>
                                        <p name="3e53" id="3e53" class="graf graf--p graf-after--p">Jobs are kind of like the <code class="markup--code markup--p-code">setTimeout(callback, 0)</code> “hack” but implemented in such a way that they introduce a much more well-defined and guaranteed ordering: later, but as soon as possible.</p>
                                        <h4 name="5382" id="5382" class="graf graf--h4 graf-after--p"><strong class="markup--strong markup--h4-strong">Callbacks</strong></h4>
                                        <p name="76e2" id="76e2" class="graf graf--p graf-after--h4">As you already know, callbacks are by far the most common way to express and manage asynchrony in JavaScript programs. Indeed, the callback is the most fundamental async pattern in the JavaScript language. Countless JS programs, even very sophisticated and complex ones, have been written on top of no other async foundation than the callback.</p>
                                        <p name="3518" id="3518" class="graf graf--p graf-after--p">Except that callbacks don’t come with no shortcomings. Many developers are trying to find better async patterns. It’s impossible, however, to effectively use any abstraction if you don’t understand what’s actually under the hood.</p>
                                        <p name="f5aa" id="f5aa" class="graf graf--p graf-after--p">In the following chapter, we’ll explore couple of these abstractions in depth to show why more sophisticated async patterns (that will be discussed in subsequent posts) are necessary and even recommended.</p>
                                        <h4 name="1ec9" id="1ec9" class="graf graf--h4 graf-after--p">Nested Callbacks</h4>
                                        <p name="8021" id="8021" class="graf graf--p graf-after--h4">Look at the following code:</p>
                                        <figure name="f02f" id="f02f" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/fbaba2812caa29f501e89f0f96e6492c?postId=2f077c4438b5" data-media-id="fbaba2812caa29f501e89f0f96e6492c" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/fbaba2812caa29f501e89f0f96e6492c?postId=2f077c4438b5" data-media-id="fbaba2812caa29f501e89f0f96e6492c" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="9f58" id="9f58" class="graf graf--p graf-after--figure">We’ve got a chain of three functions nested together, each one representing a step in an asynchronous series.</p>
                                        <p name="0f81" id="0f81" class="graf graf--p graf-after--p">This kind of code is often called a “callback hell”. But the “callback hell” actually has almost nothing to do with the nesting/indentation. It’s a much deeper problem than that.</p>
                                        <p name="d052" id="d052" class="graf graf--p graf-after--p">First, we’re waiting for the “click” event, then we’re waiting for the timer to fire, then we’re waiting for the Ajax response to come back, at which point it might get all repeated again.</p>
                                        <p name="7fb0" id="7fb0" class="graf graf--p graf-after--p">At first glance, this code may seem to map its asynchrony naturally to sequential steps like:</p>
                                        <figure name="f558" id="f558" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/13ee09260ddba1ae425da38217209977?postId=2f077c4438b5" data-media-id="13ee09260ddba1ae425da38217209977" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/13ee09260ddba1ae425da38217209977?postId=2f077c4438b5" data-media-id="13ee09260ddba1ae425da38217209977" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="4b1d" id="4b1d" class="graf graf--p graf-after--figure">Then we have:</p>
                                        <figure name="251c" id="251c" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/f4dd68bc1957079f856fc573644a0ce3?postId=2f077c4438b5" data-media-id="f4dd68bc1957079f856fc573644a0ce3" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/f4dd68bc1957079f856fc573644a0ce3?postId=2f077c4438b5" data-media-id="f4dd68bc1957079f856fc573644a0ce3" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="1189" id="1189" class="graf graf--p graf-after--figure">Then later we have:</p>
                                        <figure name="b79c" id="b79c" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/52286bd06a963a7205cffeb69b5bc4be?postId=2f077c4438b5" data-media-id="52286bd06a963a7205cffeb69b5bc4be" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/52286bd06a963a7205cffeb69b5bc4be?postId=2f077c4438b5" data-media-id="52286bd06a963a7205cffeb69b5bc4be" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="3c3b" id="3c3b" class="graf graf--p graf-after--figure">And finally:</p>
                                        <figure name="23bf" id="23bf" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/da5beb7cecdf1f54195fca1e8dc601d8?postId=2f077c4438b5" data-media-id="da5beb7cecdf1f54195fca1e8dc601d8" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/da5beb7cecdf1f54195fca1e8dc601d8?postId=2f077c4438b5" data-media-id="da5beb7cecdf1f54195fca1e8dc601d8" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="25ef" id="25ef" class="graf graf--p graf-after--figure">So, such a sequential way of expressing your async code seems a lot more natural, doesn’t it? There must be such a way, right?</p>
                                        <h4 name="066f" id="066f" class="graf graf--h4 graf-after--p">Promises</h4>
                                        <p name="aad8" id="aad8" class="graf graf--p graf-after--h4">Take a look at the following code:</p>
                                        <figure name="196e" id="196e" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/13c98482a65d48eb9a8bb0fae3048cc0?postId=2f077c4438b5" data-media-id="13c98482a65d48eb9a8bb0fae3048cc0" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/13c98482a65d48eb9a8bb0fae3048cc0?postId=2f077c4438b5" data-media-id="13c98482a65d48eb9a8bb0fae3048cc0" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="77cd" id="77cd" class="graf graf--p graf-after--figure">It’s all very straightforward: it sums the values of <code class="markup--code markup--p-code">x</code> and <code class="markup--code markup--p-code">y</code> and prints it to the console. What if, however, the value of <code class="markup--code markup--p-code">x</code> or <code class="markup--code markup--p-code">y </code>was missing and was still to be determined? Say, we need to retrieve the values of both <code class="markup--code markup--p-code">x</code> and <code class="markup--code markup--p-code">y</code> from the server, before they can be used in the expression. Let’s imagine that we have a function <code class="markup--code markup--p-code">loadX</code> and <code class="markup--code markup--p-code">loadY</code> that respectively load the values of <code class="markup--code markup--p-code">x</code> and <code class="markup--code markup--p-code">y</code> from the server. Then, imagine that we have a function <code class="markup--code markup--p-code">sum</code> that sums the values of <code class="markup--code markup--p-code">x</code> and <code class="markup--code markup--p-code">y</code> once both of them are loaded.</p>
                                        <p name="da15" id="da15" class="graf graf--p graf-after--p">It could look like this (quite ugly, isn’t it):</p>
                                        <figure name="8768" id="8768" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/d8327e91f83e3e35469cdd3729b4699d?postId=2f077c4438b5" data-media-id="d8327e91f83e3e35469cdd3729b4699d" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/d8327e91f83e3e35469cdd3729b4699d?postId=2f077c4438b5" data-media-id="d8327e91f83e3e35469cdd3729b4699d" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="33e5" id="33e5" class="graf graf--p graf-after--figure">There is something very important here — in that snippet, we treated <code class="markup--code markup--p-code">x</code> and <code class="markup--code markup--p-code">y</code> as <strong class="markup--strong markup--p-strong">future</strong> values, and we expressed an operation <code class="markup--code markup--p-code">sum(…)</code> that (from the outside) did not care whether <code class="markup--code markup--p-code">x</code> or <code class="markup--code markup--p-code">y</code> or both were or weren’t available right away.</p>
                                        <p name="e237" id="e237" class="graf graf--p graf-after--p">Of course, this rough callbacks-based approach leaves much to be desired. It’s just a first tiny step towards understanding the benefits of reasoning about <em class="markup--em markup--p-em">future values</em> without worrying about the time aspect of when they will be available.</p>
                                        <h4 name="8f53" id="8f53" class="graf graf--h4 graf-after--p">Promise Value</h4>
                                        <p name="8878" id="8878" class="graf graf--p graf-after--h4">Let’s just briefly glimpse at how we can express the<code class="markup--code markup--p-code"> x + y</code> example with Promises:</p>
                                        <figure name="d6b9" id="d6b9" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/9d68007e82fd0b98b5d9ecac952757e3?postId=2f077c4438b5" data-media-id="9d68007e82fd0b98b5d9ecac952757e3" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/9d68007e82fd0b98b5d9ecac952757e3?postId=2f077c4438b5" data-media-id="9d68007e82fd0b98b5d9ecac952757e3" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="410b" id="410b" class="graf graf--p graf-after--figure">There are two layers of Promises in this snippet.</p>
                                        <p name="29b5" id="29b5" class="graf graf--p graf-after--p"><code class="markup--code markup--p-code">fetchX()</code> and <code class="markup--code markup--p-code">fetchY()</code> are called directly, and the values they return (promises!) are passed to <code class="markup--code markup--p-code">sum(...)</code>. The underlying values these promises represent may be ready <em class="markup--em markup--p-em">now</em> or <em class="markup--em markup--p-em">later</em>, but each promise normalizes its behavior to be the same regardless. We reason about <code class="markup--code markup--p-code">x</code> and <code class="markup--code markup--p-code">y</code> values in a time-independent way. They are <em class="markup--em markup--p-em">future values</em>, period.</p>
                                        <p name="78f0" id="78f0" class="graf graf--p graf-after--p">The second layer is the promise that <code class="markup--code markup--p-code">sum(...)</code> creates
                                            <br>(via <code class="markup--code markup--p-code">Promise.all([ ... ])</code>) and returns, which we wait on by calling <code class="markup--code markup--p-code">then(...)</code>. When the <code class="markup--code markup--p-code">sum(...)</code>operation completes, our sum <em class="markup--em markup--p-em">future value</em> is ready and we can print it out. We hide the logic for waiting on the <code class="markup--code markup--p-code">x</code> and <code class="markup--code markup--p-code">y</code> <em class="markup--em markup--p-em">future values</em> inside of <code class="markup--code markup--p-code">sum(...)</code> .</p>
                                        <p name="98a8" id="98a8" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Note</strong>: Inside <code class="markup--code markup--p-code">sum(…)</code>, the <code class="markup--code markup--p-code">Promise.all([ … ])</code> call creates a promise (which is waiting on <code class="markup--code markup--p-code">promiseX</code> and <code class="markup--code markup--p-code">promiseY</code> to resolve). The chained call to <code class="markup--code markup--p-code">.then(...) </code>creates another promise, which the return
                                            <br><code class="markup--code markup--p-code">values[0] + values[1]</code> line immediately resolves (with the result of the addition). Thus, the <code class="markup--code markup--p-code">then(...)</code> call we chain off the end of the <code class="markup--code markup--p-code">sum(...)</code> call — at the end of the snippet — is actually operating on that second promise returned, rather than the first one created by <code class="markup--code markup--p-code">Promise.all([ ... ])</code>. Also, although we are not chaining off the end of that second <code class="markup--code markup--p-code">then(...)</code>, it too has created another promise, had we chosen to observe/use it. This Promise chaining stuff will be explained in much greater detail later in this chapter.</p>
                                        <p name="49f5" id="49f5" class="graf graf--p graf-after--p">With Promises, the <code class="markup--code markup--p-code">then(...)</code> call can actually take two functions, the first for fulfillment (as shown earlier), and the second for rejection:</p>
                                        <figure name="7c4a" id="7c4a" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/e0b499cba64b507409446218bc8f5d2e?postId=2f077c4438b5" data-media-id="e0b499cba64b507409446218bc8f5d2e" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/e0b499cba64b507409446218bc8f5d2e?postId=2f077c4438b5" data-media-id="e0b499cba64b507409446218bc8f5d2e" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="6423" id="6423" class="graf graf--p graf-after--figure">If something went wrong when getting <code class="markup--code markup--p-code">x</code> or <code class="markup--code markup--p-code">y</code>, or something somehow failed during the addition, the promise that <code class="markup--code markup--p-code">sum(...) </code>returns would be rejected, and the second callback error handler passed to <code class="markup--code markup--p-code">then(...)</code> would receive the rejection value from the promise.</p>
                                        <p name="6e87" id="6e87" class="graf graf--p graf-after--p">Because Promises encapsulate the time-dependent state — waiting on the fulfillment or rejection of the underlying value — from the outside, the Promise itself is time-independent, and thus Promises can be composed (combined) in predictable ways regardless of the timing or outcome underneath.</p>
                                        <p name="2e20" id="2e20" class="graf graf--p graf-after--p">Moreover, once a Promise is resolved, it stays that way forever — it becomes an <em class="markup--em markup--p-em">immutable value</em> at that point — and can then be <em class="markup--em markup--p-em">observed</em> as many times as necessary.</p>
                                        <p name="706d" id="706d" class="graf graf--p graf-after--p">It’s really useful that you can actually chain promises:</p>
                                        <figure name="44e9" id="44e9" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/99695d666aaa6da5809d2caf754ef27c?postId=2f077c4438b5" data-media-id="99695d666aaa6da5809d2caf754ef27c" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/99695d666aaa6da5809d2caf754ef27c?postId=2f077c4438b5" data-media-id="99695d666aaa6da5809d2caf754ef27c" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="8f23" id="8f23" class="graf graf--p graf-after--figure">Calling <code class="markup--code markup--p-code">delay(2000)</code> creates a promise that will fulfill in 2000ms, and then we return that from the first <code class="markup--code markup--p-code">then(...)</code> fulfillment callback, which causes the second <code class="markup--code markup--p-code">then(...)</code>&#39;s promise to wait on that 2000ms promise.</p>
                                        <p name="f92e" id="f92e" class="graf graf--p graf-after--p"><strong class="markup--strong markup--p-strong">Note</strong>: Because a Promise is externally immutable once resolved, it’s now safe to pass that value around to any party, knowing that it cannot be modified accidentally or maliciously. This is especially true in relation to multiple parties observing the resolution of a Promise. It’s not possible for one party to affect another party’s ability to observe Promise resolution. Immutability may sound like an academic topic, but it’s actually one of the most fundamental and important aspects of Promise design, and shouldn’t be casually passed over.</p>
                                        <h4 name="918a" id="918a" class="graf graf--h4 graf-after--p"><strong class="markup--strong markup--h4-strong">To Promise or not to Promise?</strong></h4>
                                        <p name="4f1d" id="4f1d" class="graf graf--p graf-after--h4">An important detail about Promises is knowing for sure if some value is an actual Promise or not. In other words, is it a value that will behave like a Promise?</p>
                                        <p name="7397" id="7397" class="graf graf--p graf-after--p">We know that Promises are constructed by the <code class="markup--code markup--p-code">new Promise(…)</code> syntax, and you might think that <code class="markup--code markup--p-code">p instanceof Promise</code> would be a sufficient check. Well, not quite.</p>
                                        <p name="27a3" id="27a3" class="graf graf--p graf-after--p">Mainly because you can receive a Promise value from another browser window (e.g. iframe), which would have its own Promise, different from the one in the current window or frame, and that check would fail to identify the Promise instance.</p>
                                        <p name="9bbd" id="9bbd" class="graf graf--p graf-after--p">Moreover, a library or framework may choose to vend its own Promises and not use the native ES6 Promise implementation to do so. In fact, you may very well be using Promises with libraries in older browsers that have no Promise at all.</p>
                                        <h4 name="d75e" id="d75e" class="graf graf--h4 graf-after--p">Swallowing exceptions</h4>
                                        <p name="4ca1" id="4ca1" class="graf graf--p graf-after--h4">If at any point in the creation of a Promise, or in the observation of its resolution, a JavaScript exception error occurs, such as a <code class="markup--code markup--p-code">TypeError</code> or <code class="markup--code markup--p-code">ReferenceError</code>, that exception will be caught, and it will force the Promise in question to become rejected.</p>
                                        <p name="79e4" id="79e4" class="graf graf--p graf-after--p">For example:</p>
                                        <figure name="2644" id="2644" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/c781dde334ea9d9c434a089de59e598d?postId=2f077c4438b5" data-media-id="c781dde334ea9d9c434a089de59e598d" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/c781dde334ea9d9c434a089de59e598d?postId=2f077c4438b5" data-media-id="c781dde334ea9d9c434a089de59e598d" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="723b" id="723b" class="graf graf--p graf-after--figure">But what happens if a Promise is fulfilled yet there was a JS exception error during the observation (in a <code class="markup--code markup--p-code">then(…)</code> registered callback)? Even though it won’t be lost, you may find the way they’re handled a bit surprising. Until you dig a little deeper:</p>
                                        <figure name="6ad7" id="6ad7" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/de748eaf81fa28c14c588dc07a18676a?postId=2f077c4438b5" data-media-id="de748eaf81fa28c14c588dc07a18676a" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/de748eaf81fa28c14c588dc07a18676a?postId=2f077c4438b5" data-media-id="de748eaf81fa28c14c588dc07a18676a" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="c1cb" id="c1cb" class="graf graf--p graf-after--figure">It looks like the exception from <code class="markup--code markup--p-code">foo.bar()</code> really did get swallowed. It wasn’t, though. There was something deeper that went wrong, however, which we failed to listen for. The <code class="markup--code markup--p-code">p.then(…)</code> call itself returns another promise, and it’s that<em class="markup--em markup--p-em"> </em>promise that will be rejected with the <code class="markup--code markup--p-code">TypeError</code> exception.</p>
                                        <h4 name="bf3f" id="bf3f" class="graf graf--h4 graf-after--p"><strong class="markup--strong markup--h4-strong">Handling uncaught exceptions</strong></h4>
                                        <p name="ce62" id="ce62" class="graf graf--p graf-after--h4">There are other approaches which many would say are <em class="markup--em markup--p-em">better</em>.</p>
                                        <p name="a8f8" id="a8f8" class="graf graf--p graf-after--p">A common suggestion is that Promises should have a <code class="markup--code markup--p-code">done(…)</code> added to them, which essentially marks the Promise chain as “done.” <code class="markup--code markup--p-code">done(…)</code>doesn’t create and return a Promise, so the callbacks passed to <code class="markup--code markup--p-code">done(..)</code> are obviously not wired up to report problems to a chained Promise that doesn’t exist.</p>
                                        <p name="cac9" id="cac9" class="graf graf--p graf-after--p">It’s treated as you might usually expect in uncaught error conditions: any exception inside a <code class="markup--code markup--p-code">done(..)</code> rejection handler would be thrown as a global uncaught error (in the developer console, basically):</p>
                                        <figure name="91dd" id="91dd" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/63033b76871b741682c5867889f39869?postId=2f077c4438b5" data-media-id="63033b76871b741682c5867889f39869" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/63033b76871b741682c5867889f39869?postId=2f077c4438b5" data-media-id="63033b76871b741682c5867889f39869" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <h4 name="ee15" id="ee15" class="graf graf--h4 graf-after--figure"><strong class="markup--strong markup--h4-strong">What’s happening in ES8? Async/await</strong></h4>
                                        <p name="e408" id="e408" class="graf graf--p graf-after--h4">JavaScript ES8 introduced <code class="markup--code markup--p-code">async/await</code><em class="markup--em markup--p-em"> </em>that makes the job of working with Promises easier. We’ll briefly go through the possibilities <code class="markup--code markup--p-code">async/await</code> offers and how to leverage them to write async code.</p>
                                        <p name="2de6" id="2de6" class="graf graf--p graf-after--p">So, let’s see how async/await works.</p>
                                        <p name="aa2d" id="aa2d" class="graf graf--p graf-after--p">You define an asynchronous function using the <code class="markup--code markup--p-code">async</code> function declaration. Such functions return an <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncFunction" data-href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncFunction" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">AsyncFunction</a> object. The <code class="markup--code markup--p-code">AsyncFunction</code> object represents the asynchronous function which executes the code, contained within that function.</p>
                                        <p name="bc29" id="bc29" class="graf graf--p graf-after--p">When an async function is called, it returns a <code class="markup--code markup--p-code">Promise</code> . When the async function returns a value, that’s not a <code class="markup--code markup--p-code">Promise</code> , a <code class="markup--code markup--p-code">Promise</code> will be automatically created and it will be resolved with the returned value from the function. When the <code class="markup--code markup--p-code">async</code> function throws an exception, the <code class="markup--code markup--p-code">Promise</code> will be rejected with the thrown value.</p>
                                        <p name="68d2" id="68d2" class="graf graf--p graf-after--p">An <code class="markup--code markup--p-code">async</code> function can contain an <code class="markup--code markup--p-code">await</code> expression, that pauses the execution of the function and waits for the passed Promise’s resolution, and then resumes the async function’s execution and returns the resolved value.</p>
                                        <p name="aa75" id="aa75" class="graf graf--p graf-after--p">You can think of a <code class="markup--code markup--p-code">Promise</code> in JavaScript as the equivalent of Java’s <code class="markup--code markup--p-code">Future</code> or <code class="markup--code markup--p-code">C#</code>&#39;s Task.</p>
                                        <blockquote name="2941" id="2941" class="graf graf--blockquote graf-after--p">The purpose of <code class="markup--code markup--blockquote-code">async/await</code> is to simplify the behavior of using promises.</blockquote>
                                        <p name="4c11" id="4c11" class="graf graf--p graf-after--blockquote">Let’s take a look at the following example:</p>
                                        <figure name="6241" id="6241" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/735a8de1b6b465455217b369c2873d70?postId=2f077c4438b5" data-media-id="735a8de1b6b465455217b369c2873d70" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/735a8de1b6b465455217b369c2873d70?postId=2f077c4438b5" data-media-id="735a8de1b6b465455217b369c2873d70" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="57a5" id="57a5" class="graf graf--p graf-after--figure">Similarly, functions that are throwing exceptions are equivalent to functions which return promises that have been rejected:</p>
                                        <figure name="9140" id="9140" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/ea6a8d0d912921330b58f12164a7a88b?postId=2f077c4438b5" data-media-id="ea6a8d0d912921330b58f12164a7a88b" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/ea6a8d0d912921330b58f12164a7a88b?postId=2f077c4438b5" data-media-id="ea6a8d0d912921330b58f12164a7a88b" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="1f8e" id="1f8e" class="graf graf--p graf-after--figure">The <code class="markup--code markup--p-code">await</code> keyword can only be used in <code class="markup--code markup--p-code">async</code> functions and allows you to synchronously wait on a Promise. If we use promises outside of an <code class="markup--code markup--p-code">async</code> function, we’ll still have to use <code class="markup--code markup--p-code">then</code> callbacks:</p>
                                        <figure name="e5e0" id="e5e0" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/6dfd4ec4f8be0da7bb762022ca093cfc?postId=2f077c4438b5" data-media-id="6dfd4ec4f8be0da7bb762022ca093cfc" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/6dfd4ec4f8be0da7bb762022ca093cfc?postId=2f077c4438b5" data-media-id="6dfd4ec4f8be0da7bb762022ca093cfc" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="b9df" id="b9df" class="graf graf--p graf-after--figure">You can also define async functions using an “async function expression”. An async function expression is very similar to and has almost the same syntax as, an async function statement. The main difference between an async function expression and an async function statement is the function name, which can be omitted in async function expressions to create anonymous functions. An async function expression can be used as an IIFE (Immediately Invoked Function Expression) which runs as soon as it is defined.</p>
                                        <p name="1fd0" id="1fd0" class="graf graf--p graf-after--p">It looks like this:</p>
                                        <figure name="1b53" id="1b53" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/7e06cdbc5f92a0f7d5a5fd6996cb9d60?postId=2f077c4438b5" data-media-id="7e06cdbc5f92a0f7d5a5fd6996cb9d60" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/7e06cdbc5f92a0f7d5a5fd6996cb9d60?postId=2f077c4438b5" data-media-id="7e06cdbc5f92a0f7d5a5fd6996cb9d60" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="f40a" id="f40a" class="graf graf--p graf-after--figure">More importantly, async/await is supported in all major browsers:</p>
                                        <figure name="219a" id="219a" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 228px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 32.6%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="0*z-A-JIe5OWFtgyd2." data-width="1536" data-height="500" data-action="zoom" data-action-value="0*z-A-JIe5OWFtgyd2."><img src="https://cdn-images-1.medium.com/freeze/max/30/0*z-A-JIe5OWFtgyd2.?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/0*z-A-JIe5OWFtgyd2.">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/0*z-A-JIe5OWFtgyd2."></noscript>
                                                </div>
                                            </div>
                                            <figcaption class="imageCaption">If this compatibility is not what you are after, there are also several JS transpilers like <a href="https://babeljs.io/docs/plugins/transform-async-to-generator/" data-href="https://babeljs.io/docs/plugins/transform-async-to-generator/" class="markup--anchor markup--figure-anchor" rel="noopener" target="_blank">Babel</a> and <a href="https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-3.html" data-href="https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-3.html" class="markup--anchor markup--figure-anchor" rel="noopener" target="_blank">TypeScript.</a></figcaption>
                                        </figure>
                                        <p name="5aec" id="5aec" class="graf graf--p graf-after--figure">At the end of the day, the important thing is not to blindly choose the “latest” approach to writing async code. It’s essential to understand the internals of async JavaScript, learn why it’s so critical and comprehend in-depth the internals of the method you have chosen. Every approach has pros and cons as with everything else in programming.</p>
                                        <h3 name="2872" id="2872" class="graf graf--h3 graf-after--p">5 Tips on writing highly maintainable, non-brittle async code</h3>
                                        <ol class="postList">
                                            <li name="c2aa" id="c2aa" class="graf graf--li graf-after--h3"><strong class="markup--strong markup--li-strong">Clean code: </strong>Using async/await allows you to write a lot less code. Every time you use async/await you skip a few unnecessary steps: write .then, create an anonymous function to handle the response, name the response from that callback e.g.</li>
                                        </ol>
                                        <figure name="7ec3" id="7ec3" class="graf graf--figure graf--iframe graf-after--li">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/15eb4c10884336d447d8e468a691d40b?postId=2f077c4438b5" data-media-id="15eb4c10884336d447d8e468a691d40b" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/15eb4c10884336d447d8e468a691d40b?postId=2f077c4438b5" data-media-id="15eb4c10884336d447d8e468a691d40b" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="0ae5" id="0ae5" class="graf graf--p graf-after--figure">Versus:</p>
                                        <figure name="f797" id="f797" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/b3f10538b73917d629d10c7a6a397089?postId=2f077c4438b5" data-media-id="b3f10538b73917d629d10c7a6a397089" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/b3f10538b73917d629d10c7a6a397089?postId=2f077c4438b5" data-media-id="b3f10538b73917d629d10c7a6a397089" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="9f30" id="9f30" class="graf graf--p graf-after--figure">2. <strong class="markup--strong markup--p-strong">Error handling: </strong>Async/await makes it possible to handle both sync and async errors with the same code construct — the well-known try/catch statements. Let’s see how it looks with Promises:</p>
                                        <figure name="53c5" id="53c5" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/d0289728b5a711d27229d89a449fd8ae?postId=2f077c4438b5" data-media-id="d0289728b5a711d27229d89a449fd8ae" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/d0289728b5a711d27229d89a449fd8ae?postId=2f077c4438b5" data-media-id="d0289728b5a711d27229d89a449fd8ae" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="7569" id="7569" class="graf graf--p graf-after--figure">Versus:</p>
                                        <figure name="e2fe" id="e2fe" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/e3dde652285c55e0a9094a82c4376e73?postId=2f077c4438b5" data-media-id="e3dde652285c55e0a9094a82c4376e73" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/e3dde652285c55e0a9094a82c4376e73?postId=2f077c4438b5" data-media-id="e3dde652285c55e0a9094a82c4376e73" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="1703" id="1703" class="graf graf--p graf-after--figure">3.<strong class="markup--strong markup--p-strong"> Conditionals: </strong>Writing conditional code with <code class="markup--code markup--p-code">async/await</code> is a lot more straightforward:</p>
                                        <figure name="79ea" id="79ea" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/ae247c8d36bc425f22c7e85bf640d963?postId=2f077c4438b5" data-media-id="ae247c8d36bc425f22c7e85bf640d963" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/ae247c8d36bc425f22c7e85bf640d963?postId=2f077c4438b5" data-media-id="ae247c8d36bc425f22c7e85bf640d963" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="f59b" id="f59b" class="graf graf--p graf-after--figure">Versus:</p>
                                        <figure name="4251" id="4251" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/e04e70a9ff01b1140ae886b9353ec354?postId=2f077c4438b5" data-media-id="e04e70a9ff01b1140ae886b9353ec354" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/e04e70a9ff01b1140ae886b9353ec354?postId=2f077c4438b5" data-media-id="e04e70a9ff01b1140ae886b9353ec354" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="cdde" id="cdde" class="graf graf--p graf-after--figure">4. <strong class="markup--strong markup--p-strong">Stack Frames: </strong>Unlike with <code class="markup--code markup--p-code">async/await</code>, the error stack returned from a promise chain gives no clue of where the error happened. Look at the following:</p>
                                        <figure name="8229" id="8229" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/0c319b2c2515b45e100d99ab922298f6?postId=2f077c4438b5" data-media-id="0c319b2c2515b45e100d99ab922298f6" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/0c319b2c2515b45e100d99ab922298f6?postId=2f077c4438b5" data-media-id="0c319b2c2515b45e100d99ab922298f6" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="dd18" id="dd18" class="graf graf--p graf-after--figure">Versus:</p>
                                        <figure name="cbdd" id="cbdd" class="graf graf--figure graf--iframe graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 35.699999999999996%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia"><img src="https://i.embed.ly/1/display/resize?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;width=40" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas>
                                                    <div class="iframeContainer">
                                                        <IFRAME width="700" height="250" data-src="/media/d2c88650dac409041493e5a227932e44?postId=2f077c4438b5" data-media-id="d2c88650dac409041493e5a227932e44" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" class="progressiveMedia-iframe js-progressiveMedia-iframe" allowfullscreen frameborder="0"></IFRAME>
                                                    </div>
                                                    <noscript class="js-progressiveMedia-inner">
                                                        <div class="iframeContainer">
                                                            <IFRAME width="700" height="250" src="/media/d2c88650dac409041493e5a227932e44?postId=2f077c4438b5" data-media-id="d2c88650dac409041493e5a227932e44" data-thumbnail="https://i.embed.ly/1/image?url=https%3A%2F%2Favatars3.githubusercontent.com%2Fu%2F1874648%3Fv%3D4%26s%3D400&amp;key=a19fcc184b9711e1b4764040d3dc5c07" allowfullscreen frameborder="0"></IFRAME>
                                                        </div>
                                                    </noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="7be4" id="7be4" class="graf graf--p graf-after--figure">5. <strong class="markup--strong markup--p-strong">Debugging: </strong>If you have used promises, you know that debugging them is a nightmare. For example, if you set a breakpoint inside a .then block and use debug shortcuts like “stop-over”, the debugger will not move to the following .then because it only “steps” through synchronous code.
                                            <br>With <code class="markup--code markup--p-code">async/await</code> you can step through await calls exactly as if they were normal synchronous functions.</p>
                                        <p name="0d35" id="0d35" class="graf graf--p graf-after--p">Writing <strong class="markup--strong markup--p-strong">async JavaScript code is important</strong> not only for the apps themselves but <strong class="markup--strong markup--p-strong">for libraries as well</strong>.</p>
                                        <p name="bb09" id="bb09" class="graf graf--p graf-after--p">For example, the <a href="https://www.sessionstack.com" data-href="https://www.sessionstack.com" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">SessionStack</a> library records everything in your web app/website: all DOM changes, user interactions, JavaScript exceptions, stack traces, failed network requests, and debug messages.</p>
                                        <p name="5b89" id="5b89" class="graf graf--p graf-after--p">And this all has to happen in your production environment without impacting any of the UX. We need to heavily optimize our code and make it asynchronous as much as possible so that we can increase the number of events that are being processed by the Event Loop.</p>
                                        <p name="f0b5" id="f0b5" class="graf graf--p graf-after--p">And not just the library! When you replay a user session in SessionStack, we have to render everything that happened in your user’s browser at the time the problem occurred, and we have to reconstruct the whole state, allowing you to jump back and forth in the session timeline. In order to make this possible, we’re heavily employing the async opportunities that JavaScript provides.</p>
                                        <p name="038b" id="038b" class="graf graf--p graf-after--p">There is a free plan that allows you to <a href="https://www.sessionstack.com/signup/" data-href="https://www.sessionstack.com/signup/" class="markup--anchor markup--p-anchor" rel="noopener" target="_blank">get started for free</a>.</p>
                                        <figure name="4b7f" id="4b7f" class="graf graf--figure graf-after--p">
                                            <div class="aspectRatioPlaceholder is-locked" style="max-width: 700px; max-height: 389px;">
                                                <div class="aspectRatioPlaceholder-fill" style="padding-bottom: 55.50000000000001%;"></div>
                                                <div class="progressiveMedia js-progressiveMedia graf-image" data-image-id="0*xSEaWHGqqlcF8g5H." data-width="800" data-height="444" data-action="zoom" data-action-value="0*xSEaWHGqqlcF8g5H."><img src="https://cdn-images-1.medium.com/freeze/max/30/0*xSEaWHGqqlcF8g5H.?q=20" crossorigin="anonymous" class="progressiveMedia-thumbnail js-progressiveMedia-thumbnail">
                                                    <canvas class="progressiveMedia-canvas js-progressiveMedia-canvas"></canvas><img class="progressiveMedia-image js-progressiveMedia-image" data-src="https://cdn-images-1.medium.com/max/800/0*xSEaWHGqqlcF8g5H.">
                                                    <noscript class="js-progressiveMedia-inner"><img class="progressiveMedia-noscript js-progressiveMedia-inner" src="https://cdn-images-1.medium.com/max/800/0*xSEaWHGqqlcF8g5H."></noscript>
                                                </div>
                                            </div>
                                        </figure>
                                        <p name="b00b" id="b00b" class="graf graf--p graf-after--figure">Resources:</p>
                                        <ul class="postList">
                                            <li name="9618" id="9618" class="graf graf--li graf-after--p"><a href="https://github.com/getify/You-Dont-Know-JS/blob/master/async%20%26%20performance/ch2.md" data-href="https://github.com/getify/You-Dont-Know-JS/blob/master/async%20%26%20performance/ch2.md" class="markup--anchor markup--li-anchor" rel="noopener" target="_blank">https://github.com/getify/You-Dont-Know-JS/blob/master/async%20%26%20performance/ch2.md</a></li>
                                            <li name="2d1c" id="2d1c" class="graf graf--li graf-after--li"><a href="https://github.com/getify/You-Dont-Know-JS/blob/master/async%20%26%20performance/ch3.md" data-href="https://github.com/getify/You-Dont-Know-JS/blob/master/async%20%26%20performance/ch3.md" class="markup--anchor markup--li-anchor" rel="noopener" target="_blank">https://github.com/getify/You-Dont-Know-JS/blob/master/async%20%26%20performance/ch3.md</a></li>
                                            <li name="507b" id="507b" class="graf graf--li graf-after--li graf--trailing"><a href="http://nikgrozev.com/2017/10/01/async-await/" data-href="http://nikgrozev.com/2017/10/01/async-await/" class="markup--anchor markup--li-anchor" rel="noopener" target="_blank">http://nikgrozev.com/2017/10/01/async-await/</a></li>
                                        </ul>
                                    </div>
                                </div>
                            </section>
                        </div>
