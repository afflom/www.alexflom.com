+++
title = "A Primer on UOR"
author = "Alex Flom"
tags = ["UOR"]
date = "2023-09-25"
draft = false
+++


## Preface

The practice of applied data science rarely begins with a discourse on philosophy or metaphysical concepts, however, the fundamentals of human perception are built upon layers of these implicit metaphysical assumptions that frame the abstract concepts with which we understand, and communicate our observable reality.

By breaking down the intrinsic information structure of our universe into it's descriptive properties, reverse engineering these fundamentals, and designing a practical data system from those blueprints, Universal Object Reference (UOR) is both inspired by the natural world, and also introduces novel and profound implications theoretically enabling true to form modeling of anything and everything perceivable.

In short, UOR is an enriched data system inspired by the fundamental concepts which organize reality. In turn, UOR promises to break down the limitations of engineered information storage, discovery, understanding, distribution, and response systems.

During the early research phase of UOR's conceptual discovery and invention, multiple knowledge domains including technology and philosopy were key to UOR fluency, reducing the reach of the project to those few individuals motivated by interest and or expertise in both domains.

Now achieving the practical milestone of rudimentary but concrete technical implementation, UOR is ready for wider developer investigation and adoption. To that end, this primer describes the technical fundamentals of concrete UOR implementation.

The following is intended for those just starting their implementation journey, as we continue to explore the full capabilities and implications of UOR system design and development.


## Introduction

On a technical level, UOR is a new data system that enables scaleable, decentralized, and extensible information resource management, with strong expressions of identity and powerful access control heuristics.

For this primer, let's focus on the fundamental building blocks of UOR which form the foundation of all higher level capabilities, starting with the UOR data model as the basis of our enriched data framework.

After the fundamental implementation basics, we will cover manually applied notation examples, then take a look at how to leverage UOR for your own immediate uses.

Finally, we will conclude with an iterative and achievable adoption roadmap.


## Contents:

1. [UOR Data Model Fundamentals](#uor-data-model-fundamentals)
    - [Element](#uor-element)
    - [Statement](#uor-statement)
    - [Element Extensions](#uor-element-extensions)
1. [Relational Expressions](#relational-expressions)
1. [Embedded Algorithms](#embedded-algorithms)
1. [Case Studies](#case-studies)
    - [Software Supply Chain Security](#1-software-supply-chain-security)
    - [Healthcare Data Management](#2-healthcare-data-management)
    - [Information Technology Infrastructure Management](#3-information-technology-infrastructure-management)
    - [Federated Machine Learning](#4-federated-machine-learning)
    - [Social Network](#5-social-network)
    - [Network Embedded Algorithms](#6-network-embedded-algorithms)
1. [Implementing UOR](#implementing-uor)


## UOR Data Model Fundamentals

The UOR Data model originates from an application of [object oriented design](https://en.wikipedia.org/wiki/Object-oriented_design) principles applied as a framework to information storage and distribution.


### UOR Element

The UOR Element is the foundational building block within the UOR framework. It represents a discrete unit of data or resource within the system. The resourceType is a key attribute that identifies the type of the resource, akin to a [class in object-oriented programming](https://en.wikipedia.org/wiki/Class_(computer_programming)).

```
{
    "locatorType": "string (optional)",
    "resourceType": "string",
    "location": "object (optional)",
    "resource": "object"
}
```

The resource field points to, or contains the actual data or location information of the element. Optionally, locatorType can be used to specify how to locate or access the resource, and location provides specific details for accessing it, if needed.


### UOR Statement

The UOR Statement is a [semantic triple](https://en.wikipedia.org/wiki/Semantic_triple) expression of the [entity–attribute–value model](https://en.wikipedia.org/wiki/Entity%E2%80%93attribute%E2%80%93value_model) that links UOR Elements together to form relationship and context within the UOR system as a [knowledge graph](https://en.wikipedia.org/wiki/Knowledge_graph) topology expression.

```
{
    "schemaVersion": "integer",
    "resType": "string",
    "subject": "UOR Element",
    "predicate": "UOR Element",
    "object": "UOR Element"
}
```

3 UOR Elements assembled into a subject, predicate, and object expression form the UOR Statement. The additional `schemaVersion` and `resType` provide version control integrity and class metadata about the statement. This structure enables the representation of complex relationships and interactions between different data elements, while maintaining the semantic fidelity of the statement.


### UOR Element Extensions

Resource and location fields are empty objects to anchor arbitrary schemas. In turn, the specific schemas are identified by the locatorType and resourceType keys.

```
{
    "schemaVersion": 1,
    "resType": "link_with_notional_types",
    "subject": {
        "resourceType": "customer_profile",
        "resource": {
            "customerID": "CUST123",
            "name": "Alice Johnson",
            "customer_profile_data": {
                // Additional customer profile details
            }
        }
    },
    "predicate": {
        "resourceType": "financial_relationship",
        "resource": {
            "type": "has_account"
        }
    },
    "object": {
        "resourceType": "bank_account",
        "resource": {
            "accountNumber": "ACC456",
            "accountType": "Savings",
            "balance": 5000,
            "bank_account_data": {
                // Additional bank account details
            }
        }
    }
}
```

In this example, we see a UOR Statement describing a bank entity and customer account identity. The customer profile and bank account are both represented as UOR Elements. Here the predicate is also a UOR Element that describes the relationship between the customer profile and the bank account.


## Relational Expressions

What do a blog post, a person, a software application, and a CVE have in common? Well, if a person authored a blog post, and that person also authored a software application that is vulnerable to a CVE, then all of these things are related.

We use UOR Elements to express each of these objects and then we use UOR Statements to express the relationships between them. 

UOR Elements are Objects in the [Object Oriented Programming](https://en.wikipedia.org/wiki/Object-oriented_programming) (OOP) sense. They are discrete units of data or pointers to data that can be used to represent anything in an information system. UOR Elements also convey the type information of the data that they represent, also described as the '[semantic](https://en.wikipedia.org/wiki/Semantics)' context of the data describing what the object is and how to interact with it. This could include runtime instructions for executing a compiled binary element for example.


## Embedded Algorithms


UOR type definitions are referenced by the `resourceType` and `locatorType` fields in a UOR Element. These type definitions describe the data structure of their corresponding resource and location fields of UOR Elements. They are also used to identify the methods that can be used to interact with the UOR Element.

The methods on a `locatorType` are used to interact with the location field of a UOR Element. These methods define how a client would perform [CRUD operations](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) on a UOR Element's resource.

Similarly, the methods on a `resourceType` describe the resource class contained in the resource field of the UOR Element. These methods inform agents and clients on how to interact with the resource defined in the UOR Element.

For example, these methods can be fetched on a [WebAssembly](https://en.wikipedia.org/wiki/WebAssembly) (WASM) module to schedule and execute it correctly. This enables a client with no prior knowledge of such an element to resolve the element type and execute it directly.

This dynamic processing of UOR Elements describes UOR's approach to multi-modality. Leveraging WebAssembly in this way enables a UOR client to act upon any defined resource within an information system. Any other element type can be substituted, including pictures, videos, sensor data, LLM models, datasets, or even physical world object operations including robotic mechanisms, and more.


## Case-Studies


### 1. Software Supply Chain Security

**Scenario**: Managing and securing the components involved in software development, from code repositories to deployment pipelines.

**UOR Implementation**: 
- **UOR Elements**: Represent software components, code commits, libraries, and deployment tools.
- **UOR Statements**: Link elements to form a chain from source code to deployed application, including dependencies and version control.
- **Security Analysis**: Trace and audit software components throughout the supply chain, identifying vulnerabilities and ensuring compliance with security standards.

**Benefits**: Enhanced traceability, improved security posture, and the ability to quickly respond to vulnerabilities or compliance issues.


### 2. Healthcare Data Management

**Scenario**: Comprehensive management of patient data, from personal health records to treatment plans and real-time monitoring.

**UOR Implementation**:
- **UOR Elements**: Represent patient profiles, medical histories, medication details, and real-time health data.
- **UOR Statements**: Link patient data to their medical history, current treatments, and monitoring devices.
- **Personalized Care**: Facilitate the delivery of personalized healthcare recommendations and treatment adjustments based on real-time data.

**Benefits**: Improved patient care, efficient data management, and enhanced capability for predictive health analytics.


### 3. Information Technology Infrastructure Management

**Scenario**: Overseeing the components of an organization’s IT infrastructure, from hardware devices to software applications.

**UOR Implementation**:
- **UOR Elements**: Represent servers, network devices, applications, and user accounts.
- **UOR Statements**: Link elements to show relationships like application dependencies, network topology, and user access rights.
- **Optimization and Monitoring**: Streamline infrastructure management, monitor system health, and automate responses to issues.

**Benefits**: Increased operational efficiency, better resource utilization, and enhanced security.


### 4. Federated Machine Learning

**Scenario**: Collaborative machine learning involving multiple decentralized data sources without sharing the actual data.

**UOR Implementation**:
- **UOR Elements**: Represent local datasets, ML models, and learning parameters.
- **UOR Statements**: Link these elements to represent training cycles, model updates, and performance metrics.
- **Collaborative Learning**: Enable various parties to contribute to a shared ML model while maintaining data privacy.

**Benefits**: Preserved data privacy, combined learning from diverse sources, and improved model accuracy.


### 5. Social Network

**Scenario**: A dynamic social networking platform where users, posts, interactions, and groups are interconnected.

**UOR Implementation**:
- **UOR Elements**: Represent user profiles, posts, comments, and group entities.
- **UOR Statements**: Define relationships like friendships, post-authorship, and group memberships.
- **Dynamic Interactions**: Facilitate real-time updates, personalized feeds, and targeted content delivery.

**Benefits**: Enhanced user experience, effective content management, and improved network analysis.


### 6. Network Embedded Algorithms

**Scenario**: A network system where data processing and decision-making are embedded within the network transmissions.

**UOR Implementation**:
- **UOR Elements**: Represent data packets, network nodes, and routing decisions.
- **UOR Statements**: Link elements to represent data flow, node responsibilities, and algorithmic routing choices.
- **Smart Networking**: Implement dynamic routing algorithms and real-time data processing directly within the network infrastructure.

**Benefits**: Increased network efficiency, reduced latency, and enhanced capacity for handling complex network tasks.


## Implementing UOR

UOR is currently in the early stages of development. The UOR data model and core concepts have been defined, and a reference implementation is in progress. This means that for the time being, you can manually implement the UOR framework in your own projects, but no libraries or tooling have been published quite yet.

The roadmap includes UOR Registry service which will offer a GraphQL knowledge graph endpoint to publish and query servies based on a fork of the [OCI Distribution](https://github.com/opencontainers/distribution-spec). For the time being, I use a vector database and a document database to store UOR Statements.

The goal, in a UOR system is to build as much context as possible. This means that every artifact, asset, and event in an information system should be represented as a UOR Statement. To achieve this iteratively, first identify content that is already formatted as JSON and write ingesters to attach those arbitrary JSON objects to UOR Statements. 

Once the existing JSON formatted content is converted, we progress to converting non-JSON native content to UOR Statements. This requires defining a JSON Schema for the content and then writing an ingester that converts the content to UOR Statements.

Finally, use an LLM as a natural language interface to to UOR knowledge graph. The LLM response should be a UOR Statement that is written to the UOR formatted knowledge graph. This continues to build the context of the UOR knowledge graph and is the easiest way to author UOR formatted content. 

## Conclusion

I hope that you've enjoyed this introduction to UOR concepts and ways that UOR can be used. I'm excited to share more of UOR with you in subsequent posts. Please feel free to reach out to me with any questions or comments.