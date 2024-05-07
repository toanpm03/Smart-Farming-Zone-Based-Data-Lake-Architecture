## Smart Farming: Zone-based Data Lake Architecture
### Objective
This paper aims to propose a dedicated data lake functional architecture and extend it to a technical
architecture to initiate a smart crop farming data-driven strategy. The paper provides a review of how big data technologies
offer multiple advantages for decision making and enabling prediction use cases. It also highlights
different big data technologies and their use.
### Methodology
The project follows nine steps:
#### Step 1: Identify Scenario

- Diverse in structure (e.g., structured crop management systems data, semi-structured sensor data, and unstructured images from satellites)

- Handle both real time stream processing for operational adjustments on the spot and batch processing approach

- Utilized data through a variety of advanced analytical techniques and operational processes that significantly enhance agricultural efficiency
#### Step 2: Design Data Flow 

![image](https://github.com/toanpm03/Smart-Farming-Zone-Based-Data-Lake-Architecture/assets/131639954/d0a1a717-fd79-4279-9e82-b6fbd3e5e34c)

Fig 1. A Zone Reference Model and its Data Flow (Giebler et al., 2021)

We decided to use the hybrid processing architecture BRAID as the data flow concept for some reasons:

- Data ingested as a stream are both forwarded to a persistent storage and to a stream processing engine. It allows to use results from batch processing in stream processing

- Results can be stored persistently and are available for later use. Data ingested in batches are stored in the persistent storage and processed in batches
#### Step 3: Design Data Organization

![image](https://github.com/toanpm03/Smart-Farming-Zone-Based-Data-Lake-Architecture/assets/131639954/af8fea29-e42e-4094-ad36-aa5bbc1b953e)

Fig 2. The decision process for choosing an appropriate data organization concept (Giebler et al., 2021)

We decided to use a data zone architecture as specified in Fig. 2  and zone reference model (Giebler et al., 2020) as it provides fitting zones for the envisioned use cases for both batch and stream processing (Fig. 1). It also contains concepts for both data quality and data security, e.g., the protected part, or varying access rights for different zones.
#### Step 4: Design Data Storage
The data storage concept for this data lake comprises multiple different storage systems (e.g., sensor data are stored in time series databases that support effective time-oriented queries while unstructured data are stored in a distributed file system).
#### Step 5: Design Infrastructure
We chose various tools for storage and processing from the Hadoop ecosystem, e.g., HDFS and Apache Spark. Other systems, RDBMS and NoSQL databases alike, are added to this core to support more data characteristics. This infrastructure concept is depicted in Fig. 3
#### Step 6: Design Data Modeling
While data in the Landing Zone and Raw Zone are kept in their original format, Data Vault is used for structured data in the Harmonized Zone and the Distilled Zone. Data Vault allows flexible, use-case independent, and scalable modeling of data in data lakes. In addition, link-based integration is used to link structured and semi-structured data to unstructured data. The Harmonized Zone uses Raw Vault, while the Distilled Zone is modeled in Business Vault to include business logic. Finally, data in the Delivery Zone and the Explorative Zone are modeled according to specific needs
#### Step 7: Design Metadata as Enabler
Metadata may be structured or semi-structured and are ingested in the same way as the data it belongs to (e.g., as data stream for streaming data). The data flow concept remains the same for both metadata and data. In terms of data organization, metadata remain continuous and run through all the data lake zones. Because of highly connected metadata, it is stored using Neo4J, a graph database management system. The metadata are modeled using Apache Atlas. Apache Atlas is well integrated into the other components of the Hadoop ecosystem that extract and govern metadata systematically across the data lake.

#### Step 8: Design Data Processes
- Data lifecycle processes involved the data cycle from creation, storage, enhancement and disposal. During each stage of its lifecycle, the metadata that is relevant is captured and stored together with the data. 

- Data pipelining processes begin from the bulk ingestion of raw data into the Landing Zone that serves as the temporary storage for the data before further processing. ETL processes are executed to transfer the data from the Landing Zone to other zones.

- The concepts of data security, privacy, and quality are effectively applied in data lifecycle processing (e.g. access control and change management) and data pipelining processes (e.g. anonymization techniques).
#### Step 9: Design Metadata as a Feature
In the scenario, we use three concepts that provide features in addition to those of metadata as enabler, namely a data catalog to allow access of data.

### Proposed Model
![image](https://github.com/toanpm03/Smart-Farming-Zone-Based-Data-Lake-Architecture/assets/131639954/2b7efb16-6071-46d7-b027-9f897b2b4482)
Fig 3. Technical Architecture
