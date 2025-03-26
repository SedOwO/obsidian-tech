- [[#K8s namespace]]
- 
### K8s namespace
Kubernetes namespaces are a method by which a single cluster used by an organization can be divided and categorized into multiple sub-clusters and managed individually. Each of these clusters can function as individual modules where users across various modules can interact and share information as necessary.

### Load balancing


### Service
The Service API lets you provide a stable (long lived) IP address or hostname for a service implemented by one or more backend pods, where the individual pods making up the service can change over time.
1. [[#Load balancing]]
2. [[#Service Discovery]]
3. [[#Exposing IP addresses|Expose to external world]]

### Load balancing
A **Kubernetes load balancer** service is a component that distributes network traffic across multiple instances of an application running in a [[K8s]] cluster. It acts as a traffic manager, ensuring that incoming requests are evenly distributed among the available instances to optimize performance and prevent overload on any single instance, providing high availability and scalability.

### Service Discovery
_Service discovery_ is a mechanism by which services discover each other dynamically without the need for hard coding IP addresses or endpoint configuration. 
Labels and selectors are used here.


### Exposing IP addresses
The following are the 3 different ways of exposing the IP addresses:
1. Load balancer: any one on the internet can access this IP.
2. Node port: only people of the same organization can access (eg. EC2 instance, VPC, Nodes).
3. Cluster IP: only accessible in the same cluster.

