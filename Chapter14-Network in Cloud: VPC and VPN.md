# Creating a VPC with Subnets
- VPC is software version of physical networks that link resources in a project
- VPC is global resources, 
- VPC containes subnetworks. subnetworks called subnets, are regional resource, Subnets have a range of IP associated with them. Subnets provide private internal addresses.
- Resources use these addressses to communicate with each other and with google APIs and services

## Using Console
- A list of subnets are created in a VPC. When an auto mode VPC is created, subnets are created in each region
- Custom subnete config - specify regions and IP address range (CIDR)
- Private Google Access: VMs on the subnet to access google services without assigining an external IP address to the VMs
- regional/global routing

## Using gcloud
## creating shared VPC with gcloud
- shared VPC within an org
- shared VPC is hosted in a common project, users in other prohects who have suffuecient permsisions can create and use resources in the shared VPC
- Before executing commands to create a shared VPC, zou will need to assign an org memebr the shred VPC admin role at org level or the foler level
- WHen an org does not exist, VPC network peering can be used of interproject traffic

# Deploying Compute Engine with a Custom Network


# Creating Firewall Rules for a VPC
- Firewall rules are defined at the network level and used to control the flow of network traffic to VMs
- Firewall rules allow or deny a specified type of traffic on a port, they also apply to traffic in one driection, either incoming or outgoing
- Firewall istateful, if traffic is allowed in one frection and a connection estabilished, it is allowed in the other direction

## Structure of Firewall Rules
**Direction**
**Priority**
**Action**
**Target**
**Source/Destination**
**Protocol and Port**
**Enforcement Status**
- implied 2 rules(65535)for all VPCs: one allows egress traffic to all destinations and one deines all incoming traffic from any source
- 4 default network rules (65534):
    - incoming traffic from any VM instance on the same network
    - incoming TCP traffic on port 22, allowing SSH
    - Incomgin TCP traffic on port 3389, allowing Microsoft RDP
    - Incoming Internet Control Message Protocol from any source on the network

## using console
## using gcloud

# Creating a VPN
- VPNs allow you to securely send network traffic from google network to your own network

## using console
- High Availability and Classic

**VPN Gateway**

A VPN (Virtual Private Network) gateway is a device or software application that serves as an entry point into a VPN network. It's essentially a specialized router or server that facilitates the connection between a user's device and the VPN network.

Here's how it works:

- Authentication and Encryption: When a user initiates a connection to a VPN, the VPN gateway authenticates the user's credentials and sets up encryption parameters to secure the connection.
- Tunneling: The VPN gateway then establishes a secure tunnel between the user's device and the VPN network. This tunnel encrypts all data passing through it, preventing it from being intercepted by unauthorized parties.
- Routing: Once the tunnel is established, the VPN gateway routes the user's internet traffic through the VPN network. This effectively masks the user's IP address and encrypts their internet activity, enhancing privacy and security.
- Access Control: VPN gateways often include access control features to restrict access to the VPN network based on user credentials, device type, or other factors.
- Management: VPN gateways typically provide management interfaces for administrators to configure settings, monitor traffic, and enforce security policies.

## using gcloud


**CIDR**
    classless interdomian routing: a network address for identifying a subnet and a host identifier
    CIDR stands for Classless Inter-Domain Routing. It's a method used to allocate and specify Internet Protocol (IP) addresses and their associated routing information. CIDR allows for more flexible allocation of IP addresses compared to older methods like classful addressing (e.g., Class A, Class B, Class C).

    In CIDR notation, an IP address is followed by a forward slash ("/") and a number representing the network prefix length. The network prefix length specifies the number of bits in the IP address that represent the network portion. This allows for the creation of networks of various sizes, rather than being limited to fixed-size classes.

    Here's an example of CIDR notation:


    192.168.1.0/24

    In this example:

    192.168.1.0 is the base IP address.
    /24 indicates that the first 24 bits (the first three octets) represent the network portion of the address.
    The remaining 8 bits (the last octet) are available for host addresses within the network.
    To understand how many IP addresses are available in this CIDR block, you can calculate it using the formula 2^(32 - prefix length). In this case, it's 2^(32 - 24) = 2^8 = 256.

    So, the CIDR notation 192.168.1.0/24 represents a network with 256 IP addresses, ranging from 192.168.1.0 to 192.168.1.255. The first 24 bits specify the network, and the last 8 bits can be used for individual devices within that network.

**Source and Destinations**

    In firewall rules, the "source" and "destination" refer to specific attributes of network traffic that the firewall is configured to filter or control. These attributes help define which packets are affected by the rule and how they are processed.

    - Source: The "source" in a firewall rule typically refers to the origin of the network traffic. It specifies where the packets are coming from. The source can be identified using various attributes such as IP addresses, IP ranges, subnets, MAC addresses, or specific interfaces.For example, a firewall rule might specify that traffic originating from a particular IP address range (e.g., 192.168.1.0/24) is subject to certain restrictions or permissions.

    - Destination: The "destination" in a firewall rule indicates the intended recipient of the network traffic. It specifies where the packets are going. Like the source, the destination can be defined using attributes such as IP addresses, IP ranges, subnets, MAC addresses, or specific interfaces.For instance, a firewall rule might dictate that traffic destined for a specific IP address or range of IP addresses is allowed or denied based on certain criteria.
    Firewall rules typically involve both the source and destination to determine whether network traffic is permitted or denied. By specifying both the source and destination attributes, administrators can precisely control the flow of traffic through the firewall, ensuring that only authorized communication is allowed while unauthorized or potentially harmful traffic is blocked.


**Protocal**

In computer networking, a protocol is a set of rules and conventions that govern how data is transmitted and received between devices on a network. Protocols define the format, timing, sequencing, and error control of messages exchanged over the network. Different protocols serve different purposes, such as data transmission, network management, addressing, and authentication.Examples of network protocols include:

    - Transmission Control Protocol (TCP): A connection-oriented protocol that provides reliable, ordered, and error-checked delivery of data packets. TCP is commonly used for applications that require guaranteed delivery of data, such as web browsing, email, and file transfer.

    - User Datagram Protocol (UDP): A connectionless protocol that provides faster but less reliable delivery of data packets. UDP is often used for real-time applications, such as video streaming, online gaming, and Voice over IP (VoIP).

    - Internet Protocol (IP): A network-layer protocol responsible for addressing and routing packets across interconnected networks. IP works in conjunction with TCP or UDP to deliver data packets to their destinations.

**Ports**
    In computer networking, a port is a numerical identifier used to distinguish between different services or applications running on a single networked device. Ports are essential for multiplexing multiple network services on a single IP address. Each port is associated with a specific protocol, and a combination of IP address and port number uniquely identifies a network service.Ports are divided into three ranges:

    Well-known ports (0-1023): Reserved for system services and commonly used network services, such as HTTP (port 80), HTTPS (port 443), FTP (port 21), SSH (port 22), and so on.
    Registered ports (1024-49151): Registered by IANA (Internet Assigned Numbers Authority) but available for use by specific applications or services.

    Dynamic or private ports (49152-65535): Available for use by client applications and are assigned dynamically by the operating system.

    For example:
    HTTP typically uses port 80 for communication. So, when you access a website using a web browser, your browser sends HTTP requests to the server's IP address on port 80.

    FTP typically uses port 21 for control messages and port 20 for data transfer. When you upload or download files using an FTP client, it establishes connections to the FTP server's IP address on these ports.
    
    In summary, protocols define the rules and conventions for communication between network devices, while ports provide a way to multiplex multiple network services on a single device by using numerical identifiers. Together, protocols and ports enable the reliable and efficient exchange of data across computer networks.


**Route**

    In networking, a route refers to the path that network packets take from their source to their destination. Routes are defined in routing tables, which are maintained by routers and other networking devices. These routes contain information about how to reach specific networks or hosts.

    There are two main types of routes:

    Static Routes: Static routes are manually configured by network administrators. They define explicit paths for network traffic to follow. Static routes are often used for simple network setups or for specific cases where the path to a destination is well-defined and unlikely to change frequently.
    Dynamic Routes: Dynamic routes are learned automatically by routers through routing protocols. Routing protocols enable routers to exchange routing information and dynamically update their routing tables based on changes in the network topology or traffic conditions. Common routing protocols include OSPF (Open Shortest Path First), RIP (Routing Information Protocol), and BGP (Border Gateway Protocol).