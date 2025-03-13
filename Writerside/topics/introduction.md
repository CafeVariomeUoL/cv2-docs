# INTRODUCTION

## What is Cafe Variome?

Café Variome is a flexible web-based data discovery tool that any biomedical data owner can install to enable the “existence” rather than the “substance” of the data to be discovered.

## Why Cafe Variome?

Health data sharing often occurs in small-scale interactions between a limited number of individuals or institutions. Although this approach helps to ensure correct data usage while protecting patient confidentiality, the value of this data is never realised and runs counter to widespread data re-use.

Cafe Variome comes into action here by allowing data owners/custodians to retain control of their data while having approved data elements for discovery, either using a single instance or a federation of data sharing instances. Its powerful Query Interface using semantic similarity has the flexibility of making the researcher/user queries as simple or as complex as required.

Any user with an interest in finding data (for example, for cohort studies or checking the availability of specific data or matching rare disease patients), can use Cafe Variome to discover data.

Highlights of various features of the Cafe Variome Data Discovery Software are as follows:

## Federated Networks

The main advantage of data discovery using Cafe Variome is to find data from a Federation of Networks. By this, we mean the combination of data from not one but from multiple instances of Cafe Variome and making the data discoverable. Cafe Variome allows data administrators to create new networks for specific purposes as well as to request to join existing networks. This implies data providers (viz., laboratories, biobanks etc.,) can connect together in closed or semiclosed discovery networks. These could be all-to-all networks or a hub and spokes arrangement or a combination of these architectures.

<img alt="federated_networks.jpeg" title="Federated Networks" height="1000" src="federated_network.jpeg" width="1000"/>
## Fast, memory-efficient and secure health data discovery

Cafe Variome's powerful query engine, with its very little memory footprint, can execute queries at a high speed, enabling it to be hosted on small servers. In addition to data discovery, Cafe Variome can index large data files of millions of records in a memory efficient way using data pipelines.
## User-friendly Interface

Cafe Variome not only has an extremely robust query engine but also an intuitive user interface with an administrator dashboard to manage users, data sources, user access and networks, to name a few. Further advantages include making the query interface dynamic based on the data imported into the tool using pipelines.

<img alt="dashboard.png" height="1000" src="dashboard.png" title="Dashboard" width="1000"/>

For the technical folk: the administrator dashboard of Cafe Variome is created using CodeIgniter's MVC pattern with HTML, Bootstrap and JavaScript. Future developments include utilising React components and Material UI for dynamic discovery interfaces.

## Beacon Endpoints
Cafe Variome implements a **[Beacon v2.0 API](http://docs.genomebeacons.org/)**, which aims to make discovering genomic data easier. By uploading data to Cafe Variome using our data inserting tools, you will have the option to make it discoverable through Beacon.

We currently support all informational endpoints along with /individuals and /biosamples endpoints. A user interface for beacon queries is in works to further simplify genomic data discovery.
## Discovery of data based on semantic similarity

Use of ontology terms in patient data has become more prevalent. Café Variome can work with any health data ontology and can be configured to automatically detect ontology terms in raw data. This enables Café Variome to connect patients to nodes in ontologies. Similarity scores among ontology terms are calculated. Therefore, you can discover similar patients based on phenotypes, diseases, or medicine that they use.
