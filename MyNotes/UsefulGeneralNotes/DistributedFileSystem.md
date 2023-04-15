**Tag Obsidian:** #BigData #database 

A distributed file system (**DFS**) is a file system that spans across multiple file servers or multiple locations, such as file servers that are situated in different physical places. Files are accessible just as if they were stored locally, from any device and from anywhere on the network.  
A DFS makes it convenient to share information and files among users on a network in a controlled and authorized way.  

The main reason to choose a DFS is to provide access to the same data from multiple locations. In today’s increasingly hybrid cloud world, whenever you need access to the same data from the data center, to the edge, to the cloud, you would want to use a DFS.  

A DFS give some *important* features:
- **Transparent local access**: Data to be accessed as if it’s local to the user for high performance.
- **Location independence**: No need for users to know where file data physically resides.
- **Scale-out**: The ability to scale out massively by adding more machines. DFS systems can scale to exceedingly large clusters with thousands of servers.
- **Fault Tolerance**: A fault-tolerant DFS is able to handle such failures by spreading data across multiple machines.

A distributed file system works as follows:

-   **Distribution**: First, a DFS distributes datasets across multiple clusters or nodes. Each node provides its own computing power, which enables a DFS to process the datasets in parallel.
-   **Replication**: A DFS will also replicate datasets onto different clusters by copying the same pieces of information into multiple clusters. This helps the distributed file system to achieve fault tolerance—to recover the data in case of a node or cluster failure—as well as high concurrency, which enables the same piece of data to be processed at the same time.
---
