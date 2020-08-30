## Azure basics:

### Azure Resource Manager 

- It’s a management layer in which resource groups and all the resources are created/configured/modified/deleted
Uses JSON files which are called ARM templates. This helps you create Azure resources via JSON template. It’s a IaC service.
Resources can be deployed using the Azure portal, CLI, powershell, Azure app or Cloudshell (built in shell in Azure GUI)
ARM talks with Azure resources on your behalf and makes it easier to interact with Azure services.
- Azure Portal/CLI/Visual studio ---> ARM API -----> Different Azure resources
- Azure QuickStart - quickly launch projects  using a library of premade ARM templates from partners and vendors.
- A regular Azure portal to access, manage, and create Azure resources. URL - portal.azure.com. It’s a GA portal
- Azure preview portal - for features like, preview, beta, other pre-release. Test preview features --> URL - preview.portal.azure.com.
- Azure Subscriptions:
  - Free - $200 for 30 days and certain free Azure services for 1 year.
  - Free trial - hard limit of 1/account
  - Student subscription 
  - $100 for 12 months
  - Pay-as-you-go -- general purpose
- Only 20 vCPU. Request for more.
- An account can have multiple subscriptions. Subscription aka account.
- Enterprise agreement - Azure and an enterprise agree on discounted prices for licenses and cloud services.
- Pay-as-you-go dev/test - for visual studio developers for dev and testing. Discounted rate for VMs and other resources.
- Azure Govt Services
  - Specially built for US Govt
  - Separate cloud from public Azure cloud
- Azure Germany 
  - A special cloud environment for European customers.
  - Operated by trustees. Not by Microsoft. 
  - This is to fulfill requirements mandated by European union.
- Azure China
  - Access Azure China via 21vianet (compliant with most rules)
  - For compliance requires.
  - Data never leaves China.

### Regions:
- Recommended region - Supports AZs
- Alternate or other region - doesn’t support AZs
- GA - a service is generally available for every customer. GA has the following categories:
- Foundational - available in recommended or other regions immediately or in 12 months. 
- Mainstream - available in recommended regions immediately or in 12 months. May become available in other regions upon customer requests.
- Specialized - available in recommended and other regions on customer demand.
- Azure Storage Account:
  - An Azure storage account contains all of your Azure Storage data objects: blobs, files, queues, tables, and disks. The storage account provides a unique namespace for your Azure Storage data that is accessible from anywhere in the world over HTTP or HTTPS.
- Storage account names are globally unique because names are used in endpoints and endpoints need to be unique.
- You get charged for storage + egress data.
- A resource must be  in one and only one resource group.
- IP Flow verify - ping in Azure
- Nexthop - like traceroute
- Tenant - a place where your Azure AD is. You log on to access Azure.
- A subscription is where you create resources.

### Azure Geographies:

- Azure regions are divided into geographies.
- There are special regions for government & DoD.
- Each region is in one geography
- Geography - NA, region - US-West-2
- Geography > Region > AZ
- Azure Availability Zones fall into:
-AZ - multiple data centers within a region.
  - 2 categories:	
    - Zonal Services - You pin down a resource to an AZ
    - Zone redundant services - Azure replicates to a different AZ

### Region Pairs:

- In case of natural disaster or power outages, 2 regions are paired together.
- If a region from the pair goes down, all the services and apps get replicated to another region
- US-West region is paired with US-East
- A pair is always in the same geography. 
- Advantages of region pairs
- Patches and updates can be rolled out to 1 region at a time without any downtime
- If there’s a regional outage, data will be replicated to another region in the pair
- Data remains in the same geography


### Availability sets 

- used to avoid single point of failure. Helps you ensure that your apps are running during maintenance events and HW failure.
- Logical grouping of VMs
  - 3 fault domains
  - 5 update domains
- Make use of fault domain and update domain
- Fault domain - separate rack - protects from HW failure
- Update domain - separate server - protects from VM reboots - updates happen in sequence. 
- Zones vs Sets
- Sets are region specific.
- Choose either a zone or  a set at the time of VM creation.
- Zone - data center, Sets - a rack or racks within a datacenter
- Zones have better SLAs
- Zones might not be available in all regions.
- Sets SLA - 99.95%
- Zones SLA - 99.99%

