## Node JS Architecture

Before starting some Node JS programming examples, it’s important to have an idea about Node JS architecture. We will discuss about “How Node JS works under-the-hood, what type of processing model it is following, How Node JS handles concurrent request with Single-Threaded model” etc. in this post.

### Node JS Single Threaded Event Loop Model

As we have already discussed, Node JS applications uses “Single Threaded Event Loop Model” architecture to handle multiple concurrent clients.

There are many web application technologies like JSP, Spring MVC, ASP.NET, HTML, Ajax, jQuery etc. But all these technologies follow “Multi-Threaded Request-Response” architecture to handle multiple concurrent clients.

We are already familiar with “Multi-Threaded Request-Response” architecture because it’s used by most of the web application frameworks. But why Node JS Platform has chosen different architecture to develop web applications. What is the major differences between multithreaded and single threaded event loop architecture.

Any web developer can learn Node JS and develop applications very easily. However without understanding Node JS Internals, we cannot design and develop Node JS Applications very well. So before starting developing Node JS Applications, first we will learn Node JS Platform internals.

### Node JS Platform

Node JS Platform uses “Single Threaded Event Loop” architecture to handle multiple concurrent clients. Then how it really handles concurrent client requests without using multiple threads. What is Event Loop model? We will discuss these concepts one by one.

Before discussing “Single Threaded Event Loop” architecture, first we will go through famous “Multi-Threaded Request-Response” architecture.

### Traditional Web Application Processing Model

Any Web Application developed without Node JS, typically follows “Multi-Threaded Request-Response” model. Simply we can call this model as Request/Response Model.


Client sends request to the server, then server do some processing based on clients request, prepare response and send it back to the client.

This model uses HTTP protocol. As HTTP is a Stateless Protocol, this Request/Response model is also Stateless Model. So we can call this as Request/Response Stateless Model.

However, this model uses Multiple Threads to handle concurrent client requests. Before discussing this model internals, first go through the diagram below.

**Request/Response Model Processing Steps:**

* Clients Send request to Web Server.
* Web Server internally maintains a Limited Thread pool to provide services to the Client Requests.
* Web Server is in infinite Loop and waiting for Client Incoming Requests
* Web Server receives those requests.
  * Web Server pickup one Client Request
  * Pickup one Thread from Thread pool
  * Assign this Thread to Client Request
  * This Thread will take care of reading Client request, processing Client request, performing any Blocking IO Operations (if required) and preparing Response
  * This Thread sends prepared response back to the Web Server
  * Web Server in-turn sends this response to the respective Client.
  * Server waits in Infinite loop and performs all sub-steps as mentioned above for all n clients. That means this model creates one Thread per Client request.

If more clients requests require Blocking IO Operations, then almost all threads are busy in preparing their responses. Then remaining clients Requests should wait for longer time.

![https://cdn.journaldev.com/wp-content/uploads/2015/04/Request-Response-Model.png](https://cdn.journaldev.com/wp-content/uploads/2015/04/Request-Response-Model.png)

<p><strong>Diagram Description</strong>:</p>
                                <ul>
                                    <li>Here &#8220;n&#8221; number of Clients Send request to Web Server. Let us assume they are accessing our Web Application concurrently.</li>
                                    <li>Let us assume, our Clients are Client-1, Client-2… and Client-n.</li>
                                    <li>Web Server internally maintains a Limited Thread pool. Let us assume &#8220;m&#8221; number of Threads in Thread pool.</li>
                                    <li>Web Server receives those requests one by one.
                                        <ul>
                                            <li>Web Server pickup Client-1 Request-1, Pickup one Thread T-1 from Thread pool and assign this request to Thread T-1
                                                <ul>
                                                    <li>Thread T-1 reads Client-1 Request-1 and process it</li>
                                                    <li>Client-1 Request-1 does not require any Blocking IO Operations</li>
                                                    <li>Thread T-1 does necessary steps and prepares Response-1 and send it back to the Server</li>
                                                    <li>Web Server in-turn send this Response-1 to the Client-1</li>
                                                </ul>
                                        </ul>
                                        <ul>
                                            <li>Web Server pickup another Client-2 Request-2, Pickup one Thread T-2 from Thread pool and assign this request to Thread T-2
                                                <ul>
                                                    <li>Thread T-2 reads Client-1 Request-2 and process it</li>
                                                    <li>Client-1 Request-2 does not require any Blocking IO Operations</li>
                                                    <li>Thread T-2 does necessary steps and prepares Response-2 and send it back to the Server</li>
                                                    <li>Web Server in-turn send this Response-2 to the Client-2</li>
                                                </ul>
                                        </ul>
                                        <ul>
                                            <li>Web Server pickup another Client-n Request-n, Pickup one Thread T-n from Thread pool and assign this request to Thread T-n
                                                <ul>
                                                    <li>Thread T-n reads Client-n Request-n and process it</li>
                                                    <li>Client-n Request-n require heavy Blocking IO and computation Operations</li>
                                                    <li>Thread T-n takes more time to interact with external systems, does necessary steps and prepares Response-n and send it back to the Server</li>
                                                    <li>Web Server in-turn send this Response-n to the Client-n</li>
                                                </ul>
                                        </ul>
                                        <p>If &#8220;n&#8221; is greater than &#8220;m&#8221; (Most of the times, its true), then server assigns Threads to Client Requests up to available Threads. After all m Threads are utilized, then remaining Client’s Request should wait in the Queue until some of the busy Threads finish their Request-Processing Job and free to pick up next Request.</p>
                                        <p>If those threads are busy with Blocking IO Tasks (For example, interacting with Database, file system, JMS Queue, external services etc.) for longer time, then remaining clients should wait longer time.</li>
                                            <li>Once Threads are free in Thread Pool and available for next tasks, Server pickup those threads and assign them to remaining Client Requests.</li>
                                            <li>Each Thread utilizes many resources like memory etc. So before going those Threads from busy state to waiting state, they should release all acquired resources.</li>
                                </ul>
                                <p><strong>Drawbacks of Request/Response Stateless Model</strong>:</p>
                                <ul>
                                    <li>Handling more and more concurrent client’s request is bit tough.</li>
                                    <li>When Concurrent client requests increases, then it should use more and more threads, finally they eat up more memory.</li>
                                    <li>Sometimes, Client’s Request should wait for available threads to process their requests.</li>
                                    <li>Wastes time in processing Blocking IO Tasks.</li>
                                </ul>
                                <h3>Node JS Architecture &#8211; Single Threaded Event Loop</h3>
                                <p>Node JS Platform does not follow Request/Response Multi-Threaded Stateless Model. It follows Single Threaded with Event Loop Model. Node JS Processing model mainly based on Javascript Event based model with Javascript callback mechanism.</p>


