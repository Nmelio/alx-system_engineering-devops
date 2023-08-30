DESCRIPTION:
Three server web infrastructure that hosts the website www.foobar.com

EXPLANATION OF SOME SPECIFICS ABOUT THIS INFRASTRUCTURE:
For every additional element, why you are adding it?
A second set of servers was added to split the traffic on the site thus increasing efficiency, and also to prevent the server for being a SPOF. The Load balancer was added to balance the traffic in and out of each server.
What distribution algorithm your load balancer is configured with and how it works?
It is configured with the Weighted Scheduling Algorithm. Work is assigned to the server according to the weight assigned to the server. For different types of the server in the group different weights are assigned thus the load gets distributed.
Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both?
The HAProxy load-balancer is enabling an Active-Active setup rather than an Active-Passive setup. In an Active-Active setup, deploy two or more active system instances and can be used to improve scalability as well as provide high availability. In active-active deployments, all instances handle requests concurrently. On the other hand, in an Active-Passive setup, deploy an active instance that handles requests and a passive instance that is on standby. In addition, a heartbeat mechanism is set up between these two instances. This mechanism is provided and managed through operating system vendor-specific clusterware.
How a database Primary-Replica (Master-Slave) cluster works?
There are two types of nodes in Master-Slave replication: Master and Slave. The single master (leader) node works as the primary database, while one or more slave (follower) nodes maintain copies of the Master’s data. The master node is responsible for handling write queries while slave nodes are responsible for handling read queries. Note: If required, the master node can also perform read queries. Whenever a write operation is performed on the master node, it is replicated to all the slave nodes to keep the data consistent across the entire system. 
What is the difference between the Primary node and the Replica node in regard to the application?
The Primary node is responsible for all the write operations the site needs whilst the Replica node is capable of processing read operations.

ISSUES WITH THIS INFRASTRUCTURE:
Where are SPOF: 
The load balance is a point of failure, because there is no alternative.
Security issues (no firewall, no HTTPS)?
The HTTP requests/responses are not encrypted using SSL certificate, so messages can be intercepted. Secondly the lack of firewall means that there could be intrusions into the server and client, and either could also send malicious information to the other
No monitoring?
Any of the servers could be down without being noticed.
