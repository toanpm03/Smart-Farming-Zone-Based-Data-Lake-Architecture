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
Fig 1. Data Flow and Data Organization (Giebler, 2021)
We decided to use the hybrid processing architecture BRAID as the data flow concept for some reasons:

- Data ingested as a stream are both forwarded to a persistent storage and to a stream processing engine. It allows to use results from batch processing in stream processing

- Results can be stored persistently and are available for later use. Data ingested in batches are stored in the persistent storage and processed in batches.
#### Step 3: Design Data Organization

Step 4: Design Data Storage

Step 5: Design Infrastructure

Step 6: Design Data Modeling

Step 7: Design Metadata as Enabler

Step 8: Design Data Processes

Step 9: Design Metadata as a Feature
