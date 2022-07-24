Google Cloud Platform (GCP) is a public cloud service that offers services and technologies to make world a better place.

Public cloud providers offer services that fall into four broad categories:
* Compute Resources
* Storage
* Networking
* Specialized or Managed services such as Machine learning services, cloud functions, etc.

**Compute Resources**
Infrastructure as a Service(IAAS)
* *Virual Machines*
    Virtual machines are a basic unit which provides computing resources and a great starting point for experimenting with the cloud.GCP offer's a variety of pre-configured VM's with different configurations of varying number of vCPU's and amounts of memory. You can also create custom configuration if the pre-configured doesn't meet your requirements. As you create and allocation of VM happens and once you get full access to the VM so you can configure the file system to which you can add persistent storage, patching the operating system or you can install additional packages. You can get the accesses of your VM where you can choose who can have accesses to the same. You can also create multiple VM's which can run independently on different operatings system or applications. GCP provides services such as load balancer's that provide a single access point to a distributer back-end. This also helps when you need to have high availability for your application. If any of the VM's in a cluster fails, the workload can be directed to any other VM in the cluster. You can also features like auto-scaling which can add or remove VM's from the cluster based on the workload.
    
* *Managed Kubernetes Cluster*
    GCP gives you all the tools you need to create and manage cluster's of server's. As many user's don't want to focus on the server's while keeping them up and running, so many cloud provider's are moving to the managed cluster's as per the user requirement's. These managed cluster's make use of container's. A *Container* is a lightweight VM that isolates processes running in another comtainer on the same server. You can also specify the autoscaling parameter to optimize the number of conatiner running. When you go for a managed cluster service the health of the container's is constantly being observed for you. If anything happens and container fails by itself the cluster management software detects the same and starts the another container. Container's are the good option when you need to run applications that depend on multiple micro-services running in your environment. These all services are being deployed through the container's and the cluster management service that takes care of monitoring, networking, and some security management tasks.

* *Serverless Computing*
    As the name suggests it's serverless of processing data or providing the compute power without thinking about the backend servers. This enables you to focus on the code and worrying much about the backend. Serverless computing is an approach that allows developers and application administrators to run their code in a cloud computing environment that does not require setting up VM's or kubernetes cluster. Google cloud platform has two serverless computing options named: App Engine and Cloud Functions.

**Storage**
Public cloud offers some storage services that are useful for many types of requirements. These types include:
* *Object Storage*
    Object storage is a system that manages the use of storage in terms of objects or blobs. Usually these objects are files, but it is important to note that the files are not stored in a conventional file system. Objects which can be files are grouped into buckets. Each object is individually addressable, usually by a URL. Object storage is not limited by the size of disks or solid-state drives (SSD's) attached to the server which can be uploaded without concern for the amount of space available on a disk. A big advantage of object storage is that it is *Serverless*. In GCP the object storage service is called as Cloud Storage which can be accessed from the server running in GCP as well as from other devices with an internet access. Access control can be applied at the object level.

* *File Storage*
    File storage service provides a hierarchical storage system for files. File systems storage provides network shared file systems. GCP has file storage service named Google Filestore which is based on the Network File System (NFS) storage system. File system is suitable for applications that require operating system like file access to the files. The file storage system decouples the file system from the specific VM's.

* *Block Storage*
    Block storage uses a fixed-size data structure called a block to organize the data. Block storage is commonly used in ephemeral and persistent disks attached to VM's. With a block storage system, you can install file systems on top of the block storage, or you can run applications that access blocks directly. Block storage can be either persistent or ephemeral. A persistent disk continues to exist and store data even if it is detached from a virtual server or the virtual server to which it is attached shuts down. *Ephemeral disks* exist and store data only as long as the VM is running. Exphemeral disks store operating system files and other files and the data that are deleted when VM is shutting down. *Persistent disks* are used when you want data to exist on a block storage device independent of a VM. These disks are good options when you want data to exist on a block storage device independent of a VM. Object storage also keeps data independent of the lifecycle of a VM, but it does not support any other operating system- or file system-level access; you have to use higher-level protocols like HTTP to access objects. Object storage can store large volumes of data that are copied to persistent disk when needed.

* *Caches*
    Caches are in-memory data stores that maintain fast access to data. The time it takes to retrive data is called latency. The latency of an in-memory stores is designed to be submillisecond. Caches are quite helpful when you need to keep read latency to a minimum in your application. Memory is more expensive than SSD or hard disk storage (HDD) storage. Caches are volatile; you lose the data stored in the cache when power is lost or the operating system is rebooted. You can store data in a cache for fast access, but it should never be used as the only data store keeping the data. Caches can get out of synchronization with the system of truth.

* *Networking*
    Each network-accessible device or service in your environment will need an IP address. GCP allocated IAAS services have both internal and external IP addresses. Internal addresses are accessible only to services in your internal GCP network. Your internal GCP network is defined as a virtual private cloud(VPC). External addresses are accessible from the internet. Static IP addresses are assigned to a device for extended periods of time. Ephemeral external IP addresses are attached to VM's and released when the VM is stopped. You also need to specify the firewall rules to control accesses over the subnetworks and VM's in your VPC. This firewall rule can be configured to limit inbound and outbound traffic to the IP address of the application server or load balancer in front of the application cluster. You may need to share data and network access between an on-premise data center and your VPC. You can do this using one of the several types of peering, which is the general term for linking distinct networks.

* *Specialized Services*
    There are some special services that can be provided by the public cloud provider as a service offering which can be used as a building block of applications or as part of workflow for processing the data. There are some examples of the same:
   * There are serverless or managed service
   * Specific function service like translation services
   * Application programming service (API) to access the functionality of the service.
   * Auto ML, a machine learning service
   * Cloud Natural Language, a service for analyzing service
   * Cloud Vision, for analyzing service
   * Cloud Inference API, a service for computing correlations over time-series data.

* Cloud Computing vs Data Center Computing
    The most basic difference between both them is that you rent resources as per your need while in data center or on-prem environment involves the owning the resources. This can be easily understood by the CapEx(Capital Expenditure) and OpEx(Operational Expenditure)model where the capex is about the investment for buying the resources while opex is about the operational cost which is spent over any resource in a desired amount of time. There are differences like disaster recovery and many more. 

* *Pay-as-you-go-for-what-you-use Model*
    This model is all about the OpEx which is mentioned in the above one paragraph where you just need to pay for the resources which you use in that period of time.

* *Elastic Resource Allocation*
    This is about the ease of provisioning or de-provisioning of the resources you need for your work on in any moment of time. You can scale as much you want based on your resources and scale down on similar basis.