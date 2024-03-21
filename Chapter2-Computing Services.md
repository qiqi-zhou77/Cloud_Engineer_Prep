## Computing Components
IaaS: Users choose the operating system to run, which packages to install, and when to back up and perform other maintenance operations.
PaaS: prividing runtime env to execute applications without the need to manage underlying servers, networks and storage systems.

**Compute Engines** IaaS
- Service allowing users to create VMs,abstractions of physical servers, programs that emilate physical servers and provide CPU, memory, storage and other services.
- Parameter specification: Operating System, Size of persistent storage, GPU, VM preemptible
- Physical server -> Host Operating Sys -> Hypervisor -> Multiple Guest OS


**Kubernetes Engine**
- Both contiainers and VMs are used for isolating computing processing and resources
 VM runs a guest operating sys on physical server, another approach is to use features of the host operating sys to isolate processes and resources, no need to have hypervisor. 
- Physical Server -> Host Operating Sys -> Container Manager -> Multiple Containers
- container manager coordinate the containers running on the server/ ensure osolation between the running containers. containers make use of the host operating sys functionality,


**App Engine** PaaS
App Engine manages the underlying computing and network infrastructure. there is no need to congigure VMs to harden networks to protect your application.

App Engine is well suited for web and mobile back end applications

- Standard Env: run application in a language specific sandbox, application do not need operating sys packgaes or other compiled software to be installed

- Flexible Env: run containerized applications in App Engine env, the applciation need libraries or other third party software installed.


**Cloud Run**
Service to run stateless containers (Stateless containers refer to containerized applications that do not rely on persistent state or data stored within the container itself. In other words, they are designed to be stateless, meaning they do not retain any information or data between runs. Instead, they rely on external data sources or services for any required state or data)

**Cloud Functions**
- Lightweight computing option that is well suited to event-driven processing
- Runs code in response to an event, like a file being uploaded to cloud storage...
- Often used to call other services
- Code running should be short running


## Storage Component of Google Cloud

### Storage Resources

**Cloud Storage**
- Object storage system
- Useful for storing objects that are treated as single units of data.
- In general, good choice when you write or retrieve an object all at once and zou need to store it independentlz of servers that may or may not be running at any time.
- Regions are distict geographic areas that can have multiple zones. Regional Storage keeps copies of object in a single goolge cloud region. A zone is considered a single failure domain.
- Nealine, less than once permonth; cold line, less than once per 90 days; archive, less than once per year


**Persistent Disk**
- Storage services that are attached to VMS in compute engine or k8s engine. 
- persistnet disks provide block storage on solid stat drives SSD and hard disk drives HDDs.
- SSD are oftne used of rlow latency applications where persistent disk performance is importnat. SSDs cost more than HDDs


**Cloud storage for Firebase**
- Mobile app, support uploads and downloads formbobile devices with unreliable network connections


**Cloud Filestore**
- File sys housed on network attached storage


### DataBase

**Cloud SQL**
- relational database service that allows users to set up Mysql, postgresql nd sqlserver databases on VMs without having to atten to data base amin tasks


**Cloud Bigtable**
- desined for petabyte scale applications that cna manage up to billions of rows and thousands of columns.
- Based on NoSQL model knwo as wide-column data model

**Cloud Spanner**
- global distributed relational database  that combines the key benefits of relational database , sich as strong consistency and transactions witht he abioity to svale horizontally like NonsQl database

**Cloud Firestore**
- Non SQL
- document database
- Key value pairs
- Accessed via a rest API that can be used for applications running in compute engines k82 or app engine
- shard / partition data to maintain performance
- suitable for applications that demand high scalabiity and structure data and do not always need strong consistency when reading data


**Cloud Memorystore**
- In memory cache servie. used to cache frequently used data in memory


## Networking Components of Google Cloud

### Network services

**Virtual Private Cloud**
- Enterprise Logically isolated cloud resoureces
- Can span the globe without relying on public Internet by replying on google global network
- Backend servers can access google servies, such as IoT,Ml without creating a public IP address for backend servers

**Cloud Load Balancing**
- Distribute Workloads across cloud infrastructure
- Also supports internal load balancing, so no IP addressses need to be exposed to the internet to get the advantages of load balancing
- it is a software service that can load balance HTTP, HTTPs, TCP/SSL and UDP traffic

**Cloud Armor**
- a google network security services that builds on global HTTPs load balancing service.

**Cloud CDN**
- CDN: Content Delivery Network, users anywhere can request content from systems ditributed in various regions
- Enabling low latency response to these requests by caching contetn on a set of endpoints qcross the globe
- Important for sites qith alrge amounts of static content nd a glpobal audience

**Cloud interconnect**
- Google Cloud service for connecting your existing networks to the Google network: Peering and Interconnects
- 

**Cloud DNS**
- Domain name service, high availability and low latency service for mapping from domain name to ip Address

### Identity Management and security
- identities are abstraction about users of servies
- Users: processing similar set sof permissions
- see next chapter


### Development tool


## Other Components of Google Cloud

**Management and observabulity tools**

**Specialized services**

