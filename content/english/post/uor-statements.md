+++
title = "A Primer on UOR"
author = "Alex Flom"
tags = ["UOR"]
date = "2023-09-25"
draft = false
+++

## Preface

I've found it both helpful and distracting to discuss Universal Object Reference (UOR) in terms of metaphysics. It is important to understand the metaphysics of UOR in order to understand the implications of implementing UOR. However, it is not necessary to understand the metaphysics of UOR to understand how to use UOR. 

The implications of implementing UOR are profound, because it is based on the fundamental concepts of our reality. What you will find, is that UOR can theoretically be used to model the entire universe and reality itself. 

This perspective has been frustrating for technologists attempting to understand how to implement UOR in a concrete way. It could be said that the people willing to spend the time to understand the metaphysics of UOR are the people who are least likely to be able to implement it.

To that end, this primer describes UOR in terms of its concrete implementation. It is my hope that this primer will be useful to those who are interested in implementing UOR for their immediate needs as we continue to grok the full capabilities and characteristics of UOR through its metaphysics.

## Introduction

I'll continue lamenting my difficulty in attempting to explain UOR over the past two years. My favorite word to describe this difficulty is "confounding". What I've recently realized is that I'm trying to explain too much of UOR at once. While it is true that UOR is a new information system paradigm that enables a distributed, decentralized, federated, and extensible approach to resource management; with strong expressions of identity and new approaches to access control. I think that it is best to start at what I see as the basics of UOR and then build up from there.

For this primer, I'll focus on a subset of the entirety of UOR. I think that this particular subset of UOR is the foundation of the entire concept. This includes attempting to explain the UOR data model as the basis of a universal language. Once I've attempted to explain UOR in these terms, I'll attempt to discuss UOR in the terms of notional implementations, and then I'll wrap up with some information on how to get started with leveraging UOR for your own immediate needs. 

I've also provided this specific context to assist the reader with understanding what a UOR system looks like, and how it can be iteratively achieved. 

## The UOR Data Model

### UOR Element
```
{
    "locatorType": "string (optional)",
    "resourceType": "string",
    "location": "object (optional)",
    "resource": "object"
}
```
The UOR Element is the foundational building block within the UOR framework. It represents a discrete unit of data or resource within the system. The resourceType is a key attribute that identifies the type of the resource, akin to a class in object-oriented programming.

The resource field contains the actual data or information of the element. Optionally, locatorType can be used to specify how to locate or access the resource, and location provides specific details for accessing it, if needed.

### UOR Statement
```
{
    "schemaVersion": "integer",
    "resType": "string",
    "subject": "UOR Element",
    "predicate": "UOR Element",
    "object": "UOR Element"
}
```
The UOR Statement is a semantic triple that links UOR Elements together, establishing relationships and context within the UOR system. It consists of a subject, predicate, and object, each of which is a UOR Element. The schemaVersion and resType provide metadata about the statement. This structure enables the representation of complex relationships and interactions between different data elements.

### UOR Element Extensions
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
As mentioned above, the resource and location fields are empty objects that are intended to anchor arbitrary schemas. The arbitrary schemas are identified by the locatorType and resourceType fields. 

In the example above, we see a UOR Statement that describes a relationship between a customer profile and a bank account. The customer profile and bank account are both represented as UOR Elements. The predicate is also a UOR Element that describes the relationship between the customer profile and the bank account.

## A Universal Language

What do a blog post, a person, a software application, and a CVE have in common? Well, if a person authored a blog post, and that person also authored a software application that is vulnerable to a CVE, then all of these things are related.

We use UOR Elements to express each of these objects and then we use UOR Statements to express the relationships between them. 

UOR Elements are Objects in the Object Oriented Programming sense. They are discrete units of data or pointers to data that can be used to represent anything in a distributed system. UOR Elements also convey the type information of the data that they represent. This includes the runtime instructions for interacting with the UOR Element.


## Embedded Algorithms

UOR type definitions are referenced by the resourceType and locatorType fields of UOR Elements. These type definitions are used to describe the data structure of their corresponding resource and location fields of UOR Elements. They are also used to identify the methods that can be used to interact with the UOR Element.

The methods on a locatorType are used to interact with the location field of a UOR Element. These methods define how a client would perform CRUD (Create, Read, Update, Delete) operations on a UOR Element's resource.

And similarly; the methods on a resourceType are used to interact with the resource field of a UOR Element. These methods define how a client would interact with resource defined in the UOR Element.

These methods are fetched as WebAssembly modules and executed by the client. This means that the client does not need to have any prior knowledge of how to interact with a UOR Element until it has resolved the UOR Element's type definition.

This dynamic processing of UOR Elements explains UOR's approach to multi-modality. Leveraging WebAssembly in this way enables a UOR client to act upon any defined resource within an information system. 

## Case-Studies

#### 1. Software Supply Chain Security

**Scenario**: Managing and securing the components involved in software development, from code repositories to deployment pipelines.

**UOR Implementation**: 
- **UOR Elements**: Represent software components, code commits, libraries, and deployment tools.
- **UOR Statements**: Link elements to form a chain from source code to deployed application, including dependencies and version control.
- **Security Analysis**: Trace and audit software components throughout the supply chain, identifying vulnerabilities and ensuring compliance with security standards.

**Benefits**: Enhanced traceability, improved security posture, and the ability to quickly respond to vulnerabilities or compliance issues.

#### 2. Healthcare Data Management

**Scenario**: Comprehensive management of patient data, from personal health records to treatment plans and real-time monitoring.

**UOR Implementation**:
- **UOR Elements**: Represent patient profiles, medical histories, medication details, and real-time health data.
- **UOR Statements**: Link patient data to their medical history, current treatments, and monitoring devices.
- **Personalized Care**: Facilitate the delivery of personalized healthcare recommendations and treatment adjustments based on real-time data.

**Benefits**: Improved patient care, efficient data management, and enhanced capability for predictive health analytics.

#### 3. Information System Infrastructure Management

**Scenario**: Overseeing the components of an organization’s IT infrastructure, from hardware devices to software applications.

**UOR Implementation**:
- **UOR Elements**: Represent servers, network devices, applications, and user accounts.
- **UOR Statements**: Link elements to show relationships like application dependencies, network topology, and user access rights.
- **Optimization and Monitoring**: Streamline infrastructure management, monitor system health, and automate responses to issues.

**Benefits**: Increased operational efficiency, better resource utilization, and enhanced security.

#### 4. Federated Machine Learning

**Scenario**: Collaborative machine learning involving multiple decentralized data sources without sharing the actual data.

**UOR Implementation**:
- **UOR Elements**: Represent local datasets, ML models, and learning parameters.
- **UOR Statements**: Link these elements to represent training cycles, model updates, and performance metrics.
- **Collaborative Learning**: Enable various parties to contribute to a shared ML model while maintaining data privacy.

**Benefits**: Preserved data privacy, combined learning from diverse sources, and improved model accuracy.

#### 5. Social Network

**Scenario**: A dynamic social networking platform where users, posts, interactions, and groups are interconnected.

**UOR Implementation**:
- **UOR Elements**: Represent user profiles, posts, comments, and group entities.
- **UOR Statements**: Define relationships like friendships, post-authorship, and group memberships.
- **Dynamic Interactions**: Facilitate real-time updates, personalized feeds, and targeted content delivery.

**Benefits**: Enhanced user experience, effective content management, and improved network analysis.

#### 6. Network Embedded Algorithms

**Scenario**: A network system where data processing and decision-making are embedded within the network transmissions.

**UOR Implementation**:
- **UOR Elements**: Represent data packets, network nodes, and routing decisions.
- **UOR Statements**: Link elements to represent data flow, node responsibilities, and algorithmic routing choices.
- **Smart Networking**: Implement dynamic routing algorithms and real-time data processing directly within the network infrastructure.

**Benefits**: Increased network efficiency, reduced latency, and enhanced capacity for handling complex network tasks.

## Implementing UOR

UOR is currently in the early stages of development. The UOR data model and core concepts have been defined, and a reference implementation is in progress. This means that for the time being, you will be able to leverage UOR format in your own projects, but no UOR tooling has been published yet.

Eventually the UOR Registry will host a GraphQL endpoint that will enable decentralized UOR knowledge graph queries. For the time being, I use a vector database and a document database to store UOR Statements. 

The goal, if there is such a thing, in a UOR system is to build as much context as possible. This means that every event in an information system should be represented as a UOR Statement. To achieve this iteratively, first identify content that is already formatted as JSON and write ingesters that attach those arbitrary JSON objects to UOR Statements. 

Once the existing JSON formatted content is converted, then start converting non-JSON native content to UOR Statements. This requires defining a JSON Schema for the content and then writing an ingester that converts the content to UOR Statements.

Use an LLM to interact with the UOR knowledge graph. The LLM (Large Language Model) response should be a UOR Statement that is written to the UOR formatted knowledge graph. This continues to build the context of the UOR knowledge graph and is the easiest way to author UOR formatted content. 

## Conclusion

I hope that you've enjoyed this introduction to UOR concepts and ways that UOR can be used. I'm excited to share more of UOR with you in subsequent posts. Please feel free to reach out to me with any questions or comments.