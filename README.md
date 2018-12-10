# Blog.github.io  
## Basic Concept of Distributed System:  
>A distributed system is a system whose components are located on different networked computers,  
>which then communicate and coordinate their actions by passing messages to one another.  
>Distributed computing also refers to the use of distributed systems to solve computational problems.  
>In distributed computing, a problem is divided into many tasks, each of which is solved by one or more computers, 
>which communicate with each other via message passing.  
>>( https://en.wikipedia.org/wiki/Distributed_computing)  
  

>These machines have a shared state, operate concurrently and can fail independently without  
>affecting the whole system’s uptime.  

>A good example to illuminate this concept: 
>>( https://hackernoon.com/a-thorough-introduction-to-distributed-systems-3b91562c9b3c)  

>Let’s compare a traditional database with a distributed database!  
>Traditional databases are stored on the filesystem of one single machine,  
>whenever you want to fetch/insert information in it — you talk to that machine directly. 
###Traditional System:
              ![GitHub](https://github.com/XianquanLiao/Blog.github.io/blob/master/Traditional%20System.jpg "Traditional System")  
 
>If we distribute this database system, we’d need to have this database run on multiple machines at the same time.  
>The user must be able to talk to whichever machine he chooses.  
###Distributed System:
              ![GitHub](https://github.com/XianquanLiao/Blog.github.io/blob/master/Distributed%20System.jpg "Traditional System")  

>Systems are always distributed by necessity. What a distributed system enables you to do is scale horizontally.  
>Going back to our previous example of the single database server, the only way to handle more traffic would be  
>to upgrade the hardware the database is running on. This is called scaling vertically.
>Scaling vertically is all well and good while you can, but after a certain point you will see that even  
>the best hardware is not sufficient for enough traffic, not to mention impractical to host.  
>Scaling horizontally simply means adding more computers rather than upgrading the hardware of a single one. 
>It is significantly cheaper than vertical scaling after a certain threshold but that is not its main case for preference.
>Vertical scaling can only bump your performance up to the latest hardware’s capabilities.  
>These capabilities prove to be insufficient for technological companies with moderate to big workloads.  
>The best thing about horizontal scaling is that you have no cap on how much you can scale —  
>whenever performance degrades you simply add another machine, up to infinity potentially.  
>That's why the distributed system is widely existed, and it is necessary to learn about this concept.

##Introduction to Serverless Computing:  
>One of the many important techniques in the field of distributed system is serverless computing  
>and I want to particularly introduce what is the serverless computing and what kind of features it has.
  
>Serverless computing is a cloud-computing execution model in which the cloud provider acts as the server,  
>dynamically managing the allocation of machine resources. The name "serverless computing" is used  
>because the server management and capacity planning decisions are completely hidden from the developer or operator.  
>Serverless code can be used in conjunction with code deployed in traditional styles, such as microservices.  
>Alternatively, applications can be written to be purely serverless and use no provisioned servers at all.  
>Most, but not all, serverless vendors offer compute runtimes, also known as function as a service (FaaS) platforms,  
>which execute application logic but do not store data. 
>>(https://en.wikipedia.org/wiki/Serverless_computing)  

>An example(UI-driven applications):
>A traditional three-tier client-oriented system with server-side logic. A good example is a typical ecommerce app.
###Tradtional 3-tier System:
              ![GitHub](https://github.com/XianquanLiao/Blog.github.io/blob/master/3-Tier%20System.jpg "Traditional 3-tier System")  

>With this architecture the client can be relatively unintelligent, with much of the logic  
>in the system—authentication, page navigation, searching, transactions—implemented by the server application.  
###With a Serverless architecture this may end up looking more like this:  
              ![GitHub](https://github.com/XianquanLiao/Blog.github.io/blob/master/Serverless%20System.jpg "Serverless System")  

>This example demonstrates a very important point about Serverless architectures. In the original version,  
>all flow, control, and security was managed by the central server application. In the Serverless version,  
>there is no central arbiter of these concerns. Instead we see each component playing a more architecturally  
>aware role—an idea also common in a microservices approach.
>There are many benefits to such an approach. Systems built this way are often “more flexible and  
>amenable to change,” both as a whole and through independent updates to components.
>>( https://martinfowler.com/articles/serverless.html)

###>Benefits: 
>>(https://en.wikipedia.org/wiki/Serverless_computing)
>####1. Reduced operational cost
>Serverless can be more cost-effective than renting or purchasing a fixed quantity of servers,  
>It allows you to pay someone to manage servers, databases and even application logic that you might otherwise  
>manage yourself. Since you're using a predefined service that many other people will also be using we see an Economy  
>of Scale effect: you pay less for your managed database because one vendor is running thousands of very similar databases.

>####2. Elasticity verses Scalability
>In addition, a serverless architecture means that developers and operators do not need to spend time setting up  
>and tuning autoscaling policies or systems; the cloud provider is responsible for seamlessly scaling the capacity to the demand. 
>As cloud native systems inherently scale down as well as up, these systems are known as elastic rather than scalable.
>Small teams of developers are able to run code themselves without the dependence upon teams of infrastructure and support engineers. 

>####3. Productivity
>With Function as a service, the units of code exposed to the outside world are simple functions.  
>This means that typically, the programmer does not have to worry about multithreading or directly handling  
>HTTP requests in their code, simplifying the task of back-end software development.

###>Drawbacks:  
>>(https://en.wikipedia.org/wiki/Serverless_computing)
>####1. Performance
>Infrequently-used serverless code may suffer from greater response latency than code that is continuously  
>running on a dedicated server, virtual machine, or container. This is because, unlike with autoscaling,  
>the cloud provider typically "spins down" the serverless code completely when not in use. This means that  
>if the runtime requires a significant amount of time to start up, it will create additional latency.

>####2. Resource limits
>Serverless computing is not suited to some computing workloads, such as high-performance computing,  
>because of the resource limits imposed by cloud providers, and also because it would likely be cheaper  
>to bulk-provision the number of servers believed to be required at any given point in time.

>####3. Monitoring and debugging
>Diagnosing performance or excessive resource usage problems with serverless code may be more difficult  
>than with traditional server code, because although entire functions can be timed, there is typically  
>no ability to dig into more detail by attaching profilers, debuggers or APM tools. Furthermore, the environment  
>in which the code runs is typically not open source, so its performance characteristics cannot be  
>precisely replicated in a local environment.

>####4. Security
>Serverless is sometimes mistakenly considered as more secure than traditional architectures.  
>While this is true to some extent because OS vulnerabilities are taken care of by the cloud provider,  
>the total attack surface is significantly larger as there are many more components to the application  
>compared to traditional architectures and each component is an entry point to the serverless application.  
>Moreover, the security solutions customers used to have to protect their cloud workloads become  
>irrelevant as customers cannot control and install anything on the endpoint and network level such as IDS/IPS. 
>This is intensified by the mono-culture properties of the entire server network. (A single flaw can be applied globally.)

>####5. Privacy
>Many serverless function environments are based on proprietary public cloud environments.  
>Here, some privacy implications have to be considered, such as shared resources and access  
>by external employees. However, serverless computing can also be done on private cloud environment  
>or even on-premises, using for example the Kubernetes platform. This gives companies full control  
>over privacy mechanisms, just as with hosting in traditional server setups.

>####6. Standards
>Serverless computing is covered by IDCA (International Data Center Authority in their Framework AE360)  
>However, the part related to portability can be an issue when moving business logic from one public cloud  
>to another for which the docker solution was created. Cloud Native Computing Foundation (CNCF) is  
>also working on developing a specification with Oracle. 
 
  
