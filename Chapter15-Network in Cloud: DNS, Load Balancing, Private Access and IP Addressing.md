# Configuring Cloud DNS
- Domain Name Resolution - Map domain name to IP Address
- A DNS zone is a portion of the domain name system (DNS) namespace that is managed by a specific organization or administrator. It consists of a collection of DNS records that define the mapping between domain names and IP addresses or other resources.

## With Cloud Console
- Public Zone are accessible from the internet. These zones provide name servers that respond to queries from any source
- Private Zone provide name services to google cloud resources, such as VMs and load balancers. It only respond to queries that originate from resources in the same project as the zone
- DNS forwarding: passing DNS queries to an on-premises DNS server if you are using Cloud VPN or Interconnect

## With With gloud

# Configuring Load Balancer
- load Balancers distribute workload to servers running an application
- Load Balancers can distribute within a single region or across multiple resions


## Types of Load Balancer
- Global v regional
- External v Internal
- Traffic Types

## With Cloud Console
## With gcloud



# Google Private Access
- VMs running in a VPC can use exgternal IP adress to connect to Google APIs and other Services
- Private Goolgle Access is used to reach google cloud resources without using an external IP address, allowing you to connect to google APIs thru the VPCs default network gateway
- Private Service Acceses is used to access a Google or third party managed VPC network thru a  VPC peering connection
- Pricate Service Connect is used with Google cloud resources that man or may not have external IP addresses as well as on premises system


    Google Cloud Private Access allows Google Cloud resources to be accessed privately from on-premises networks or other networks not connected to the public internet. This feature enables you to securely connect to Google APIs, services, and data without exposing them to the public internet.

    Here's how it works:

    Private Connectivity: Google Cloud Private Access utilizes Google's global network to establish private connections between your on-premises network or virtual private cloud (VPC) network and Google Cloud services without traversing the public internet.

    Virtual Private Network (VPN) or Cloud Interconnect: To enable private access, you typically set up a VPN tunnel or use Cloud Interconnect to establish a dedicated connection between your network and Google Cloud. This connection is secure and encrypted.

    Private Google Access for on-Premises Networks: With Private Google Access enabled for on-premises networks, instances in your VPC network can access Google Cloud APIs and services like Cloud Storage, BigQuery, and Cloud SQL without external IP addresses.


# Managing IP Address
## Expanding CIDR Blocks
- CIDR blocks define a range of IP addresses that are available for use in a subnet
- If you need to increase the number of addresses available, you can use the gcloud command.
## Reserve IP Addresses


**Server**
    Purpose: Servers are specialized computers designed to provide specific services, resources, or functionality to other computers or users within a network. They can serve various purposes, such as hosting websites, storing data, running applications, managing network traffic, or providing communication services.

    Hardware: Server hardware is typically optimized for reliability, performance, and scalability. It often includes features like multiple processors, large amounts of memory (RAM), redundant power supplies, and storage arrays configured for high availability.

    Operating System: Servers run specialized operating systems tailored for server tasks. Common server operating systems include Linux distributions (such as Ubuntu Server, CentOS, or Red Hat Enterprise Linux) and Windows Server.

    Services: Servers provide services or resources to clients on the network. These services can include web hosting (HTTP), email (SMTP, IMAP), file sharing (FTP, SMB), database management (MySQL, PostgreSQL), domain name resolution (DNS), directory services (Active Directory), and more.

    Networking: Servers are connected to the network infrastructure to communicate with other devices and clients. They typically have one or more network interfaces (NICs) to facilitate communication over local area networks (LANs) or the internet.

    Management: Server administration involves tasks such as installation, configuration, monitoring, maintenance, and security management. Administrators use various tools and techniques to manage servers effectively, ensuring they operate reliably and securely.
