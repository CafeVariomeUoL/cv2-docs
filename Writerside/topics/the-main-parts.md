# The Main Parts

Cafe Variome, in its essence, has two main parts - the Discovery Interface (aka query interface) and the User Management Interface (aka the Admin Dashboard).

Cafe Variome exploits the natural synergy between these two parts and makes use of the best in both to bring out the perfect solution for discovery of data.

### Discovery Interface

At its simplest, Cafe Variome uses Elasticsearch and Neo4j to index user uploaded data and query it. The user can make the query as simple or as complicated as required. A generic query interface is provided with the initial installation of Cafe Variome. This interface can be tailored to your data using simple PHP, JS and HTML changes.

### User Management Interface

An Administrators Dashboard is made available to get an overview of all things data - # of sources, networks, users and network requests along with disk space usage and # of records per source (if present). This tool is very handy as it gives full control of the installation. 

>The Administrator Dashboard can only be accessed by users present in the Administrator control access group.

Admin Dashboard can be quickly used to identify any issues in the status of servers being used i.e., to verify whether services such as Elasticsearch, OIDC Provider and Neo4j are functioning properly.

<img height="1000" src="Admin_Dashboard_2.png" width="1000"/>

As seen above, this main page is an unrestricted access point to manage **sources, data management, networks, access groups, users, content management and system (installation) settings.** 
