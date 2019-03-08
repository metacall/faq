# FAQ
**MetaCall Frequently Asked Questions.**

1. [What is Metacall?](#whatismetacall)
2. [What is Metacall used for?](#whatuse)
3. [Does Function Mesh application architecture pattern benefit from Metacall technology?](#functionmeshmetacallrel)
4. [Can Function Mesh be implemented without Metacall?](#isfnmeshdeponmetacall)
5. [How is Metacall different from REST and RPC?](#MetdiffRestRPC)
6. [Is Metacall a Polyglot?](#ispolyglot)
7. [Who is the target audience for Metacall?](#targetaudience)
---
## What is Metacall?
Metacall helps you build serverless applications using a more fine-grained, scalable and NoOps oriented FunctionMesh instead of ServiceMesh and DevOps approach. MetaCall automagically converts your code into a **[Function Mesh](https://medium.com/@metacall/function-mesh-architecture-c0304ba4bad0)** and auto-scales individual hot parts or functions of your app. 

Metacall not only helps to simplify application development but also speedsup time to market. Developers can focus purely on code and  business logic instead of expending expensive development cycles on DevOps.

## What is Metacall used for?

*	The purpose of Metacall is to integrate local development with function-mesh transparently.

*	Metacall enables a new, smarter and productive way to develop distributed systems. It is a library that allows you to execute code across boundaries – be it language, process, pod, container, node or server boundaries. Your code could be in language X and it can invoke functions implemented in languages X, Y, and Z where X, Y, Z are the set of supported languages in Metacall core. 

*	CRUD via HTTP in REST APIs is a form of RPC with limited functions. Metacall extends the abstraction to any function that can be called remotely and not just limited to semantics of CRUD. (Note REST, i.e., CRUD over HTTP is sort of a degenerate form of RPC). Over and above these functions could be implemented in a different programming language and running on a different pod / container / server / node distributed geographically. (?)

## Does Function Mesh application architecture pattern benefit from Metacall technology?

Function Mesh is a new transparent way to inter-connect serverless functions. Function Mesh enables building of complex distributed systems while efficiently scaling only the hot functional parts of the system. Metacall is an enabling technology that helps to build the function gateway of sorts, under the covers. The only thing developers need to care about is writing a small configuration file indicating what code they want to publish and the function gateway will be automatically created by Metacall.  Scaling up and down of Metacall instances happens in an automatic manner governed by certain configurable limits such as $$ spent for resources, response time or latencies. {Elaborate – is there anything unique that Metacall does for FunctionMesh that others cannot – such as **[OpenFaaS](https://www.openfaas.com/)**, **[Zeit](https://zeit.co/)**, **[Kubeless](https://kubeless.io/)**?}

## Can Function Mesh be implemented without Metacall?

*Answer TBD - For e.g., RPC, REST APIs - are those used to build function mesh without using Metacall?*

## How is Metacall different from REST and RPC?

If you look closely, REST APIs comprise of CRUD (Create, Read, Update, Delete) operations using HTTP. It is sort of RPC with limited functions the CRUD. Metacall extends this abstraction to any function that can be called remotely and not just limited to semantics of CRUD. In other words, REST, ie, CRUD over HTTP is sort of a degenerate form of RPC. In addition, these functions could be implemented in a different programming language and may be running on a different pod or container or node or server which is distributed geographically.  TBD - How Metacall is different from RPC or is it?

## Is Metacall a Polyglot? 

Yes, Metacall is a Polyglot as it can help integrate functionality across application components written in different languages.  

* Currently supports following languages:
* In future: *TBD Pending*

## Who is the target audience for Metacall?
**Target Audience**: Developers, Solution Architects.

**Key Use case**:
Metacall is useful for enterprises that need to migrate legacy or traditional non-micro-services architecture based distributed application solutions (monolithic, SoA) without refactoring the entire code base.  It is also very useful for developer’s productivity and eliminates the need to setup complex K8s cluster for testing code in production.  

Metacall enables developers to test the code in local just as it would run in production – saves time and resources and brings solutions to market faster.
