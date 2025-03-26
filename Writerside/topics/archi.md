# Architecture
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

<img height="1000" src="fullarchitecture.png" width="1000"/>

All of these parts are individually described in further sections.