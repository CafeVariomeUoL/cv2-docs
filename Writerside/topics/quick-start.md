# Quick Start

>Post-installation steps to setup Café Variome.


## Prerequisites
After successful installation of Cafe Variome, you will be shown the following info:

>Setup completed. Remember that you must remove the Install directory completely. 

Please remove the /Install directory that came with the software package as it is no longer needed.

You can now navigate to the base URL that was set during installation (ex: http://localhost/dummy_cv) in the choice of your browser. This takes you to the landing page of Cafe Variome, as shown below:

<img height="1000" src="cafevariome_home.png" width="1000"/>

On clicking Login, you will be shown SSO selection page, upon which you will be redirected to the KeyCloak login page, where you need to enter the Admin password credential that you have setup while installing.

<img height="1000" src="List_of_SSO_Servers.png" width="1000"/>
<img height="1000" src="Keycloack_Login_Page.png" width="1000"/>

`If you would want to impersonate a demo users to see how it works without being an admin, use the following credentials:`
    
    Username: demo@cafevariome.org
    
    Password: Dem0Us3r
After logging in, the following screen will be displayed alongside the top navigation:

<img height="1000" src="Home_screen.png" width="1000"/>

The following screenshot shows the Administrator Dashboard:

<img height="1000" src="Admin_Dashboard.png" width="1000"/>

>Make sure you have both Elasticsearch and Neo4J running as per the requirements.
>Otherwise, the following screen warns you of disabled ES and Neo4J. See Dashboard errors to resolve them.
>{style="note"}

<img height="1000" src="AdminDashboard_Disable_Neo4j_and_Elasricsearch.png" width="1000"/>

## Inital Configuration


* The following steps are required to configure Cafe Variome for Health Data Discovery:
* 
* Create/join a **Network** to get started with data discovery.
* 
* Setup **Discovery Groups** to provide access to your source to your chosen user(s). 
* 
* Create a data **Pipeline** to streamline your data upload process.
* 
* Create a **Data Source** to upload your data files. 
* 
* Upload/import your data using the **Data Files** file manager.
* 
* Generate **Data Indices** (Elasticsearch, Neo4j and User Interface).
* 
* Create Ontology-related mappings for your data (optional).
* 
* Add user(s) and source(s) to the current Network & Discovery Groups.