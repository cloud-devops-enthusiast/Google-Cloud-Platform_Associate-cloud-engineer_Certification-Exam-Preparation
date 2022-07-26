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
  
* *Cloud SQL*