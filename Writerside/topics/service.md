# Cafe Variome Service

### aka The Daemon Process

This is a lightweight program, written in PHP 8.0,  that runs in the background. 

>You do not have to do anything; it is automatically invoked after successful installation of Cafe Variome. 

<img height="1000" src="DaemonProcess.png" width="1000"/>

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