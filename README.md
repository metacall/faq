# FAQ
**MetaCall Frequently Asked Questions.**

## A. General

1. [What is MetaCall?](#AQ1)
2. [What is MetaCall used for?](#AQ2)
3. [Does Function Mesh application architecture pattern benefit from MetaCall technology?](#AQ3)
4. [Can Function Mesh be implemented without MetaCall?](#AQ4)
5. [Is MetaCall a Polyglot?](#AQ5)
6. [Who is the target audience for MetaCall?](#AQ6)
7. [Which applications / workloads have the potential to benefit the most from MetaCall?](#AQ7)
8. [Can MetaCall be used for SOA / Legacy / Monolithic / Micro-services architecture-based applications? Or is it suited for only some of these application architectures?](#AQ8)
9. [Is MetaCall meant for private function calls or also for public APIs?](#AQ9)
10. [Is there any benchmark data to show how MetaCall compares with alternative technologies?](#AQ10)
11.	[What are some of the benefits associated with adopting MetaCall?](#AQ11)
12.	[Are there any challenges associated with MetaCall adoption?](#AQ12)
13.	[How is MetaCall implemented?  What is its high-level architecture?](#AQ13)
14.	[What is MetaCall’s scaling model?](#AQ14)
15.	[Is MetaCall cross-platform?](#AQ15)
16.	[What are some of the MetaCall use cases?](#AQ16)
17.	[List some of the benefits of MetaCall.](#AQ17)
18.	[How does MetaCall benefit Legacy code migration or evolution?](#AQ18)
19. [How does MetaCall help in progressive migration instead of refactoring and rebuilding legacy solutions?](#AQ19)
20. [How is MetaCall different in terms of number of functions that can be invoked or called per file?](#AQ20)
21.	[How does MetaCall offer the benefit of being a common solution for gateway, SQS?](#AQ21) 
22.	[Are there any disadvantages of using MetaCall?](#AQ22)
23.	[How does MetaCall benefit developer productivity?](#AQ23)
24.	[Who deploys MetaCall and scales it at runtime?](#AQ24)
25.	[Is MetaCall pluggable and supports different protocols?](#AQ25)
26. [What kind of FaaS does MetaCall support?](#AQ26)

## B. MetaCall vs. other similar technologies

1. [How is MetaCall different from REST and RPC?](#BQ1)
2.	[How is MetaCall same or different or better than pure REST and RPC?](#BQ2)
3.	[What are the key MetaCall differentiations factors from say OpenFaaS, Zeit, Kubeless, other competing technologies?](#BQ3)
4. [What is the difference between MetaCall and AWS Lambda?](#BQ4)
5. [Is MetaCall similar to AWS Lambda, Microsoft Azure Functions and Twilio? ](#BQ5)
6. [How does MetaCall provide value add that is beyond what other similar services such as AWS Lambda offer? ](#BQ6)
---

<div id='AQ1'/>

### What is MetaCall?
MetaCall helps you build serverless applications using a more fine-grained, scalable and NoOps oriented FunctionMesh instead of ServiceMesh and DevOps approach. MetaCall automagically converts your code into a **[Function Mesh](https://medium.com/@metacall/function-mesh-architecture-c0304ba4bad0)** and auto-scales individual hot parts or functions of your app. 

MetaCall not only helps to simplify application development but also speedsup time to market. Developers can focus purely on code and  business logic instead of expending expensive development cycles on DevOps.

<div id='AQ2'/>

### What is MetaCall used for?

*	The purpose of MetaCall is to integrate local development with function-mesh transparently.

*	MetaCall enables a new, smarter and productive way to develop distributed systems. It is a library that allows you to execute code across boundaries – be it language, process, pod, container, node or server boundaries. Your code could be in language X and it can invoke functions implemented in languages X, Y, and Z where X, Y, Z are the set of supported languages in MetaCall core. 

*	CRUD via HTTP in REST APIs is a form of RPC with limited functions. MetaCall extends the abstraction to any function that can be called remotely and not just limited to semantics of CRUD. (Note REST, i.e., CRUD over HTTP is sort of a degenerate form of RPC). Over and above these functions could be implemented in a different programming language and running on a different pod / container / server / node distributed geographically. (?)

<div id='AQ3'/>

### Does Function Mesh application architecture pattern benefit from MetaCall technology?

Function Mesh is a new transparent way to inter-connect serverless functions. Function Mesh enables building of complex distributed systems while efficiently scaling only the hot functional parts of the system. MetaCall is an enabling technology that helps to build the function gateway of sorts, under the covers. The only thing developers need to care about is writing a small configuration file indicating what code they want to publish and the function gateway will be automatically created by MetaCall.  Scaling up and down of MetaCall instances happens in an automatic manner governed by certain configurable limits such as $$ spent for resources, response time or latencies. {Elaborate – is there anything unique that MetaCall does for FunctionMesh that others cannot – such as **[OpenFaaS](https://www.openfaas.com/)**, **[Zeit](https://zeit.co/)**, **[Kubeless](https://kubeless.io/)**?}

<div id='AQ4'/>

### Can Function Mesh be implemented without MetaCall?

*Answer TBD - For e.g., RPC, REST APIs - are those used to build function mesh without using MetaCall?*

<div id='AQ5'/>

### Is MetaCall a Polyglot? 

Yes, MetaCall is a Polyglot as it can help integrate functionality across application components written in different languages.  

For a complete list of supported languages, refer to **[MetaCall Language Support - Backend)](https://github.com/metacall/core#2-language-support-backends)**

<div id='AQ6'/>

### Who is the target audience for MetaCall?
**Target Audience**: Developers, Solution Architects.

**Key Use case**:

MetaCall is useful for enterprises that need to migrate legacy or traditional non-micro-services architecture based distributed application solutions (monolithic, SoA) without refactoring the entire code base.  It is also very useful for developer’s productivity and eliminates the need to setup complex K8s cluster for testing code in production.  

MetaCall enables developers to test the code in local just as it would run in production – saves time and resources and brings solutions to market faster.

<div id='AQ7'/>

### Which applications / workloads have the potential to benefit the most from MetaCall?

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

<div id='AQ8'/>

### Can MetaCall be used for SOA / Legacy / Monolithic / Micro-services architecture-based applications? Or is it suited for only some of these application architectures?

MetaCall can be used for either of the above.  It is not limited to an application architecture type.

<div id='AQ9'/>

##	Is MetaCall meant for private function calls or also for public APIs?

*Answer - check with V*

<div id='AQ10'/>

### Is there any benchmark data to show how MetaCall compares with alternative technologies?

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

<div id='AQ11'/>

### What are some of the benefits associated with adopting MetaCall?

Following is a placeholder answer, we need to refine it as per V's inputs.

* MetaCall eases the DevOps and deployment issues associated with applications built using Micro-services architecture and deployed using containers, orchestrated via K8s. It allows testing of same code in local environment. The same code runs in distributed environment. 
* MetaCall helps enterprises simplify and evolve DevOps into NoOps with the simplicity of deployment and automation. 
* Polyglot Engineering – Support for multiple languages – Multi-lingual – helps integrate various programming languages. This helps communication across application components developed in different languages.
* Helps to integrate Legacy applications in cloud and hybrid environments via phased migration instead of long tedious refactoring
* Removes dependency on third party solutions such as AWS Lambda


<div id='AQ12'/>

### Are there any challenges associated with MetaCall adoption?

- MetaCall uses QUIC (HTTP/3) technology underneath. As of **[November 2018](https://www.zdnet.com/article/http-over-quic-to-be-renamed-http3/)**, 31.2% of top 10 million websites support HTTP/2 and only 1.2% sites support QUIC.  Is this going to be a limiting factor for MetaCall adoption?

<div id='AQ13'/>

### How is MetaCall implemented?  What is its high-level architecture?

MetaCall implementation uses a higher-level protocol (QUIC / HTTP3) to reduce RPC overheads.  It uses a high-performance multi-core asynchronous I/O model.

<div id='AQ14'/>

### What is MetaCall’s scaling model?

MetaCall has unique scaling model that is more granular and more compute resource-efficient than micro-services and REST based API interaction models. MetaCall can scale at 3 levels – per process, per pod and per function-mesh.  Basically, it allows you to do more work with less resources and enables finer-grained resource utilization. {Any benchmark run numbers here would be useful – say with MetaCall, xyz micro-services benchmark ran 5X times faster than without MetaCall.}

<div id='AQ15'/>

### Is MetaCall cross-platform?
MetaCall is a cross platform architecture – supports any of the following Oss
	Currently: Debian Linux
	In future: OSX (?)

<div id='AQ16'/>

### What are some of the MetaCall use cases and examples?

**MetaCall use cases** – TBD

**MetaCall examples** - see Auth Function Mesh and refer to the **[examples folder in GitHub.](https://github.com/metacall/examples)**

<div id='AQ17'/>

### List some of the benefits of MetaCall.

- Developer Productivity
  * MetaCall enables developers to test their code locally while the same code can be run across clusters at runtime.  
  * It saves on test/debug resources and helps with developer productivity.
  * During development and testing, there is no dependency on launching K8s cluster, or installing Minikube or testing by using AWS/cloud resources. 

- Saves time, lowers costs
  * MetaCall reduces the need of additional test resources required for cluster setup and testing
  * Helps to save cloud resource costs

- Simplifies and speeds up Legacy code and cloud technologies integration
 * Instead of total refactoring to bring legacy code to cloud, MetaCall allows phasewise and staged migration of chunks of functionality to contemporary cloud application architectures models as it allows function calls across language, node and process boundaries.

<div id='AQ18'/>

### How does MetaCall benefit Legacy code migration or evolution?

To bring Legacy code to cloud, or to evolve it using newer application architecture models such as micro-services, you need a service like Lambda.  Instead, you can use MetaCall and without rewriting legacy code, migrate some or all its functionality to the cloud.

<div id='AQ19'/>

### How does MetaCall help in progressive migration instead of refactoring and rebuilding legacy solutions?

Let us consider this example as shown in figures below:

| ![Phase Approach][phase] |
|:---:|
| *Function A calls functions B, C and D, all implemented in PHP * |

[phase]: https://github.com/metacall/faq/blob/master/fig/fn1.png

Fn A is in PHP and it calls code B, C and D. With MetaCall, you can progressively migrate functions to say Node JS or other implementations required as part of evolving the legacy code without having to rewrite or refactor the whole of legacy code. Refer to figures below that show phased migration of PHP code to Node.js:

| ![Phase Approach1][phase1] | ![Phase Approach2][phase2]  | ![Phase Approach3][phase3] | 
|:---:|:---:|:---:|
| *Function C is implemented in Node.js and rest code is as is* | *Function B is nmigrated to Node.js* | *Function B, C and D are all in Node.js now* | 

[phase1]: https://github.com/metacall/faq/blob/master/fig/fn2.png
[phase2]: https://github.com/metacall/faq/blob/master/fig/fn3.png
[phase3]: https://github.com/metacall/faq/blob/master/fig/fn4.png
[phase4]: https://github.com/metacall/faq/blob/master/fig/fn5.png

Without MetaCall, you will need 6 months or so to move legacy code into new node.js or other models before you can verify and test. With metacall, you can do it in chunks – it helps with phased migration.  

| ![Phase Approach4][phase4] |
|:---:|
| *Legacy code migration and integration in phased manner* |

As indicated in the figure above, with MetaCall, you don’t need two teams – one to maintain legacy and another to refactor the code and make it work again using newer design and application architecture models.  Helps agile and reduces TTM.


<div id='AQ20'/>

### How is MetaCall different in terms of number of functions that can be invoked or called per file?

Nowadays when you do functions, you can only do one function per file.  MetaCall can do N functions per file. MetaCall allowsyou to write multiple functions in the same deployment. You can keep monolithic architecture or micro-services architecture and MetaCall will slice everything.  Monolith refer to pre MSA or SoA application architecture. {Need to highlight the benefit of this – how does this help developer , project, business}

<div id='AQ21'/>

### How does MetaCall offer the benefit of being a common solution for gateway, SQS?

*Answer to be provided by V*

<div id='AQ22'/>

### Are there any disadvantages of using MetaCall?

Lots of upside of MetaCall – downside – a small amount of resource is always consumed – to avoid cold starts. 

<div id='AQ23'/>

### How does MetaCall benefit developer productivity?
MetaCall simplifies test and debugging which is a nightmare in distributed application development. Test in local and the same code runs exactly the same way in production – across process, pod and container boundaries. During test it runs local. So no need to test in dev and again in production.


<div id='AQ24'/>

### Who deploys MetaCall and scales it at runtime? 
Self – automated? There is way to limit resource consumption – say by $$$ or number of replicas etc. How? {*Elaborate with teh help of V*}


<div id='AQ25'/>

### Is MetaCall pluggable and supports different protocols?
MetaCall implementation has two interfaces – on caller side the function gateway uses simple http (for now) – in future it could be pluggable so it could use GraphQL or XML or WebSockets.  At the other end, for function level communication or function gateway, it uses JSON-RPC. That could be pluggable too – it could use QUIC or gRPC  or RabbitMQ – whichever works better for the user in terms of solution performance, required communication bandwidth and latency.


<div id='AQ26'/>

### What kind of FaaS does MetaCall support?]
*Answer TBD*

## MetaCall vs. other similar technologies

<div id='BQ1'/>

### How is MetaCall different from REST and RPC?

If you look closely, REST APIs comprise of CRUD (Create, Read, Update, Delete) operations using HTTP. It is sort of RPC with limited functions the CRUD. MetaCall extends this abstraction to any function that can be called remotely and not just limited to semantics of CRUD. In other words, REST, ie, CRUD over HTTP is sort of a degenerate form of RPC. In addition, these functions could be implemented in a different programming language and may be running on a different pod or container or node or server which is distributed geographically.  TBD - How MetaCall is different from RPC or is it?

<div id='BQ2'/>

##	How is MetaCall same or different or better than pure REST and RPC? 

* As compared to REST/HTTP method, RPC is simpler and mature, **[request response nature helps in tracing](https://medium.com/@natemurthy/rest-rpc-and-brokered-messaging-b775aeb0db3)** the calls in large scale distributed systems. Does MetaCall assist, in any way, with debugging and tracing issues in distributed solutions?
* Defining interaction with services across process and server boundaries is richer with RPC than with REST limited by CRUD semantics.
* RPC is suitable for one-one or one-many communications.  Many to one such as in data streaming, fan-in and fan-out is a tricky one – with MetaCall – the implementation addresses this (?)
* MetaCall is better than pure RPC as it provides function gateway functionality and more scalable and higher in performance than pure RPC.

<div id='BQ3'/>

### What are the key MetaCall differentiations factors from say **[OpenFaaS](https://www.openfaas.com/)**, **[Zeit](https://zeit.co/)**, **[Kubeless](https://kubeless.io/)**, other competing technologies?

Refer to the picture below.  It shows how MetaCall differs from competition:

| ![MetaCall Competition][metacall-compet] |
|:---:|
| *MetaCall vs. Competition* |

[metacall-compet]: https://github.com/metacall/faq/blob/master/fig/metacall-compet.png

<div id='BQ4'/>

### What is the difference between MetaCall and AWS Lambda?

Unlike Lambda, MetaCall does not have cold starts. Refer to the figures below:

| ![Lambda Model][lambda] |
|:---:|
| *Function scaling model with Lambda* |

[lambda]: https://github.com/metacall/faq/blob/master/fig/lambda.png

| ![MetaCall Model][metacall] |
|:---:|
| *Function scaling model with MetaCall* |

[metacall]: https://github.com/metacall/faq/blob/master/fig/metacall.png


 With Lambda, you can have two or more layers of LB to scale up function and obtain function mesh – see figure. With MetaCall, you can have any-to-any function mesh and it is much less expensive.  In MetaCall model, each function also acts as a gateway with the help of MetaCall library. This tremendously helps in scaling and everything is integrated.  No third party products are required for integrating across languages, platforms and components or routing function calls.

<div id='BQ5'/>

### Is MetaCall similar to AWS Lambda, Microsoft Azure Functions and Twilio?
AWS Lambda and Microsoft Azure functions are generic serverless platforms that can be used to create FaaS solutions. Twilio is a cloud-based enterprise contact centre software platform which is specialized for communications code (SMS, Text, Voice) and allows creation of Twilio based apps for contact center, marketing and customer engagement.

MetaCall is similar to AWS Lambda and Azure functions in the sense that it also enables you to create FaaS based solutions.  However, the approach is very different.  Unlike AWS or Microsoft, MetaCall does not host and handle these functions via triggers. MetaCall automagically converts your code into a **[Function Mesh](https://medium.com/@metacall/function-mesh-architecture-c0304ba4bad0)**  and auto-scales individual hot parts or functions of your app.  Both Lambda and Azure Functions are similar in functionality as they propose to segment the application architecture in order to scale only the parts that require scaling, thus making consumption efficient with pay-per-function-use pricing model.  Unlike these two, MetaCall is not cloud provider proprietary as it can work for applications that are distributed across cloud, on-premises and even hybrid applications.

<div id='BQ6'/>

### How does MetaCall provide value add that is beyond what other similar services such as AWS Lambda offer?
In this question, we will try to answer the following queries related to MetaCall versus other similar technologies:

* Applications today are comprised of various moving parts in order to have scalable, efficient systems. Does MetaCall help in any way to replace any or all of these multiple moving parts or simplify them?

* When and how does MetaCall decide to optimize certain application actions?

* How does MetaCall based application compare with an optimized application system built using various AWS functionalities including Lambda?  Is it time saved to deployment? Is one better than the other in the long run?  What are the features that separate MetaCall from the rest?

Since it first appeared in 2014, AWS Lambda function implementation has not changed much. Microsoft Azure and Google cloud implemented very similar functions. The main drawback of these technologies as compared to MetaCall are detailed below:

* Current Lambda implementations are handlers in the form of: 

```
exports.handler = async (event) => { 
    return { 
        statusCode: 200, 
        headers:{ 
            "Content-Type": "text/html"
        }, 
        body: "Hello", 
    }; 
};
```

Handlers are **[different](https://softwareengineering.stackexchange.com/questions/205846/difference-between-trigger-handler-and-callback) from events or a function (callback). This handler is similar to the ones that exist in micro-services. When you use AWS Lambda, besides handlers, you will need to use AWS API Gateway in order to provide a valid REST endpoint to the Lambda handler. This complicates the problem multi-fold. Although it offers high granularity in terms of resource consumption, it imperates the use of other AWS services to make it work. Eventually, your application or solution will have to be split into many handlers, making it harder to manage. 

For example, 10 lambda functions require 10 separate deployments and 10 additional entries into the API Gateway. If you consider Database or Message Queue service implementations, then this resource and service dependency list begins to grow even further. Now imagine, if we try to inter-connect other kinds of Lambdas to build a complete application, it just gets more and more complex.

MetaCall deals with callback or a function which is very different from a handler. A function is a piece of executable code that is passed as an argument to other code, which is expected to call back (execute) the argument at some convenient time. The invocation may be immediate as in a synchronous callback, or it might happen at later time as in an asynchronous callback.

MetaCall functions look like as shown below:  

```
exports.hello_world = () => { 
    return "Hello"; 
}
```

Instead of looking like a handler, a MetaCall function looks like a normal function, that can be unit tested locally with common development tools. There is no need of extra framework or resource deployment in order to debug it or test it. Also, you can add more functions in the same file and they will be deployed separately. 

If you want to call other functions, you just have to call it like a normal function: 

```
import { other_function } from 'lib';

    exports.hello_world = () => { 
        return other_function(); 
    }
```

This will build a function mesh for you. The function ‘other_function’ may be executed on another peer, and the network resolution, scalability, and everything will be automatically taken care of by MetaCall.

Following are a list of benefits that MetaCall usage brings in to the developers and modern application development process:
1. Developers can build monolithic applications that will be fully distributed through MetaCall model.

2. MetaCall brings in an integrated API Gateway along with the functions, so there is no need for updating API Gateways for each function as in the case of AWS Lambda.

3. MetaCall allows application developers to write functions that can be tested locally, and validated globally in one shot. This is because they are normal functions and after being upload to the FaaS they will be automatically scaled.  Developers do not have to first test and then verify the deployment in production.

4. With MetaCall usage, the organization’s development lifecycle can be speeded up.  The developer encounters less friction when implementing the software.

5. MetaCall abstracts and hides the nuances and differences across multiple cloud vendors. With MetaCall, the developer will not be required to understand AWS or any other vendor specific implementation models because MetaCall integrates with repositories seamlessly.

6. MetaCall pricing is transparent and simpler. You will not have to deal with high segmentation and obfuscated costs. You will be able to see all telemetry and consumption of your code.

Here is how MetaCall overcomes some of the drawbacks associated with AWS Lambda:

* Metacall does not have **[typical serverless cold start] (https://thenewstack.io/how-cold-starts-impact-serverless-performance/)** performance issues.

* MetaCall automatically builds all dependencies with your functions in a standard way, using existing package managers.

* MetaCall is simple to use as it integrates into normal developer code, without complex frameworks, thus reducing vendor lock-in.

* Unlike AWS Lambda or typical serverless models, MetaCall enables you to test code locally and run it, later on, in the FaaS, with equivalent distributed execution without having to test it twice – once locally and then in production.

* MetaCall scales hot parts of your application depending on the workload and the function calls for each function published in the function mesh. The function mesh can be subdivided or compressed depending on the workload.

* MetaCall allows persistence though functions just by exporting common objects or arrays in the code. 

In short, instead of having to use AWS API Gateway, DynamoDB, Lambda, Elastic Load Balancer, Simple Queue Service... (among others), MetaCall solves application scaling and distribution problem at the same time, without DevOps. There is no learning curve or new framework needed for MetaCall use. Local testing capability significantly improves development time and cuts down on resource usage. The function mesh model allows for a more effective way of scaling, so we can scale horizontally, vertically and in a new third dimension introduced by the code splitting. 

All this is taken care of by MetaCall, with no additional cost or new knowledge required for the developer.

Besides the above, with MetaCall, there is an extra benefit: your existing code can be migrated to MetaCall easily, because as it does not need a new framework. MetaCall can consume classical functions. Migrations to MetaCall based FaaS environment can be done automatically.

