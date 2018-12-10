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

### Traditional System:
  ![GitHub](https://github.com/XianquanLiao/Blog.github.io/blob/master/Traditional%20System.jpg)  
 
>If we distribute this database system, we’d need to have this database run on multiple machines at the same time.  
>The user must be able to talk to whichever machine he chooses.  

### Distributed System:
  ![GitHub](https://github.com/XianquanLiao/Blog.github.io/blob/master/Distributed%20System.jpg)  

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

## Introduction to Serverless Computing:  
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

### Tradtional 3-tier System:
  ![GitHub](https://github.com/XianquanLiao/Blog.github.io/blob/master/3-Tier%20System.jpg)  

>With this architecture the client can be relatively unintelligent, with much of the logic  
>in the system—authentication, page navigation, searching, transactions—implemented by the server application.  

### With a Serverless architecture this may end up looking more like this:  
  ![GitHub](https://github.com/XianquanLiao/Blog.github.io/blob/master/Serverless%20System.jpg)  

>This example demonstrates a very important point about Serverless architectures. In the original version,  
>all flow, control, and security was managed by the central server application. In the Serverless version,  
>there is no central arbiter of these concerns. Instead we see each component playing a more architecturally  
>aware role—an idea also common in a microservices approach.
>There are many benefits to such an approach. Systems built this way are often “more flexible and  
>amenable to change,” both as a whole and through independent updates to components.
>>( https://martinfowler.com/articles/serverless.html)

###  Benefits: 
>In my process of developing an AWS Serverless application using the Serverless Framework,  
>the most convenient thing is that the first deployment is no different from the second and third deployments.  
>Just execute serverless deploy, and after a few minutes, our code runs online. If it's a traditional AWS app,  
>I need to SSH to my server for deployment so I can write my auto-deployment script. 

>In addition, I think the deployment is convenient, and the price is reasonable.  
>I can boldly use these services. Of course, there are other significant advantages.

#### 1. Reduce startup costs 
>When we develop a Web application as a company, we need a version management server,  
>a continuous integration server, a test server, an application version management repository, etc.  
>as a basic service during development. When running online, we need a good database server  
>in order to handle a large number of requests. When our app is for the average user, we need to:
>Mail service for sending reminders, registrations, etc.
>SMS service (according to the national real name), used for user authorization operations such as registration and login
>For large companies, these are off-the-shelf infrastructure. For start-ups, this is some startup cost.
>Serverless can be more cost-effective than renting or purchasing a fixed quantity of servers.

####  2. Automatic expansion capability
>Behind Serverless is FaaS (Function as a Services) such as AWS Lambda.
>For traditional applications, the way to handle more requests is to deploy more instances.  
>However, it is often too late to deploy instances. For FaaS, we don't need to do this, and FaaS will automatically expand.  
>It can launch as many copies of the instance as needed without lengthy deployment and configuration delays.

####  3. Reduce operating costs
>For start-ups, they have no infrastructure, no financial resources, and may not be able to build infrastructure.  
>Adopting cloud services is often the best option and can save a lot of money.  
>They can focus on creating products that are valuable to users. If a startup uses cloud services  
>instead of building servers yourself. Then, he will have more time to develop business functions than  
>focus on them. Just pay for the software at runtime.
>The biggest difference between Serverless and cloud server with function calculation is that  
>the cloud server needs to run all the time, and the function calculation is calculated on demand.  
>On-demand computing means that the function is run when the request arrives. When there is no request, it is not worth the money.
>At the beginning of the project, the number of users tends to grow slowly, and when we choose a server,  
>we often estimate it according to the users that may appear. At this time, it is often a waste of unnecessary costs.  
>However, even if the user suddenly breaks out, the Serverless app can handle it easily.  
>Just modify the database configuration and redeploy one.  

####  4. Faster development speed
>A range of basic services are already available due to the Serverless service provider.  
>As developers, we only need to focus on how to better implement the business, rather than some technical limitations.
>The service provider has prepared for us and tested this series of services. They are basically stable and reliable  
>and do not encounter particularly large problems. In fact, when we have enough powerful code,  
>such as using tests to ensure robustness, then with continuous integration, we can deploy directly to  
>the production environment when the PUSH code. Of course, it may not be so troublesome. We just need to  
>add a predeploy hook and do some automatic testing in this hook to release the new version directly locally.
>In this process, we don't need to consider too many postings.

###  Drawbacks:  
>As an application that starts at runtime, Serverless also has several problems we need to admit.

####  1. Not suitable for long-running applications
>Serverless runs when the request comes. This means that when the application is not running,  
>it will enter the "sleep state", and the next time the request comes, the application will need a startup time,  
>which is a cold start. At this time, you can use the CRON method or CloudWatch to wake up the application regularly.
>If your application needs to run uninterruptedly for a long time, processing a large number of requests,  
>then you may not be suitable for the Serverless architecture. In this case, using a cloud server like EC2  
>is often a better option. Because EC2 is cheaper in terms of price.
>EC2 is equivalent to buying a car, and Lambda is equivalent to renting a car.
>The cost of long-term car rental is definitely more expensive than buying a car, but you will lose some of  
>the maintenance costs. Therefore, this problem is actually a question worthy of in-depth calculation.

####  2. Fully dependent on third party services
>when you decide to use a cloud service, it means you may have gone without a return.  
>In this case, you can only put unimportant APIs on Serverless.
>Serverless is not a good thing for you when you already have a lot of infrastructure.  
>When we adopted the Serverless architecture, we were bundled with a special service provider.  
>We use AWS's services, so it's not that easy to move our services to Google Cloud.
>We need to modify the underlying code of the series. The solution that can be taken is  
>to establish an isolation layer. This means that when designing an application, you need to:
> - Quarantine API Gateway
> - Isolating the database layer
>These will also bring us some extra costs, and the problems that may be brought out will be more than the problems solved.
  
