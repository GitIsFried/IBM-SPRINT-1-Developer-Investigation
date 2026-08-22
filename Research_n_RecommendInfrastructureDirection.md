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
Solution that provides SQL-based relational database that delivers advanced data management and analytics capabilities for transactional workloads. Designed for transactional, analytical and mission-citical workloads.

#### Advantages
- Strong performance: Designed for high-performance transactional and analytical workloads.
- Scalability: Supports scaling for large enterprise workloads.
- High availability: Provides features for backup, recovery and high-availability deployments.
- Security: Provides enterprise security and access-control capabilities.
- IBM ecosystem integration: Integrates well with other IBM services, including watsonx and IBM's data and AI services.
- Mature technology: Well-established database technology suitable for mission-critical applications.

#### Disadvantages
- Potentially excessive for the project: The capabilities of Db2 are significantly beyond what is required for a relatively small web application.
- Higher complexity: Requires more database expertise and administration than simpler alternatives.
- Cost: Enterprise-oriented features can make Db2 less attractive for a low-cost student/project deployment.
- Less developer familiarity: PostgreSQL and MySQL are generally more familiar to modern web developers.
- Potential vendor lock-in: Using Db2-specific functionality can make migration to another database more difficult.

### Db2 Warehouse
#### Description
Data warehouse designed for high-performance, in-database analytics. Runs on a single node for cost-efficiency or on multiple nodes for improved performance. Best used for large-scale applications.

#### Advantages
- Excellent analytical performance: Designed for complex queries across large datasets.
- Scalable: Can support large quantities of analytical data.
IBM ecosystem integration: Can integrate with IBM's data, analytics and AI technologies.
- Useful for future analytics: Could support advanced reporting or machine-learning workloads if the project grows substantially.
- Data warehouse capabilities: Better suited than a traditional transactional database for analysing historical data.

#### Disadvantages
- Not designed as the primary application database: A web application generally requires a transactional database rather than a data warehouse.
- Overkill: The project's expected data volume and analytical requirements do not justify a dedicated data warehouse.
- Higher cost and complexity: Introduces additional infrastructure and management requirements.
- Unnecessary duplication: Using both a transactional database and Db2 Warehouse would create an additional data pipeline that the project does not currently require.

### EDB Postgres
#### Description
An integrated portfolio of databases and tools that extend PostgreSQL for enterprise workloads. Adds additional enterprise capabilities, tools, security features and support.

#### Advantages
- PostgreSQL compatibility: Uses PostgreSQL technology, providing access to the PostgreSQL ecosystem and SQL functionality.
- Enterprise features: Provides additional tools and capabilities for enterprise deployments.
- Scalability: Suitable for larger and more demanding PostgreSQL workloads.
- Migration support: Can be useful for organisations migrating from proprietary databases to PostgreSQL.
- Familiar technology: Developers familiar with PostgreSQL can generally work with EDB Postgres.

#### Disadvantages
- More than the project requires: Enterprise EDB capabilities are unnecessary for a relatively small application.
- Cost: Enterprise support and additional functionality can increase costs.
- Additional complexity: Provides capabilities that the development team may not need.
- Potentially redundant: IBM Cloud already provides managed PostgreSQL through IBM Cloud Databases.
- Maintenance considerations: Depending on the deployment method, additional administration may still be required.

### IBM Cloud Databases
#### Description
Delivers and maintain ready-to-use, highly available, database instances, allowing developers and IT staff to focus on value added tasks and database software including PostgreSQL, MySQL, MongoDB, Redis and other database offerings, infrastructure operations, database software updates, and backup. IBM Cloud® Database SMEs deliver and maintain ready-to-use, highly available, database instances freeing developer and IT staff time to focus on other priorities.

#### Advantages
- Low management overhead: IBM manages much of the database infrastructure.
Easy deployment: Databases can be provisioned through IBM Cloud rather than manually installing and configuring a database server.
- Scalability: Database resources can be adjusted as application requirements increase.
Managed backups and recovery: Reduces the amount of database administration required from the development team.
- High availability options: Supports configurations designed to improve database availability and resilience.
- PostgreSQL compatibility: Provides access to a mature, widely used open-source relational database.
- Good application compatibility: PostgreSQL is well suited to web applications containing structured data and relationships.
Integration with IBM Cloud: Can integrate with the project's IBM Cloud infrastructure and other services.

#### Disadvantages
- Ongoing service cost: A managed database can cost more than installing a database directly on an existing virtual server.
Service limitations: Available resources, connections, storage and configurations are subject to IBM's service limits and quotas.
- Less infrastructure control: IBM manages the underlying database environment, limiting low-level configuration compared with self-hosting.
- Internet/cloud dependency: Application availability depends on the database service and network connectivity.
- Potential migration considerations: Although PostgreSQL is open source, IBM-specific deployment and management configurations may need to be considered when migrating to another provider.

## Preferred Database Direction and Rationale
Based on previously chosen architecture solutions and stakeholder needs, IBM Postgre and IBM Cloud Databases are the best architectural solutions chosen. EDB Postgres is cyber secure, structured, has built in permissions, PostgreSQL is widely supported by many modern development frameworks and programming languages. IBM Cloud Database is better if running directly on IBM Cloud Virtual Server as it provides a managed database environment.

# IBM service constrain Investigation
Based on the document above, this part will only list out the service constraints that we're planning to use:
### Virtual Private Server(VPS)
### IBM Cloud Object Storage
### IBM Storage solutions for AI
### EDB Postgres

# Dependencies/Limitations documentation
Based on the document above, this part will only list out the service constraints that we're planning to use:
### Virtual Private Server(VPS)
### IBM Cloud Object Storage
### IBM Storage solutions for AI
### EDB Postgres

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
- [1] "IBM, “Server Hosting,” Ibm.com, 13,Oct,2021. [https://www.ibm.com/think/topics/server-hosting](https://www.ibm.com/think/topics/server-hosting) (accessed 22/08/2026)
- [2] “Cloud web hosting | IBM,” Ibm.com, 25,Sept,2025. [https://www.ibm.com/products/cloud/web-hosting](https://www.ibm.com/products/cloud/web-hosting) (accessed 22/08/2026)
- [3] “Cloud VPS hosting | IBM,” Ibm.com, 15,July,2025. [https://www.ibm.com/solutions/cloud-vps](https://www.ibm.com/solutions/cloud-vps) (accessed 22/08/2026)
- [4]
“IBM Cloud Virtual Server for VPC,” www.ibm.com. [https://www.ibm.com/products/virtual-servers](https://www.ibm.com/products/virtual-servers) (accessed 22/08/2026)
- [5] “IBM Confidential Computing Container Runtime,” Ibm.com, Feb. 20, 2026. [https://www.ibm.com/products/confidential-computing-container-runtime](https://www.ibm.com/products/confidential-computing-container-runtime) (accessed 22/08/2026)
- [6] Ibm.com, 2024. [https://cloud.ibm.com/docs/codeengine?topic=codeengine-about](https://cloud.ibm.com/docs/codeengine?topic=codeengine-about) (accessed 22/08/2026) 
- [7] “IBM Power Virtual Server,” www.ibm.com. [https://www.ibm.com/products/power-virtual-server](https://www.ibm.com/products/power-virtual-server) (accessed 22/08/2026)
##### Storage Options Investigation
- [8] “Enterprise Data Storage Solutions | IBM,” Ibm.com, 2026. [https://www.ibm.com/solutions/storage](https://www.ibm.com/solutions/storage) (accessed 22/08/2026)
- [9] “IBM Cloud Object Storage - Overview,” www.ibm.com. [https://www.ibm.com/products/cloud-object-storage](https://www.ibm.com/products/cloud-object-storage) (accessed 22/08/2026)
- [10] “Flexible storage classes - IBM Cloud Object Storage,” Ibm.com, 2025. [https://www.ibm.com/products/cloud-object-storage/storage-classes](https://www.ibm.com/products/cloud-object-storage/storage-classes) (accessed 22/08/2026)
- [11] “Artificial Intelligence (AI) Storage Solutions | IBM,” Ibm.com, 2026. [https://www.ibm.com/solutions/ai-storage](https://www.ibm.com/solutions/ai-storage) (accessed 22/08/2026)
##### Database Options Investigation
- [12] “Database Solutions | IBM,” Ibm.com, 2023. [https://www.ibm.com/solutions/database](https://www.ibm.com/solutions/database) (accessed 22/08/2026)
- [13] “Db2 for Linux, UNIX and Windows,” Ibm.com, 09,Jan,2026. [https://www.ibm.com/docs/en/db2/11.5.x?topic=editions-db2-database-product-offerings](https://www.ibm.com/docs/en/db2/11.5.x?topic=editions-db2-database-product-offerings) (accessed 22/08/2026)
- [14] “IBM Software Hub,” Ibm.com, June 18, 2026. [https://www.ibm.com/docs/en/software-hub/5.4.x?topic=services-data-management](https://www.ibm.com/docs/en/software-hub/5.4.x?topic=services-data-management) (accessed 22/08/2026)
- [15] “Data Management Software & Solutions | IBM,” Ibm.com, 2025. [https://www.ibm.com/solutions/data-management](https://www.ibm.com/solutions/data-management) (accessed 22/08/2026)
- [16] “Cloud database solutions | IBM,” Ibm.com, 2025. [https://www.ibm.com/products/cloud-databases](https://www.ibm.com/products/cloud-databases) (accessed 22/08/2026)