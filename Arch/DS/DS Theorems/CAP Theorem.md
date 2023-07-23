#devOps #architecture #database

A distributed system can only deliver **two of the three** desired characteristics:
- **Consistency**
- **Availability**
- **Partition tolerance**

### Consistency
- [ ] All clients see the **same data at the same time.**
- [ ] Data written to one node must be instantly forwarded or replicated to all other nodes in the system before write is deemed successful.

### Availability
- [ ] Any client makig a request for data **gets a response** even if one or more nodes are down.

### Partition Tolerance
- [ ] Partition is a communcication break within a distributed system.
- [ ] Partition tolerance means cluster must continue to **work despite any number of communication breakdowns** between nodes in the system

### NoSQL DB
- [ ] Ideal for distributed network applications
- [ ] horizontally scalable and distributed by design 
	- [ ] SQL db(relational) are vertically scalable
- [ ] can rapidly scale across growing network consisting of multiple inter connected nodes

### Types of NoSQL databases

#### CP
- [ ] When a partition occurs between any two nodes, the system has to shut down the non-consistent node (i.e., make it unavailable) until the partition is resolved.
- [ ] MongoDB
	- [ ] stores data as binary JSON (**BSON**)
	- [ ] ideal for **big data** and eral-time application running at multiple locations
	- [ ] Consistency
		- [ ] Primary (single master) and secondary nodes 
	- [ ] Partition
		- [ ] If primary went down, one of secondary becomes primary
	- [ ] Availability
		- [ ] Between primary going down and secondary becoming new primary, there will be unavailability

#### AP
- [ ] When a partition occurs, all nodes remain available but those at the wrong end of a partition might return an older version of data than others
- [ ] Apache Cansandra
	- [ ] Wide-column database that lets you store data on a distrubuted network.
	- [ ] Masterless architecture
	- [ ] Availability
		- [ ] All nodes are independent. so will always be available.
	- [ ] Partition
		- [ ] When a node goes down and new one comes up, It will sync with others
	- [ ] Consistency
		- [ ] Nodes won't sync with each other that frequently so no instant consistency.

#### CA 
- [ ] A CA database delivers consistency and availability across all nodes. It can’t do this if there is a partition between any two nodes in the system, however, and therefore **can’t deliver fault tolerance.**
- [ ] in a distributed system, partitions can’t be avoided. So for all practical purposes, a CA distributed database can’t exist.
- [ ] if you need one. Many **relational** databases, such as PostgreSQL, deliver consistency and availability and can be deployed to multiple nodes using replication.

### In Microservices
- [ ] if the ability to quickly iterate the data model and scale horizontally is essential to the application, but can tolerate eventual (as opposed to strict) consistency
	- [ ] AP database -> Cassandra
- [ ] if the application depends heavily on data consistency—as in an eCommerce application or a payment service
	- [ ] relational databse -> PostgreSQL (P doesn't apply for single node)
