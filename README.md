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
10.	[How is Metacall same or different or better than pure REST and RPC?](#Q10)
11. [Is Metacall meant for private function calls or also for public APIs?](#Q11)
12.	[What are the key Metacall differentiations factors from say OpenFaaS, Zeit, Kubeless, other competing technologies?](#Q12)
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

##	How is Metacall same or different or better than pure REST and RPC? 

* As compared to REST/HTTP method, RPC is simpler and mature, **[request response nature helps in tracing](https://medium.com/@natemurthy/rest-rpc-and-brokered-messaging-b775aeb0db3)** the calls in large scale distributed systems. Does Metacall assist, in any way, with debugging and tracing issues in distributed solutions?
* Defining interaction with services across process and server boundaries is richer with RPC than with REST limited by CRUD semantics.
* RPC is suitable for one-one or one-many communications.  Many to one such as in data streaming, fan-in and fan-out is a tricky one – with Metacall – the implementation addresses this (?)
* Metacall is better than pure RPC as it provides function gateway functionality and more scalable and higher in performance than pure RPC.

<div id='Q11'/>

##	Is Metacall meant for private function calls or also for public APIs?

*Answer - check with V*

<div id='Q12'/>

## What are the key Metacall differentiations factors from say **[OpenFaaS](https://www.openfaas.com/)**, **[Zeit](https://zeit.co/)**, **[Kubeless}(https://kubeless.io/)**, other competing technologies?



<div id='Q13'/>

##

<div id='Q14'/>

##

<div id='Q15'/>

##

<div id='Q16'/>

##

<div id='Q17'/>

##

<div id='Q18'/>

##

<div id='Q19'/>

##

<div id='Q20'/>

##

<div id='Q21'/>

##

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