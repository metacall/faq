# FAQ
**MetaCall Frequently Asked Questions.**

1. [What is MetaCall?](#Q1)
2. [What is MetaCall used for?](#Q2)
3. [Does Function Mesh application architecture pattern benefit from MetaCall technology?](#Q3)
4. [Can Function Mesh be implemented without MetaCall?](#Q4)
5. [How is MetaCall different from REST and RPC?](#Q5)
6. [Is MetaCall a Polyglot?](#Q6)
7. [Who is the target audience for MetaCall?](#Q7)
8. [Which applications / workloads have the potential to benefit the most from MetaCall?](#Q8)
9. [Can MetaCall be used for SOA / Legacy / Monolithic / Micro-services architecture-based applications? Or is it suited for only some of these application architectures?](#Q9)
10.	[How is MetaCall same or different or better than pure REST and RPC?](#Q10)
11. [Is MetaCall meant for private function calls or also for public APIs?](#Q11)
12.	[What are the key MetaCall differentiations factors from say OpenFaaS, Zeit, Kubeless, other competing technologies?](#Q12)
13. [Is there any benchmark data to show how MetaCall compares with alternative technologies?](#Q13)
14.	[What are some of the benefits associated with adopting MetaCall?](#Q14)
15.	[Are there any challenges associated with MetaCall adoption?](#Q15)
16.	[How is MetaCall implemented?  What is its high-level architecture?](#Q16)
17.	[What is Metacall’s scaling model?](#Q17)
18.	[Is MetaCall cross-platform?](#Q18)
19.	[What are some of the MetaCall use cases?](#Q19)
20.	[List some of the benefits of MetaCall.](Q20)
21. [What is the difference between Metacall and AWS Lambda?](#Q21)
---

<div id='Q1'/>

## What is MetaCall?
MetaCall helps you build serverless applications using a more fine-grained, scalable and NoOps oriented FunctionMesh instead of ServiceMesh and DevOps approach. MetaCall automagically converts your code into a **[Function Mesh](https://medium.com/@metacall/function-mesh-architecture-c0304ba4bad0)** and auto-scales individual hot parts or functions of your app. 

MetaCall not only helps to simplify application development but also speedsup time to market. Developers can focus purely on code and  business logic instead of expending expensive development cycles on DevOps.

<div id='Q2'/>

## What is MetaCall used for?

*	The purpose of MetaCall is to integrate local development with function-mesh transparently.

*	MetaCall enables a new, smarter and productive way to develop distributed systems. It is a library that allows you to execute code across boundaries – be it language, process, pod, container, node or server boundaries. Your code could be in language X and it can invoke functions implemented in languages X, Y, and Z where X, Y, Z are the set of supported languages in MetaCall core. 

*	CRUD via HTTP in REST APIs is a form of RPC with limited functions. MetaCall extends the abstraction to any function that can be called remotely and not just limited to semantics of CRUD. (Note REST, i.e., CRUD over HTTP is sort of a degenerate form of RPC). Over and above these functions could be implemented in a different programming language and running on a different pod / container / server / node distributed geographically. (?)

<div id='Q3'/>

## Does Function Mesh application architecture pattern benefit from MetaCall technology?

Function Mesh is a new transparent way to inter-connect serverless functions. Function Mesh enables building of complex distributed systems while efficiently scaling only the hot functional parts of the system. MetaCall is an enabling technology that helps to build the function gateway of sorts, under the covers. The only thing developers need to care about is writing a small configuration file indicating what code they want to publish and the function gateway will be automatically created by MetaCall.  Scaling up and down of MetaCall instances happens in an automatic manner governed by certain configurable limits such as $$ spent for resources, response time or latencies. {Elaborate – is there anything unique that MetaCall does for FunctionMesh that others cannot – such as **[OpenFaaS](https://www.openfaas.com/)**, **[Zeit](https://zeit.co/)**, **[Kubeless](https://kubeless.io/)**?}

<div id='Q4'/>

## Can Function Mesh be implemented without MetaCall?

*Answer TBD - For e.g., RPC, REST APIs - are those used to build function mesh without using MetaCall?*

<div id='Q5'/>

## How is MetaCall different from REST and RPC?

If you look closely, REST APIs comprise of CRUD (Create, Read, Update, Delete) operations using HTTP. It is sort of RPC with limited functions the CRUD. MetaCall extends this abstraction to any function that can be called remotely and not just limited to semantics of CRUD. In other words, REST, ie, CRUD over HTTP is sort of a degenerate form of RPC. In addition, these functions could be implemented in a different programming language and may be running on a different pod or container or node or server which is distributed geographically.  TBD - How MetaCall is different from RPC or is it?

<div id='Q6'/>

## Is MetaCall a Polyglot? 

Yes, MetaCall is a Polyglot as it can help integrate functionality across application components written in different languages.  

* Currently supports following languages:
* In future: *TBD Pending*

<div id='Q7'/>

## Who is the target audience for MetaCall?
**Target Audience**: Developers, Solution Architects.

**Key Use case**:

MetaCall is useful for enterprises that need to migrate legacy or traditional non-micro-services architecture based distributed application solutions (monolithic, SoA) without refactoring the entire code base.  It is also very useful for developer’s productivity and eliminates the need to setup complex K8s cluster for testing code in production.  

MetaCall enables developers to test the code in local just as it would run in production – saves time and resources and brings solutions to market faster.

<div id='Q8'/>

## Which applications / workloads have the potential to benefit the most from MetaCall?

|   Application Type               |   Benefits with MetaCall   |   Comments             |
|----------------------------------|:--------------------------:|------------------------|
| Application with persistent or long-lived interactions and inter-service connections for performing tasks that can scale up or down quickly| Yes         |     `Need confirmation from V`     |
| Applications with short term intermittent communication across components or micro-services where these interactions can scale up or down fast | Yes         |     `Need confirmation from V`     |
| Applications that are not front-end facing but in deeper end of the stack and deal with caches, databases and intermediary services |Yes         |     `Need confirmation from V`     |
| Applications with bi-directional data flow |? | |
| CPU-centric applications |? | |
| I/O intensive applications |? | |
| Message Broker based big data applications? (ETL, Hadoop, Spark, Flink – data warehousing apps) | ? | |
| Real time messaging application for Big Data Analytics | ? | *Need confirmation from V* **[Reference: Real time messaging for analytics](https://medium.com/@natemurthy/rest-rpc-and-brokered-messaging-b775aeb0db3)**|
---

<div id='Q9'/>

## Can MetaCall be used for SOA / Legacy / Monolithic / Micro-services architecture-based applications? Or is it suited for only some of these application architectures?

MetaCall can be used for either of the above.  It is not limited to an application architecture type.

<div id='Q10'/>

##	How is MetaCall same or different or better than pure REST and RPC? 

* As compared to REST/HTTP method, RPC is simpler and mature, **[request response nature helps in tracing](https://medium.com/@natemurthy/rest-rpc-and-brokered-messaging-b775aeb0db3)** the calls in large scale distributed systems. Does MetaCall assist, in any way, with debugging and tracing issues in distributed solutions?
* Defining interaction with services across process and server boundaries is richer with RPC than with REST limited by CRUD semantics.
* RPC is suitable for one-one or one-many communications.  Many to one such as in data streaming, fan-in and fan-out is a tricky one – with MetaCall – the implementation addresses this (?)
* MetaCall is better than pure RPC as it provides function gateway functionality and more scalable and higher in performance than pure RPC.

<div id='Q11'/>

##	Is MetaCall meant for private function calls or also for public APIs?

*Answer - check with V*

<div id='Q12'/>

## What are the key MetaCall differentiations factors from say **[OpenFaaS](https://www.openfaas.com/)**, **[Zeit](https://zeit.co/)**, **[Kubeless}(https://kubeless.io/)**, other competing technologies?

Refer to the picture below.  It shows how MetaCall differs from competition:

![MetaCall Competition][metacall-compet]
*MetaCall vs. Competition*

[metacall-compet]: https://github.com/metacall/faq/blob/master/fig/metacall-compet.png

<div id='Q13'/>

## Is there any benchmark data to show how MetaCall compares with alternative technologies?

Here is some of the available benchmark data for MetaCall (beta). More benchmarking tests are underway and will be updated shortly.

**Test Description**

Simple function that merges two strings using the following technologies:

1.	Flask (Python http server)
2.	Express (Node.js http server)
3.	MetaCall with Python
4.	MetaCall with Node.js
5.	NginX (no back end at all)

**Results:** 

- MetaCall with Node.js is 0.3-0.4X faster than Express (Node.js http server)
- Typically, Express is much faster than Flask because it is I/O focused. With MetaCall with Python is 17X to 30X faster than Flask.  {Is it faster than Express – does MetaCall put flask on steroids in a way?}
- MetaCall with Python is 2X faster than MetaCall with Node.js

**Benchmark configuration details**
No connections used, only function calls to understand performance overhead of call itself. MetaCall can do 1M calls per second without any optimizations turned on in a dual core Xeon processor. Intel Xeon processor with 20 cores – server. VM with 10 cores was used to run the test. Xeon W-2155 13.75M cache, 3.3GHz processor.

<div id='Q14'/>

## What are some of the benefits associated with adopting MetaCall?

Following is a placeholder answer, we need to refine it as per V's inputs.

* MetaCall eases the DevOps and deployment issues associated with applications built using Micro-services architecture and deployed using containers, orchestrated via K8s. It allows testing of same code in local environment. The same code runs in distributed environment. 
* MetaCall helps enterprises simplify and evolve DevOps into NoOps with the simplicity of deployment and automation. 
* Polyglot Engineering – Support for multiple languages – Multi-lingual – helps integrate various programming languages. This helps communication across application components developed in different languages.
* Helps to integrate Legacy applications in cloud and hybrid environments via phased migration instead of long tedious refactoring
* Removes dependency on third party solutions such as AWS Lambda


<div id='Q15'/>

## Are there any challenges associated with MetaCall adoption?

- MetaCall uses QUIC (HTTP/3) technology underneath. As of **[November 2018](https://www.zdnet.com/article/http-over-quic-to-be-renamed-http3/)**, 31.2% of top 10 million websites support HTTP/2 and only 1.2% sites support QUIC.  Is this going to be a limiting factor for MetaCall adoption?

<div id='Q16'/>

## How is MetaCall implemented?  What is its high-level architecture?

MetaCall implementation uses a higher-level protocol (QUIC / HTTP3) to reduce RPC overheads.  It uses a high-performance multi-core asynchronous I/O model.

<div id='Q17'/>

## 17.	What is Metacall’s scaling model?

MetaCall has unique scaling model that is more granular and more compute resource-efficient than micro-services and REST based API interaction models. MetaCall can scale at 3 levels – per process, per pod and per function-mesh.  Basically, it allows you to do more work with less resources and enables finer-grained resource utilization. {Any benchmark run numbers here would be useful – say with MetaCall, xyz micro-services benchmark ran 5X times faster than without MetaCall.}

<div id='Q18'/>

## Is MetaCall cross-platform?
MetaCall is a cross platform architecture – supports any of the following Oss
	Currently: Debian Linux
	In future: OSX (?)

<div id='Q19'/>

## What are some of the MetaCall use cases and examples?

**MetaCall use cases** – TBD

**MetaCall examples** - see Auth Function Mesh and refer to the **[examples folder in GitHub.](https://github.com/metacall/examples)**

<div id='Q20'/>

## List some of the benefits of MetaCall.

- Developer Productivity
  * MetaCall enables developers to test their code locally while the same code can be run across clusters at runtime.  
  * It saves on test/debug resources and helps with developer productivity.
  * During development and testing, there is no dependency on launching K8s cluster, or installing Minikube or testing by using AWS/cloud resources. 

- Saves time, lowers costs
  * MetaCall reduces the need of additional test resources required for cluster setup and testing
  * Helps to save cloud resource costs

- Simplifies and speeds up Legacy code and cloud technologies integration
 * Instead of total refactoring to bring legacy code to cloud, MetaCall allows phasewise and staged migration of chunks of functionality to contemporary cloud application architectures models as it allows function calls across language, node and process boundaries.

<div id='Q21'/>

## What is the difference between Metacall and AWS Lambda?

Unlike Lambda, Metacall does not have cold starts. Refer to the figures below:

|![Lambda Model][lambda]|
|:---:|
|*Function scaling model with Lambda* |
[lambda]: https://github.com/metacall/faq/blob/master/fig/lambda.png

|![MetaCall Model][metacall]|
|:---:|
|*Function scaling model with MetaCall* |
[metacall]: https://github.com/metacall/faq/blob/master/fig/metacall.png


 With Lambda, you can have two or more layers of LB to scale up function and obtain function mesh – see figure. With Metacall, you can have any-to-any function mesh and it is much less expensive.  In Metacall model, each function also acts as a gateway with the help of Metacall library. This tremendously helps in scaling and everything is integrated.  No third party products are required for integrating across languages, platforms and components or routing function calls.

<div id='Q22'/>

##

<div id='Q23'/>

##

<div id='Q24'/>

##


<div id='Q25'/>

##


<div id='Q26'/>

##


<div id='Q27'/>

##


<div id='Q28'/>

##


<div id='Q29'/>

##


<div id='Q30'/>

##