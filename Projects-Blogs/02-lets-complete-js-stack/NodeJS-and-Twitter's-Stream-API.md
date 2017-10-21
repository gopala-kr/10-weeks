<div class="gb-markdown BookAbout" data-reactid="115"><h1>NodeJS and Twitter&apos;s Stream API</h1>
<p>By far, Twitter has one of the most developer friendly APIs on the internet. Whether you are learning about APIs, creating an app for a startup, learning about OAuth or just hacking around, Twitter&#x2019;s API will be very easy to use. </p>
<p>On top of the standard REST APIs that would be expected out of any API, Twitter also has a stream API. Twitter&#x2019;s stream API is commonly referred to as a &#x201C;fire hose&#x201D; and should be visualized as such. With the proper credentials Twitter gives developers access to live feeds for any hashtag, user ID or @ mention. This means as a user tweets or a hashtag trends, Twitter will send data about those tweets directly to your app as it happens.</p>
<h2>Our App</h2>
<p>For our app we are going to hook into the public statuses of a handful of major news organizations using their Twitter IDs. This includes tweets created by the user, tweets which are retweeted by the user, replies to any tweet created by the user and retweets of any tweet created by the user. This means a lot of data, very quickly. Again, imagine a fire hose.</p>
<p>This small app, created with NodeJS, will be able to handle all the data that Twitter will throw at it. This app can be later incorporated into a larger app. It will start off by setting our environmental variables while the app starts. Then, it will create a connection to the Twitter stream API. Finally, It will field all of the tweets that are sent in its direction. </p>
<p>Later, there will be some examples about what can be done with this app, as well as how to handle the synchronous and asynchronous struggles of each tweet.</p>
<p>To start the project create a new directory and make a new file called <code>app.js</code>.
<code>mkdir TwitterStreamAPI &amp;&amp; cd TwitterStreamAPI &amp;&amp; touch app.js</code></p>
<h2>Our NPMs</h2>
<p>Assuming Node is already installed, run the command <code>npm init</code> in the new project directory to create a package.json file. Give the app a name and fill out the rest of the necessary fields.
<code>npm init</code></p>
<p>There are two primary NPMs, <a href="https://www.npmjs.com/package/dotenv" target="_blank">Dotenv</a> and <a href="https://www.npmjs.com/package/twitter" target="_blank">Twitter</a>, that will be used in this app. Then another one, <a href="https://www.npmjs.com/package/chalk" target="_blank">Chalk</a>, that will be used for visualizing data in the console. </p>
<p>They can be install and saved with the following command.
<code>npm install --save dotenv twitter chalk</code></p>
<p>Dotenv is used for managing environmental variables. The credentials that Twitter provides will be referenced as environmental variables to follow the best practice of never hard coding any credentials. The <code>.env</code> file that these credentials will be referenced from will be mentioned in our <code>.gitignore</code> file so that they never end up on Github.</p>
<p>Our credentials will be passed to the other primary NPM, Twitter. The Twitter NPM uses the very popular NPM Request to establish, maintain and reconnect if necessary to Twitter&#x2019;s stream API.  </p>
<p>There is also one dev dependency that is being used called Nodemon. Nodemon can be used in any NodeJS project. Rather than starting the app with <code>node app.js</code> start the app with <code>nodemon app.js.</code> Nodemon will watch the projects files and restart the app when a file is saved. This NPM is strictly for convenience. It gets rid of the annoying task of having to start and stop an app every time there is a change.</p>
<p>Nodemon can be installed and saved as a dev dependency with the following command.
<code>npm install --save-dev nodemon</code></p>
<p>Nodemon should also be install globally, so that it can be run as a terminal command.
<code>npm install -g nodemon</code></p>
<p>After all the NPMs are done installing, the <code>package.json</code> file should look similar to this:</p>
<pre><code>{
  &quot;name&quot;: &quot;twitterstreamapi&quot;,
  &quot;version&quot;: &quot;1.0.0&quot;,
  &quot;description&quot;: &quot;An example project for working with NodeJS and Twitter&apos;s stream API&quot;,
  &quot;main&quot;: &quot;app.js&quot;,
  &quot;scripts&quot;: {
    &quot;test&quot;: &quot;node app.js&quot;
  },
  &quot;repository&quot;: {
    &quot;type&quot;: &quot;git&quot;,
    &quot;url&quot;: &quot;git+https://github.com/maxrbaldwin/Twitter-Stream-API.git&quot;
  },
  &quot;keywords&quot;: [
    &quot;Node&quot;,
    &quot;Twitter&quot;,
    &quot;API&quot;
  ],
  &quot;author&quot;: &quot;Max Baldwin&quot;,
  &quot;license&quot;: &quot;ISC&quot;,
  &quot;bugs&quot;: {
    &quot;url&quot;: &quot;https://github.com/maxrbaldwin/Twitter-Stream-API/issues&quot;
  },
  &quot;homepage&quot;: &quot;https://github.com/maxrbaldwin/Twitter-Stream-API#readme&quot;,
  &quot;dependencies&quot;: {
    &quot;chalk&quot;: &quot;^1.1.3&quot;,
    &quot;dotenv&quot;: &quot;^2.0.0&quot;,
    &quot;twitter&quot;: &quot;^1.2.5&quot;
  },
  &quot;devDependencies&quot;: {
    &quot;nodemon&quot;: &quot;^1.9.2&quot;
  }
}
</code></pre><h2>Getting Your Twitter Credentials</h2>
<p>To get credentials for this Twitter app, navigate to <a href="https://apps.twitter.com/" target="_blank">Twitter&#x2019;s developer apps page</a>. On this page there is a button near the top right corner that says, <code>Create New app</code>. 
<img src="https://s3.amazonaws.com/f.cl.ly/items/2X1q0b0S1X1T1T3V0G0p/Screen%20Shot%202016-05-04%20at%204.37.23%20PM.png?v=4b00bfb1" />
On the create new app page, fill out the necessary information and agree to the terms and conditions. The field for callback URL is unnecessary for this app because there is no Oauth. Just fill that field in with <code>http://localhost.com</code>. When Twitter is done registering this new app, navigate to the <code>Keys and Access Tokens</code> tab after clicking on the app name. On this page there are four important details. The consumer key, consumer secret, access token and access token secret will be environmental variables in our app.
<img src="https://lh3.googleusercontent.com/q1rfBBgWtLDC4-tL9jkZ7QWcn3TvUcBFci7_PBLYNJC1v61LlD0YeorxTv8ItNJK89wvwPm1Q59fm1Llllcw35vnhNK5qeJ2oZTWA9HgfdvnOnBSBIHqoyGWR2FzYRyedok9FDAOsR36-TgD3utWssj2qGrewIXZOhcdihR8qHQCNGDZaCk6x0OnelPoos15eyzUchJq6sH-2BzF0dbb5ZOvoRyGy2RcF4jpW9l1wKyl0il5WB-zwSCd-gVzGAiUG7SLkgG4WxqLyo4AMwef9cCPLp85jDJ0r1ZLxb51EM7zRVr1KgB67Sn12hvEH6YfNJO0Krc7J2mtwx7KhvMn14PFLvmv6_-EYSaqKJu89WfwUIxgpv60LNK8s_DFhrrxsKaybYBskHUaPV-SyaJFAOP_VsOSShkhLyaWegDkp2J3u2gpyDBEjc2hVb1_RYaIr64dKwWW1A26t9dfaaQ2cpIzCJP8HjUss6LTqbZ-qK1h2GBJDxJvB5OddnZYDpgNGjDy-HaYbPQQBza_rRyT7cJqDcJWMA9axyY9UM1bzyDs9QELueiWtouWrXB_Gz08VjolTpISt-4H-V3pzn_H1-bnDD7mToY=w1906-h1076-no" /></p>
<h2>Environmental Variables</h2>
<p>Environmental variables are a set of values that are specific to the environment that they are running in. There are many values on a computer or server that can be set as an enviromental variables. An example would be the port number that an app is running on. </p>
<p>When building an app with the NPM Express, one of the last things that is done after configuring the app is running the listen function. The listen function requires a port number be passed to it. In a local development environment the port number might be 3000, 5000, 9999 or any other four digit number. Although, when this app is deployed to a production server the app might be run on port 80 or another port dictated by the hosting service. </p>
<p>Heroku, a popular hosting service, will always dictate a port number and pass it as an environmental variable to an app. Therefore, in our development environment an environmental variable should be used as well to mimic the expected behavior in production.</p>
<p>For this Twitter app, as stated before the consumer key, consumer secret, access token and access token secret will be environmental variables. If this app was being worked on by multiple developers the consumer key and consumer secret will stay the same, but the access token and access token secret could be different for each developer working on the project.</p>
<p>In NodeJS there are a handful of ways to store and instantiate environmental variables in an app. In this case a more traditional path will be followed. All environmental variables will be stored in a <code>.env</code> file and injected into the environment when the app starts using the Dotenv NPM. In the top most directory of the app, where <code>package.json</code> and the node modules folder live, create an <code>.env</code> file.
<code>touch .env</code></p>
<p>In the newly created <code>.env</code> file add the enviromental variables as shown below. Double or single quotes are not needed around the values.</p>
<pre><code>consumer_key=Insert consumer key
consumer_secret=Insert consumer secret
access_token_key=Insert access token
access_token_secret=Insert access token secret
</code></pre><h2>Just Ignore It Git</h2>
<p>Mentioned before was the idea of a <code>.gitignore</code> file. This file is exactly what it sounds like. When pushing to GitHub, Git will ignore the files mentioned in this file. The reason this is done is because anyone can see the files for this project on Github. That means any credentials, passwords or tokens can be copied from this repo. Just as it is a bad idea it give your house keys to strangers, it is equally as dangerous to push any credentials to GitHub. </p>
<p>In the top most directory of this project, create a <code>.gitignore</code> file.
<code>touch .gitignore</code></p>
<p>The <code>.gitignore</code> file for this project will look something like this.</p>
<pre><code>.env
*.env
./.env
*/.env
node_modules
./node_modules
</code></pre><p>The <code>node_modules</code> directory is added as well because every developer that pulls on the project will have the <code>package.json</code> file. That is enough for them to install the node modules on their computer. This will also make the project less files to push to and pull from.</p>
<h2>Stream Parameters</h2>
<p>The stream parameters that we will pass to Twitter when we connect to the stream API will tell Twitter what information we want to receive from its stream. There are a lot of cool data that Twitter will return. Twitter will return tweets based on keywords, hashtags, location or language. 
This app will ask for Tweets based on specific Twitter IDs. Therefore, per Twitter&#x2019;s API documentation, a comma separated list of Twitter account IDs will be passed as stream parameters. In this case there are eight Twitter IDs that will be passed. </p>
<p>There is probably a programmtic way to do it, but to get an account&#x2019;s Twitter ID, use <a href="http://gettwitterid.com/" target="_blank">this website</a>.</p>
<p>The Twitter IDs for this project will be stored simply as an array in a JSON object. This JSON object will also have a method on it so that the Twitter IDs can be easily parsed and accessed from anywhere in the app. In the top most directory of the app create a new diretory called <code>streams</code>. This directory will house all filters and the IDs directory. Therefore, after the <code>streams</code> directory is created, inside of the <code>streams</code> directory also create three directories called <code>filters</code>, <code>ids</code> and <code>error</code>. All of these directories will have a file called <code>index.js</code> inside of them.
<code>mkdir streams and cd streams</code>
<code>mkdir error filters ids</code>
<code>touch error/index.js filters/index.js ids/index.js</code></p>
<p>Open the newly created <code>ids/index.js</code> and add the Twitter ids as an array inside of an object like this:</p>
<pre><code><span>var</span> streamIDs = {
    STREAM_IDS: [{
        name: <span>&apos;NYT&apos;</span>,
        id: <span>1255671</span>
    }, {
        name: <span>&apos;Guardian&apos;</span>,
        id: <span>87818409</span>
    }, {
        name: <span>&apos;bbcworld&apos;</span>,
        id: <span>742143</span>
    }, {
        name: <span>&apos;bbcnews&apos;</span>,
        id: <span>612473</span>
    }, {
        name: <span>&apos;washingtonpost&apos;</span>,
        id: <span>2467791</span>
    }, {
        name: <span>&apos;theatlantic&apos;</span>,
        id: <span>35773039</span>
    }, {
        name: <span>&apos;newrepublic&apos;</span>,
        id: <span>82689705</span>
    }, {
        name: <span>&apos;vice&apos;</span>,
        id: <span>23818581</span>
    }]
};

<span>module</span>.exports = streamIDs;
</code></pre>
<p>The stream IDs are placed as an array inside of an object because, as mentioned before, there will be a convenince method on the same object that will get and parse the stream IDs. That method should be added under the closing bracked of the <code>streamIDs</code> variable. It should looks something like this.</p>
<pre><code>streamIDs.getStreamIDs = <span><span>function</span>(<span></span>) </span>{
    <span>var</span> ids = [];

    <span>this</span>.STREAM_IDS.forEach(<span><span>function</span>(<span>el, i</span>) </span>{
        ids.push(el.id);
    });

    <span>return</span> ids.toString();
}
</code></pre>
<p>Now <code>ids/index.js</code> is an exported module with its static data and a convenince method to get that data.</p>
<h2>Creating Filters</h2>
<p>The filters would be a set of functions that will handle the data from the streams as it is passed from Twitter. For now, only two filters will be created and they will be attached to the same stream. On of the filters, <code>filters/index.js</code>, will handle all of the tweets that come through the stream without errors. The other filter, <code>error/index.js</code>, will handle any errors that come through the stream. There are a millions things that would be done to the tweets as they come through this app, but for now the filters will just <code>console.log</code> their text.</p>
<p>The stream filter will be a function inside of <code>filters/index.js</code>. This function will have one parameter called <code>tweet</code>. That <code>tweet</code> parameter will be the tweet object that Twitter will pass to the app whenever there is a tweet from one of the tweet IDs. The stream filter is going to look like this:</p>
<pre><code><span>var</span> chalk = <span>require</span>(<span>&apos;chalk&apos;</span>);

<span>var</span> streamFilter = <span><span>function</span>(<span>tweet</span>) </span>{
  <span>console</span>.log(chalk.green(tweet.user.screen_name, <span>&apos; : &apos;</span> , tweet.text));
};

<span>module</span>.exports = streamFilter;
</code></pre>
<p>In production <code>chalk</code> is not nessecary, but for now it will help visualize the data being sent to the app from Twitter. In this case, the user&apos;s Twitter handle and the tweet text are being logged in green. Right now, if run, this file does not do anything, but it is an important piece of the puzzle.</p>
<p>The error filer, <code>error/index.js</code>, will look very similar to the stream filter.</p>
<pre><code><span>var</span> chalk = <span>require</span>(<span>&apos;chalk&apos;</span>);

<span>var</span> streamError = <span><span>function</span>(<span>err</span>) </span>{
  <span>console</span>.log(chalk.red(err));
};

<span>module</span>.exports = streamError;
</code></pre>
<p>Although they look similar now, their functionality would be completely different if this app were to be built out. Therefore, they will remain two seperate files.</p>
<h2>Putting Together The Pieces</h2>
<p>Now that all of the pieces of the puzzle are assembled, <code>app.js</code> can be completed. Open <code>app.js</code> and reference our NPMs as variables at the top of the file.</p>
<pre><code><span>var</span> Twitter = <span>require</span>(<span>&apos;twitter&apos;</span>);
<span>var</span> env = <span>require</span>(<span>&apos;dotenv&apos;</span>).config();
</code></pre>
<p>The <code>config()</code> function at the end of the <code>env</code> variable will get the enviromental variables out of the <code>.env</code> file in our project and parse them into a JSON object. Now all of the enviromental variables can be accessed with dot notation. Logging <code>env.consumer_key</code> should log your consumer key. </p>
<p>Next, reference the stream filters and stream ID module as variables below our NPM variables.</p>
<pre><code><span>var</span> streamFilter = <span>require</span>(<span>&apos;./streams/filters&apos;</span>);
<span>var</span> streamError = <span>require</span>(<span>&apos;./streams/error&apos;</span>);
<span>var</span> streamIDs = <span>require</span>(<span>&apos;./streams/ids&apos;</span>);
</code></pre>
<p>Now that they stream IDs are referenced in this file, the stream parameters can be added as a variable and set for later use. The convenice method, <code>getStreamIDs()</code> will be used to get the stream IDs as a comma seperated list.</p>
<pre><code><span>var</span> streamParameters = {
  follow: streamIDs.getStreamIDs()
};
</code></pre>
<p>The object key <code>follow</code> will tell Twitter that the stream connection is requesting to follow the Twitter IDs that are provided. Now that the stream parameters have been created, that last piece of the puzzle is to instanitate the Twitter NPM and pass it our credentials.</p>
<pre><code><span>var</span> client = <span>new</span> Twitter({
  consumer_key: env.consumer_key,
  consumer_secret: env.consumer_secret,
  access_token_key: env.access_token_key,
  access_token_secret: env.access_token_secret
});
</code></pre>
<p>This new variable client will return a handful of different methods to interact with Twitter&apos;s APIs. The method that this app is going to use is <code>stream</code>. The method <code>stream</code> is a function at accepts three parameters and returns one. The three parameters are the stream being subscribed to, the parameters of the stream and a callback. The callback, if the connection is successful, will return a stream object with <code>.on</code> methods for the filters. It will look something like this.</p>
<pre><code>client.stream(<span>&apos;statuses/filter&apos;</span>, streamParameters, <span><span>function</span> (<span>stream</span>) </span>{
  stream.on(<span>&apos;data&apos;</span>, streamFilter);
  stream.on(<span>&apos;error&apos;</span>, streamError);
});
</code></pre>
<p>After all the pieces are put together properly <code>app.js</code> should look like this.</p>
<pre><code><span>var</span> Twitter = <span>require</span>(<span>&apos;twitter&apos;</span>);
<span>var</span> env = <span>require</span>(<span>&apos;dotenv&apos;</span>).config();

<span>var</span> streamFilter = <span>require</span>(<span>&apos;./streams/filters&apos;</span>);
<span>var</span> streamError = <span>require</span>(<span>&apos;./streams/error&apos;</span>);
<span>var</span> streamIDs = <span>require</span>(<span>&apos;./streams/ids&apos;</span>);

<span>var</span> streamParameters = {
  follow: streamIDs.getStreamIDs()
};

<span>var</span> client = <span>new</span> Twitter({
  consumer_key: env.consumer_key,
  consumer_secret: env.consumer_secret,
  access_token_key: env.access_token_key,
  access_token_secret: env.access_token_secret
});

client.stream(<span>&apos;statuses/filter&apos;</span>, streamParameters, <span><span>function</span> (<span>stream</span>) </span>{
  stream.on(<span>&apos;data&apos;</span>, streamFilter);
  stream.on(<span>&apos;error&apos;</span>, streamError);
});
</code></pre>
<p>Run the app with the <code>nodemon</code> or <code>node</code> command.
<code>nodemon app.js</code> or <code>node app.js</code></p>
<p>After running this command, if the credentials are correct, there should be some green tweets in the terminal. Sit back and watch all the differet kinds of tweets come in. Recognize and investigate any errors that may log in red. If the Twitter IDs being used are the news organizations provided, wait for some breaking news to happen. The whole terminal will be covered in green tweets.</p>
<h2>What Can Be Done With This?</h2>
<p>The better question is what can&apos;t be done with this. Well it won&apos;t cook you dinner, but being connected directly to an app like Twitter can be very powerful.</p>
<p>A company called Dataminr, that is based in New York City, uses this basic concept to track news events on Twitter before they happen. Dataminr proved their value in 2011 when their technology recognized hashtags of unrest in Arab nations. This unrest would later be named The Arab Spring.</p>
<p>There are an excessive amount of small companies on the internet that sell hashtag aggregation services for weddings, birthdays and other life milestone events. A startup I used to work for called Offerpop aggregates content from hashtags for marketing reasons.</p>
<p>I built an app using this small app as a foundation. My app was called NewsSeed and it matched keywords from Tweets to group new stories from different news sources. The possibilties are limitless.</p>
<h2>Handling Sync and Async</h2>
<p>A challenge that may present itself is handling each tweet synchronously and asynchronously. Going back to their filters, when each tweet is passed into each filter it will be syncronous. It will go through every line of code until the end, unless it is met with an asynchronous function.</p>
<p>One of the first things that comes to mind for handling each Tweet is storing them into a database. If this is something that needs to be done, handling retweets is going to propose a challenge if similar retweets are not to be stored in the database. When each of these Twitter ID&apos;s tweets are retweet, the filter is going to recieve every retweet. That could be hundreds or thousands of tweets, that are very similar, coming through the filter. It is probably not desireable to store all of them into a database. That is why they are all going through a filter.</p>
<p>One solution is to create a syncronous cache at the beginning of the filter. To do this in the filters directory create a folder called <code>cache</code> and put an <code>index.js</code> inside of it.</p>
<p><code>cd streams &amp;&amp; mkdir cache &amp;&amp; cd cache &amp;&amp; touch index.js</code></p>
<p>The <code>index.js</code> in the <code>cache</code> directory will just be a simple object with helper methods on it. As the tweets come in use the story link or another unique value as the key that will be placed onto this <code>cache</code> object. The cache that I used for my NewsSeed app looked like this.</p>
<pre><code><span>var</span> cache = {
  stories: {},
  check: <span><span>function</span>(<span>storyLink, tweetToString</span>) </span>{
    <span>if</span>(<span>this</span>.stories[storyLink] &amp;&amp; <span>this</span>.stories[storyLink].tweet &amp;&amp; <span>this</span>.stories[storyLink].tweet === tweetToString) {
      <span>return</span> <span>true</span>;
    }

    <span>return</span> <span>false</span>;
  },
  set: <span><span>function</span>(<span>storyLink, tweetToString</span>) </span>{
    <span>this</span>.stories[storyLink] = {
      tweet: tweetToString
    };
  },
  <span>delete</span>: <span><span>function</span>(<span>key, storyLink</span>) </span>{
    <span>delete</span> <span>this</span>[key][storyLink];
  }
};

<span>module</span>.exports = cache;
</code></pre>
<p>Now the filter that is being used might look something like this</p>
<pre><code><span>var</span> chalk = <span>require</span>(<span>&apos;chalk&apos;</span>);
<span>var</span> cache = <span>require</span>(<span>&apos;./cache&apos;</span>);

<span>var</span> streamFilter = <span><span>function</span>(<span>tweet</span>) </span>{
    <span>var</span> storyLink = <span>// A function that gets the storyLink</span>
    <span>var</span> tweetToString = <span>// A function that parses the tweet into a string</span>

    <span>// If our tweet is not in cache, put it in the cache</span>
    <span>if</span> (!cache.check(storyLink, tweetToString)) {
        cache.set(storyLink, tweetToString);

        <span>// do something asynchronous</span>

        <span>console</span>.log(chalk.green(tweet.user.screen_name, <span>&apos; : &apos;</span> , tweet.text));
    }
};

<span>module</span>.exports = streamFilter;
</code></pre>
<p>Because all of the methods in the cache are syncronous similar tweets that are already set in the cache will skip the code in the condtional statement.</p>
<h2>Conclusion</h2>
<p>The key take aways from this small project are environmental variables, the Twitter API and the sync vs async workflow. There was a good portion on enviromental varaibles. What they are, how to use them and how to keep them safe were all covered. Knowing the Twitter API can be very powerful. This project only scratched the surface of the data that could be recieved from Twitter. Twitter&apos;s OAuth workflow could also be a good thing to know. Finally, sync and async workflow are the blessing and curse of javascript. Mastering it is very important.</p>
</div></div></div></div></div></div></div></div>
