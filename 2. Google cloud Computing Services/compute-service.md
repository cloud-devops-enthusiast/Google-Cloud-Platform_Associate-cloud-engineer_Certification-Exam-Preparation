**Computing Components of Google Cloud Platform**
GCP is a whole suite of cloud computing services that include various services for which you can refer [this](https://github.com/cloud-devops-enthusiast/Google-Cloud-Platform_Associate-cloud-engineer_Certification-Exam-Preparation/blob/d1e4cd417315f3256f779ebe76382a7f986d6905/1.%20Overview%20of%20Google%20Cloud%20Platform/Overview.md)

* **Computing Resources**

    Public cloud services provides compute services with so many options to choose from. In this model of service the user has maximum control over all of the computing services. User's can choose which operating system to run, which packages are needed to be install and when to backup and perform the maintainence operations. This type of Computing service is referred as Infrastructure as a Service(IaaS). GCP's IaaS computing service is called Compute Engine and the PaaS offerings are App Engine and Cloud Functions.

* *Compute Engine*

    VM's are abstractions of physical servers. They are essentially programs that emulate physical servers and provide CPU, memory, storage and other services that you would find if you ran your favorite operating system on a server under your desk or in a data center. GCP uses a security hardend version of the KVM hypervisor. KVM stands for Kernel Virtual Machine and provide virtualization on Linux systems running on x86 hardware. These hypervisor's run on an operating system like Windows or Linux server. Hypervisor can run multiple operating system, referred to as Guest Operating System, while keeping the activities of each isolated from other guest operating system. Each instance of an executing guest operating system is a VM instance.
    Vm's come in range of pre-defined sizes, but you can also create customized configurations. There are many parameters which you can specify while the creation of VM:
    1. The Operating System
    2. Size of Persistent storage
    3. Adding GPUs Or Graphical Processing Units for compute-intensive operations
    4. Making the VM preemptible

    Making a VM preemptible, means you may be charged significantly less for the VM than normal (about 80% less), but your VM could be shut down at any time by Google. It will frequently be shut down if the preemptible VM has run for at least 24 hours. 

* *Kubernetes Engine*

    Kubernetes Engine is designed to allow users to easily run containerized applications on a cluster of servers. Containers are often compared to VM's because they are each used for isolating, computing, processing and resources. Containers take a different approach than VM's for isolating computing processes. A VM runs a guest operating system on a physical server. The physical server runs an operating system as well, along with hypervisor. Another approach to isolating computing resources is to use features of the host operating system to isolate processes and resources. Using this approach there is no need of the hypervisor; the host operating system maintains isolation. Instead of Hypervisor a container manager is used over here. A single container manager coordinates running on the server. No additional, or guest operating system run on top of the container manager. Container's make use of host operating system functionality, while the operating system and container manager ensure isolation between the running conatainers.
    Kubernetes monitors the health of servers in the cluster and automatically repair problems, such as failed servers. Kubernetes engine also supports autoscaling, so if the load on your application increases, Kubernetes engine will allocate additional resources.

* *App Engine*

    App Engine is GCP's compute PaaS offer. With App Engine, developers and application administrators don't need to concern themselves with configuring VM's or specifying Kubernetes cluster. Instead developers create applications in a popular programming languages such as Java, Go, Python or Node Js and deploy that code to a serverless application environment. App engine manages the underlying computing and network infrastructure. There is no need to configure VM's or harden network to protect your application. App engine is perfect fit for the web and mobile backend applications. App Engine is available in two types: Standard and Flexible.
    In standard environment, your applications run in a language-specific sandbox, so your applications is isolated from the underlying server's operating systemas well as from other applications running on that server.
    In flexible environment, you run Docker containers in the app engine environment. The flexible environment works well in cases where you have application code but also need libraries or other third-party software installed.

* *Cloud Functions*
    
    Google cloud functions is a lightweight computing option that is well suited to event-driven processing. Cloud functions runs code in response to an event. Cloud function runs code in response to an event, like a file being uploaded to a bucket, a message being sent to a queue, or a change in a Cloud Pub/Sub topic. Cloud functions are designed to be lightweight and easy to use. Cloud functions is often used to call other services such as third-party application programming interface (API's) or other GCP services, like a natural language translation service.

* *Storage Resources*
    
* *Cloud Storage*
    
    Cloud storage is a GCPs object storage system. Objects can be of any type of file or binary large object. Objects are then stored in the buckets, which are analogous to folders in a file system. One thing to remember that cloud storage is not a file system. Cloud storage is accessible from VMs (or any network device with appropriate privileges) and so complements file systems on persistent disks. Each stored object is uniquely identified by a unique URL which is a combination of the bucket name and object name. GCP users and other's can be granted permissions to read and write objects in a bucket. Cloud Storage is more useful for storing data that can be treated as single units of data. There are different classes of cloud storage.
    Regional Storage keeps copies of objects in a single google cloud region. Regional storage is optimized for storing data that is geographically distributed in a single geography. In regional storage there are multiple zones or deployment zones, where objects are stored.
    When you think about the high availability or durability, Multi-Region deployments are a good option. Multi-Region deployments are a way to store data in multiple regions. Multi-Region allows for faster access to data when users or applications are distributed across multiple geographic regions. 
    The cold storage class is low-cost archival stoarge designed for high durability and infrequent access. This class of storage is suitable for data that is accessed infrequently and is not expected to be accessed again for a long time.

* *Persistent Disk*
    
    Persistent disks are storage service that are attached to VM's in compute engine or kubernetes engine. Persistent disks provide block storage on solid-state drives (SSD's) and hard-disk drives (HDD's). SSDs are often used for low latency applications where persistent disk performance is important. SSD's cost more than HDD's, so applications that require high performance should use SSD's. GCP is that these disks suport multiple readers without a degradation in performance. This allows for multiple instances to read a single copy of data. Disks can also be resized as needed while in use without the need to restart your VM's. Persistent disks can be upto 64TB in size either using SSD's or HDD's.

* *Cloud Storage for Firebase*

    Mobile app developers may find Cloud Storage for firebase to be the best combination of cloud object storage and the ability to support uploads and downloads from mobile devices with sometimes unreliable network connection.

* *Cloud Filestore*

    Cloud filestore can provide high number of input-output operations per second (IOPS) as well as variable storage capacity requirements. Filestore implements the Network File System(NFS) protocol so system administrators can easily mount shared file systems on virtual servers.

* **Databases**
 
    GCP has number of database services, out of which some are relational databases and some are NoSQL databases. Some are serverless and others require users to manage clusters of servers. GCP's users must understand their application requirement before choosing a service and this specially important when choosing a database, which often provide core storage services in the application stack.
  
* *Cloud SQL*

    Cloud SQl is GCP's managed relational database service that allows user's to setup MySQL or PostgreSQL, databases on VMs without having to attend to database administration tasks, such as backing up databases or patching database software. Cloud SQL is available in multiple configurations:
    1. First-Generation MySQL, databases use MySQL 5.5 or 5.6 and can have upto 16GB of RAM and 500GB of data storage.
    2. Second-Generation MySQL, databases use MySQL 5.6 or 5.7 and can have upto 416GB of RAM and 10TB of data storage.
    3. PostgreSQL 9.6 runs on the second-generation platform and can be configured with upto 64 CPU's, 416GB of RAM and upto 10 TB of storage

* *Cloud Bigtable*
    
    Cloud bigtable is designed for petabyte-scale applications that can manage upto billions of rows and thousands of columns. It is based on a No SQL model known as a wide-column data model, and unlike cloud sql that supports relational databases. Bigtable is suited for applications that require low-latency write and read operations. It is designed to support millions of concurrent read and write operations per second. Bigtable integrates with other Google cloud services, such as Cloud Storage, Cloud Pub/Sub, Cloud Dataflow and Cloud Dataproc.

* *Cloud Spanner*
    
    Cloud spanner is Google's globally distributed relational database that combines the key benefits of relational databases, such as strong consistency and transactions, with the ability to scale horizontally like a NoSQL database. Spanner is a high availiability database with a 99.999 percent availability service level agreement(SLA), making it a good option for enterprise applications that demand scalable, highly available relational database service. Cloud spanner also has enterprise-grade security with encryption at rest and encryption in transit, along with identity-based access control.

* *Cloud Datastore*
    
    Cloud datastore is a NoSQL document database. This kind of database uses the concept of a document, or collection of key-value pairs, as the basic building block. Cloud datastore is accessed via a REST API that can be used from applications running in compute engine, kubernetes engine or app engine. This database will scale automatically based on the load. You can say, cloud datastore is a managed service, it takes care of replication, backups and other database administration tasks. Although it is a NoSQL database, cloud datastore supports transactions, indexes, and SQL-like queries. Cloud datastore is well suited to applications that demand high scalability and structured data and do not always need strong consistency when reading data.

* *Cloud Memorystore*
    
    Cloud memorystore is an in-memory cache service. Other databases offered by GCP are designed to store large volumes of data and support complex queries, but cloud memorystore is a managed redis service for caching frequently used data in memory. Cloud memorystore allows users to specify the size of the cache while leaving administrative tasks to google. GCP ensures high availability, patching and automatic failover so user's don't have to worry about data loss.

* *Cloud Firestore*
    
    Cloud firestore is another GCP managed NOSQL database service designed as a backend for highly scalable web and mobile applications. A distinguishing feature of cloud firestore is its client libraries that provide offline support, synchronization and other features for managing data across mobile devices, IOT devices and backend data stores. Cloud firestore includes a datastore mode, which enables applications written for datastore to work with cloud firebase as well.

**Networking Services**

    GCP provides a number of networking services designed to allow users to configure virtual networks within Google's global network infrastructure.

* *Virtual Private Cloud*

    While using public cloud, the infrastructure is shared over there with customers of that cloud service provider. As multiple organizations will use the same cloud infrastructure, where enterprises can logically isolate their cloud resources by creating a virtual private cloud(VPC). A diffrential factor of GCP is that a VPC can span the globe without relying on the public internet. Traffic from any server on a VPC can be securely routed through the google's global network to any other point on that network. The another advantage of the google network structure is that your backend servers can access google services, without the need of the public IP addresses of the servers. VPC's in the google cloud can be linked to an on-premise virtual priavte networks using internet protocol security(IPSec). Here firewalls can also be used to restrict access to resources within the VPC's.

* *Cloud Load Balancing*

    Cloud load balancing can distribute the workload within and across regions, adapt to failed or degraded servers, and autoscale your compute resources to accommodate changes in the workload. Cloud load balancing also supports internal load balancing, so no IP adresses needed to be exposed to the internet to get the advantages of load balancing. This service can load balance HTTP, HTTPS, TCP, and UDP traffic.

* *Cloud Armor*
  
    Cloud armor is a google network security service that builds on the global HTTP(s) load balancing service. Cloud armor features include the following:
    * Ability to manage accesses based on IP addresses, user groups, and user roles.
    * Predefined rules to counter cross-site scripting (XSS) attacks.
    * Ability to counter SQL injection attacks.
    * Ability to define rules at both level 3 (network) and level 7 (application) to protect your application from attacks.
    * Allows and restricts access based on the geographic location of the incoming traffic.
    Cloud armor is more like a firewall than a load balancer, for easy reference you can say cloud armor as a bullet-proof jacket.

* *Cloud CDN*
  
    Using Content delivery network (CDN's), users can access the request from anywhere where systems are distributed into the various regions of the world. CDN's enable low-latency response to these requests by caching content on a set of endpoints across the globe. Google currently has more than 90 CDN endpoints that are managed as a global resource, so there is no need to maintain region-specific configurations. News sites, for example, could use the cloud CDN service to ensure fast response to requests from any point of the world.

* *Cloud Interconnect*
    
    Cloud interconnect is a set of GCP services for connecting your existing networks to the google network. Cloud interconnect offers two types of connections: Interconnects and Peering. Interconnect with direct access to networks uses the address allocation for private internet standard to connect your devices in your VPC. A direct network connection is maintained between an on-premise or hosted data center and one of Google's connection facilities, which are located in north america, south america, europe, asia and australia. Alternatively if an organization cannot achive a direct interconnect with a google facility, it could use partner interconnect. Thi service depends on a third-party network provider to provide connectivity between the company's datacenter and a google facility.

* *Cloud DNS*

    Cloud DNS is a domain name service provided in GCP. Cloud DNS is a high availability, low-latency service for mapping from domain names, such as example.com to ip addresses, such as 74.120.28.18 .

* *Identity Management*

    GCP's cloud identity and access management (IAM) service enables customer to define fine-grained access controls on resources in the cloud. IAM uses the concepts of users, roles and privilages. The authenticated users can access resources and perform operations based on the privilages granted to that identity. Groups of related permissions can be bundled into roles. Roles are sets of permissions that can be assigned to an identity.

* *Development Tools*

    Cloud SDK is a command-line interface for managing GCP resources, including VM's, disk storage, network firewalls and virtually any other resource you might deploy in GCP. Google has also developed plug-ins to make it easy to work with popular development tools, some of them are Cloud tools for Visual Studio, App engine maven plugin and many more.

**Additional Components of GCP**

* *Management Tools*

    * Stackdriver: This is a service that collects metrics, logs and event data from applications and infrastructure and integrates the data so DevOps engineers can monitor, assess and diagnose operational problems.
    * Monitoring: This extends the capabilities of stackdriver by collecting performance data from GCP, AWS resources and application instrumentation, including popular open source systems like NGINX, Cassendra and Elasticsearch.
    * Logging: The service enables users to store and analyze and alert on log data from both GCP and AWS logo.
    * Error Reporting: This aggregates application crash information for display in a centralized interface.
    * Trace: This is a distributed tracing service that enables you to trace the path of a request through a network of services.
    * Debugger: This enables developers to inspect the state of executing code, inject commands and view call stack variables.
    * Profiler: This is used to collect CPU and memory utilization information across the cross hierarchy of an application.

**Specialized Services**

*Apigee (API+Gee) API Platform*

    The apigee API platform is a management service for GCP customers providing API access to their applications. The apigee platform allows developers to deploy, monitor and secure their API's. It also generate API proxies based on the Open API Specification.

*Data Analytics*

    GCP has a number of services designed for analyzing big data in batch and streaming modes. There are some important tools in the set of services: Bigquery, Cloud Dataflow, Cloud Dataproc and Cloud dataprep.

*AI and Machine Learning*

    Google is a leader in AI and machine learning, so there are so many services in GCP:
    * Cloud AutoML: This is a tool that allows developers without machine learning experience to develop ML models.
    * Cloud Machine Learning Engine: This is a platform for building and deploying scalable ML systems to production.
    * Cloud Natural Language Processing: This tool is for analyzing human languages and extracting information from them.
    * CLoud Vision: This is a service for analyzing images and extracting information from them.