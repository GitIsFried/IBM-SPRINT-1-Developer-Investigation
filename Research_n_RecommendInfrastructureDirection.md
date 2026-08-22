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

## Storage Options

## Advantages

## Disadvantages

## Preferred Storage Direction and Rationale

# Database Options Investigation

## Introduction

## Database Options

## Advantages

## Disadvantages

## Preferred Database Direction and Rationale

# IBM service constrain Investigation

# Dependencies/Limitations documentation

# Recommendations to Project Manager and Developer 2

# Sources
- Hosting Options Investigation
https://www.ibm.com/think/topics/server-hosting
https://www.ibm.com/products/cloud/web-hosting
https://www.ibm.com/solutions/cloud-vps
https://www.ibm.com/products/virtual-servers 
https://www.ibm.com/products/confidential-computing-container-runtime
https://www.ibm.com/products/power-virtual-server
- Storage Options Investigation
- Database Options Investigation
- IBM service constrain Investigation
- Dependencies/Limitations documentation
- Recommendations to Project Manager and Developer 2