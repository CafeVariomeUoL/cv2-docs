# The Framework

As previously mentioned, Cafe Variome primarily consists of two main parts. To bring both of them together, there are a lot of moving parts working in union. These are briefly described in the following sections using an abstract architectural diagram. 

## Architecture
The following diagram brings together various layers and parts of Cafe Variome:

<img alt="Abstract Architecture" height="1000" src="AbstractArchitecture.png" title="Abstract Architecture" width="1000"/>


Cafe Variome functions using 6 basic layers:

* User-facing visual Interface using the CodeIgniter Framework
* 
* Query Interface using Elasticsearch and Neo4j services
* 
* Authentication Layer with Keycloak and other OIDC Providers
* 
* Data Pipeline Layer connecting to the database and manipulating it
* 
* Input-Output Layer for data file management 
* 
* Network Interface Layer for running the Daemon Service and for federated data discovery

An in-depth view of the above architecture is as follows:

<img alt="Full Architecture" height="1000" src="fullarchitecture.avif" width="1000" title="Full Architecture"/>

All of these parts are individually described in further sections.

## Cafe Variome Service

### aka The Daemon Process

This is a lightweight program, written in PHP 8.0,  that runs in the background. 

>You do not have to do anything; it is automatically invoked after successful installation of Cafe Variome. 

<img height="1000" src="DaemonProcess.avif" title="Daemon Process" width="1000"/>

It provides communication between spawned processes and the user interface using sockets and server-side events (SSE).

Its main purpose is to show a task's live progress.

Daemon currently supports:

* File Processing 
* 
* Elasticsearch indexing
* 
* Neo4j indexing
* 
* User Interface index creation