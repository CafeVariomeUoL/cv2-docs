# Data Owners

## Information for the data custodians

Data drives discovery. As a data owner, you might be in possession of some data that you would like to share and make discoverable (woohoo, for the greater good!). The first step of doing this is to make sure that the data is being deposited somewhere secure. Cafe Variome comes in multiple flavours, where you can choose the destination to store your data or automate it using our tool.

In preparation for this, the custodian needs to decide on the levels of data required for discovery (ex: record-level or resource-level discovery), and on whether authentication and authorisation are required for the user to be able to gain access to data (or should the data be publicly accessible etc.,)

<img alt="Information for Data Custodians" height="1000" src="inforamation for data custodians.png" title="Information for Data Custodians" width="1000"/>
## Cafe Variome provides this functionality by allowing data owners/custodians to retain control of their data while having approved data elements for discovery, either using a single instance or a federation of data-sharing instances. 

The available data can be uploaded into Cafe Variome using Import Pipelines, which will import different formats of data (.csv, .xls, .xslx, phenopacket and .json files) into an EAV model based on a standard template. The owner may also choose to create a data pipeline specific to importing their data using the admin interface. This uploaded data will be imported into the EAV datastore and then be indexed using Elasticdearch or Neo4J (or Triple Stores). A data connector can also be made specific to your own database. 