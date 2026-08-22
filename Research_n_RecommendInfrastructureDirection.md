# Epilogue
Before initiating an investigation, it is important to first identify what the client wants, after two meetings with client Naresh, it is stated that he wants a solution that is:
- Scalable
- Focus on Audutors
- Allow Users to report content
- Managers(so definitely some kind of management tooling)
- Creativity.(Go crazy with it)

Therefore it is important that for both hosting and database options, that the solutions chosen are:
- Scalable
- Modular Architecture(Easy to update and understand)
- Easy to manage
- KISS(Keep It Simple Stupid)

# Hosting Options Investigation

## Introduction
Server hosting is an IT service, which in this case is being provided by IBM. IBM provies cloud services that allows hosting, they handle the physical hardware and some of the software pre-requisites to handle website hosting.

This arrangement menas that for a monthly subscription, that the user can avoid up-front cost, delays, and labor of purchasing, setting up, managing, and maintaining physical server hardware themselves, onsite. This means
- Faster server development and application delivery
- Predictable ongoing costs with no capital expenditures
- Simple, responsive and inexpensive scaling(very important)

The types of server hosting options available to us are
- Shared server hosting
- Virtual Private Server(VPS) hosting
- Dedicated server hosting

For this application, the best hosting option would be VPS as unlike dedicated server hosting, VPS lets you quickly shift your workloads among multiple virtual server instances, and there is no resources that we have to share unlike Shared Server hosting. VPS can quickly scale resources to meet unpredictable surges in traffic.

## Hosting Options
IBM VPS already has many advantages includng:
- Global Hosting
- Pay-as-you-use billinb
- Best-in-class network performance
- Enterprise-grade security
- Reliable support
- Seamless add-ons

The four options available are:
- IBM Cloud Virtual Servers for VPC
- IBM Cloud Hyper Protect Virtual Servers
- IBM Cloud Code Engine
- IBM Power Systems Virtual Servers

### IBM Cloud Virtual Servers for VPC
#### Description
Solution built on IBM Cloud Virtual Private Cloud(VPC), it aims to have developer-friendly infrastructure, faster modern workloads and easier with pre-set instance profiles, rapid deployment and private network control in an agile public cloud environment. Pay-as-you-use by the hour or reserve your capacity in advance for reduced costs. The deployment options are either a Public, multi-tenant deployment or a Dedicated, single-tenant deployment.
#### Advantages
- Hyperscale provisioning: Provision and deploy 1,000 virtual server instances in 4 minutes or less, consistently.
- Best-in-class networking performance: Get up to 80 Gbps across general purpose virtual server profiles.
- Developer-friendly: Use the REST-based API that’s aligned to industry norms, with easy integration into existing tooling.
- Logically isolated: Keep granular control over which IP addresses and applications can access your resources.
- Security-rich environment: Effectively maintain your regulated environment with support for KYOK, BYOK and the highest level of FIPS certification. 
- Cost-effective high availability: Strengthen fault tolerance and help keep key specific workloads from being under-utilized or over-utilized.
- Trusted technology partnerships: Support your critical applications across a range of enterprise solutions. IBM Cloud is a trusted consulting and technology partner of SAP and Red Hat.
- Choice of AI infrastructure: Deploy your AI models in the cloud with a wide variety of cost-effective GPUs and AI accelerators.
#### Disadvantages
- Deployment Issues: Immediately shut down after booting of Hyper Protect instances if YAML schemas or logging configurations are incorrectly setup
- Capacity Issues: Some zones can receive a "cannot_start_capacity" error, which means that the chosen zone has insufficient resources(goes against scaling requirement)
- Network Limitations: IPv6 isn't supported for standard virtual server instances within IBM Cloud VPC, Only TCP, UDP, and ICMP protocols are fully supported by security groups and network ACLs, and disabling NAT infrastructure on virtual server instances isn't supported.
- Routing Limitations: Communication between virtual servers and internal IBM Cloud services can be blocked if endpoints, network ACLs, or reserved IP addresses are misconfigured.

### IBM Cloud Hyper Protect Virtual Servers
#### Description
Solution aims to achieve a runtime container that delivers a confidential computing environment, protecting Linux workloads from internal and external threats using IBM Secure Execution for Linux, while having seamless operations.
#### Advantages
- Build with end-to-end security: Developers can build applications in a trusted execution environment that keeps sensitive data encrypted and isolated at all times.
- Deploy with verified trust: Admins can validate application origin and integrity by using encrypted contracts and attestation for secure, zero-trust deployments.
- Manage sensitive data confidently: Operations teams can manage workloads without accessing sensitive data, reducing insider risk and enforcing data privacy.
- Operate on-premises: Run protected workloads with consistent security policies and container registry support.
#### Disadvantages
- No support: This solution is depreceated as of 20-02-2026, full support ended 20-02-2027. No new instances can be created.
- Its replacement is IBM Confidential Computing Container Runtime.

### IBM Code Engine
#### Description
Solution is a fully managed, serverless platform that runs containerized applications, batch jobs, and source code without requiring manual infrastructure or cluster management. It abstracts Kubernetes complexity, scales down to zero, and lets you pay only for consumed resource 
#### Advantages
- No Infrastructure Management: Automatically handles provisioning, networking, security, and cluster scaling.
- Scale-to-Zero Pricing: Reduces costs by scaling resources down to zero when inactive and billing only for active usage.
- Direct Source-to-Container Building: Builds container images automatically straight from raw source code or Git repositories using native buildpacks.
- Unified Workloads: Combines web apps, long-running processes, event-driven triggers, and batch jobs in one platform.
- Open Source Foundations: Built on transparent technologies like Kubernetes, Knative, and Istio, reducing vendor lock-in
#### Disadvantages
- Ecosystem and Documentation Gaps: Fewer community learning resources, videos, and manuals compared to older serverless giants like AWS Lambda.
- Platform Complexity for Beginners: Container concepts can still present a steep learning curve for users completely new to cloud-native workflows.
- Shared Multi-Tenant Constraints: Operates as a shared regional network infrastructure which may not fulfill niche regulatory or strict isolated architecture requirements.
- Cost at Scale: While cheap for intermittent use, continuous high-traffic operations can become expensive compared to reserved bare-metal or standard cluster pricing.

### IBM Power Systems Virtual Servers
#### Description
Solution provides a family of configurable, multitenant, virtual IBM Power servers with access to other IBM architectures such as watsonx.ai. Maintains high security and performance of IBM Power while modernising at your pace and price point on and off premises.
#### Advantages
- Business continuity planning: Keep your business running with reliable failover solutions including backup, high availability and disaster recovery. Reduce capital expenditure, planning complexity and capacity headroom.
- Modernization: Connect to over 250 IBM Cloud services, with APIs that easily integrates to existing tools. Shift from buying maximum capacity to provisioning on demand, as needs arise.
- Data center optimization and operational excellence: Optimize your data center for faster growth and global reach with certified architectures and ISV support, while cutting costs and improving service with faster response times and flexible pay-as-you-go billing.
- Accelerate adoption of RISE with SAP: Follow the fastest and least disruptive path to transform your business with IBM Power Virtual Server.
#### Disadvantages
- Users must handle application maintenence, OS-level security patches, and update continuously
- Pinning Restrictions: Using Virtual Server Instance (VSI) pinning prevents automatic live migration during host maintenance, forcing scheduled downtime if hardware needs updates.
- OS Lifecycle Strictness: Running older, unsupported versions of AIX, IBM i, or Linux leads to compliance blocks, lack of patches, and dropped technical support.

## Preferred Hosting Direction and Rationale
As discussed earlier, the Virtual Private Server(VPS) hosting solutions are chosen for its balanced of cost, scalability and workability. Based on the research that is summarised above, the chosen solution is IBM Cloud Virtual Servers, as it is highly scalable, with low cost and simple development road, while also containing the most descriptive documentation.

# Storage Options Investigation

## Introduction
Based on initial investigation, this project will require a very flexible storage solution.

## Storage Options
The options available are
- LTO Tape Cartridges
- IBM cloud Object Storage
- IBM FlashSystem

Based on initial findings, it's clear that the only practical solution this team can implement that meets all requirements is IBM Cloud Object Storage. It delivers:
- High end cyber security
- Data availability and compliance
- Multi-zone resuiliency
- fast data transfer options
- Optimised for AI
- Stores media, backups and archives well
- Built in Role based policies and access permissions protected with encryption key management system
- Flexible storage teirs mean monthly payment fees only scale to when storage is actually being utilised, theoretical data storage is infinite.

Therefore we'll look at the different tiers that IBM Cloud Object Storage holds. These tier and their advantages and disadvantages are.
| Teirs | Advantages | Disadvantages |
| --- | --- | --- |
| One-Rate | Predictable costs from combining storage, API, egress and retrieval of data without separate charges. Monthly storage rate decreases and API and egress increases by storage volume | Bad if media and data being accessed is unpredictable(for our application most likely) |
| Smart tier | Built for changing data, stores data without cost over runs,  | --- |
| Standard | Immediate data availability(streaming media), DevOps, analytics, collaboration and active content repositories with no retrieval charges, minimum object size and minimum duration requirement | --- |
| Vault | Grade below standard, meant for less active data | Small retrieval charge to read data, meant for data accessed once a month/less, threshold object size of 128KB, storage duration of 30 days |
| Cold Vault | A grade above archiving, specialises in long-term backup, large dataset preservation | Threshold object size of 256KB, minimum storage duration of 90 days |
| Archive | Low cost, data transition using archive policies from other tiers and simple API | --- |

There is also a separate storing option specifically for AI under IBM storage. I recommend Deleloper 2(Kai Lek Kum) to investigate it in his own time, but the synapsis is this; It offers:
- Retrieve data faster: Leverage AI-driven autonomous storage with NVMe performance to deliver data at scale with high throughput, low latency and always-on availability—ensuring fast, intelligent access through deep AI integration.
- Reduce silos: Consolidate data and workloads across environments with a scalable solution optimized for hyperconverged infrastructure (HCI)—spanning edge, on-premises and cloud while enabling seamless AI integration.
- Improve collaboration: Enable smarter collaboration with content-aware storage that intelligently manages and shares data and workloads—ensuring the right users have access at the right time while improving efficiency and utilization.
- Simplify operations: Streamline IT with centralized data and application services on a single, scalable, AI-driven autonomous storage platform that integrates easily with existing environments and modern architectures like HCI.
- Optimize costs: Minimize data sprawl with a flexible, scalable storage solution that uses AI integration to optimize performance and capacity—supporting growth without overprovisioning.
- Reduce risk: Strengthen security posture with built-in data resiliency and disaster recovery and advanced ransomware protection, ensuring rapid recovery and continuous business operations.

## Advantages of IBM Cloud Object Storage
- Central service for AI and data lakes: Provides an ideal low-cost data store for AI workloads, natively integrated with the watsonx portfolio.
- Immutable data retention: Protect against ransomware and preserve electronic records and data integrity until retention and/or legal requirements are met.
- Native backup: Back up your data to a protected Backup Vault, secured from deletion or modification.
- Native geographic resiliency: Protect data within or across established regions, providing immediate data consistency with no replication lag.
- Data replication: Replicate your object data across customized cloud regions to meet your unique requirements.
- Fast data transfer: Improve transfer times with natively integrated IBM Aspera® high-speed data transfer

## Disadvantages of IBM Cloud Object Storage
- High Latency: Slower time-first-byte
- No In-Place Editing: Cannot perform random writes or modify parts of existing file. Updating said file requires rewriting it backend
- Consistency Limits: Overwrites and deletions experiency can cause "stale data"
- Lack of POSIX Compliance: Standard file system semantics aren't supported. These include atomic renames, hard links, native multi-client directory locking.
- Complex Management: Managing network connection interfaces, resource usage logs and granular access controls are challenging for new admins.
- Cost Structure: Base and data transfer fees can scale up quickly, need careful infrastructure planning to avoid unexpected expenses.

## Preferred Storage Direction and Rationale
It is clear that the best storage architecture to persue is IBM Cloud Object Storage, where Standard tier handles ongoing/recent content being flagged and assessed, Cold Vault tier for content that might be reassessed on a later date and Archive tier for long term storage, under Smart Tier for scalability. Moreover, for our AI agents, we'll utilise IBM Storage solutions for AI.

# Database Options Investigation
## Introduction
IBM databases allow applications to run with analytics and gnerative AI workloads across the cloud, even on other cloud services such as Amazon Web Services(AWS), aiming to work on all workloads while maintaining performance and cost efficiency. Works with other IBM architecture such as watsonx.data, optimises price-performance for our use cases.

## Database Options
The options available are:
- IBM Db2
- Db2 Warehouse
- EDB Postgres
- IBM Cloud Databases

### IBM Db2
#### Description

#### Advantages

#### Disadvantages

### Db2 Warehouse
#### Description

#### Advantages

#### Disadvantages

### EDB Postgres
#### Description

#### Advantages

#### Disadvantages

### IBM Cloud Databases
#### Description

#### Advantages

#### Disadvantages

## Preferred Database Direction and Rationale

# IBM service constrain Investigation
Based on the document above, this part will only list out the service constraints that we're planning to use:
### Virtual Private Server(VPS)
### IBM Cloud Object Storage
### IBM Storage solutions for AI
### PostgreSQL

# Dependencies/Limitations documentation
Based on the document above, this part will only list out the service constraints that we're planning to use:
### Virtual Private Server(VPS)
### IBM Cloud Object Storage
### IBM Storage solutions for AI
### PostgreSQL

# Recommendations to Project Manager and Developer 2
**For Dat Nguyen Minh[PM]:**
Lol idk.

**For Kai Lek Kum[Dev2]:**
Investigate further how IBM Storage for Data and AI can be utilised for our architecture and how it should be implemented. Once so, document advantages, disadvantages, and any question you have for Naresh.

# Questions for Naresh
- Hosting Options Investigation
Are we limited to IBM solutions?
How important is cyber security?
What information do you wanna store?
- Storage Options Investigation
For media storage is it permanent or only lasts for a few days?

- Database Options Investigation
- IBM service constrain Investigation
- Dependencies/Limitations documentation
- Recommendations to Project Manager and Developer 2

# Sources
##### Hosting Options Investigation
- [Source1](https://www.ibm.com/think/topics/server-hosting)
- [Source2](https://www.ibm.com/products/cloud/web-hosting)
- [Source3](https://www.ibm.com/solutions/cloud-vps)
- [Source4](https://www.ibm.com/products/virtual-servers)
- [Source5](https://www.ibm.com/products/confidential-computing-container-runtime)
- https://cloud.ibm.com/docs/codeengine?topic=codeengine-about
- [Source6](https://www.ibm.com/products/power-virtual-server)
##### Storage Options Investigation
- [Source7](https://www.ibm.com/solutions/storage)
- [Source8](https://www.ibm.com/products/cloud-object-storage)
- [Source9](https://www.ibm.com/products/cloud-object-storage/storage-classes)
- [Source10](https://www.ibm.com/solutions/ai-storage)
https://www.ibm.com/solutions/ai-storage 
##### Database Options Investigation
##### IBM service constrain Investigation
##### Dependencies/Limitations documentation
##### Recommendations to Project Manager and Developer 2