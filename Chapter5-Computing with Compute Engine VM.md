# 1 Creating and Configure VM with Console
Three ways: Goolgle cloud console, SDK (software dev kit), Shell
The first time to work with VM, you need to have a billing account 
## Main VM Config Details
    - Name of the VM
    - Region and zone where the VM will run
    - Machine type, which determines the number of CPUs and the amount of memeory in the VM
    - Boot Disk, which includes the operating sys the VM will run

**Machine Family**: General Purpose, Compute optimized, Memory optimizd, GPU (A set of processor and hardware config designed for particular workload)
**Series & Generations**
**Machine Type**
**Boot Disk**: SSD (Solid State Drive) & HDD (Hard Disk Drive)
SSDs offer faster performance, greater durability, and lower power consumption compared to HDDs, but at a higher cost per gigabyte. HDDs, on the other hand, provide larger storage capacities at a lower cost but are slower and less durable due to their mechanical components. 

## Advanced Config Details
- Management Tab: Describe VM and the use. Create Labels
- Security Tab: Shielded VM ir Secure Shell Keys
- Boot Disks and Additioanl Disks
- Networking Tab
- Sole Tenancy tab: Sole tenancy refers to a hosting environment where a single client or customer has exclusive access to the entire physical server or computing resources of a provider.


# 2 Creating and Config VM with Cloud SDK and Shell
Cloud SDK provides a command line interface (CLI)
To use it, you first need to install it on your local device

## Installing Cloud SDK
three ways to interacting with Cloud resources
- Using command line interface
- Using RESTful interface
- Using Cloud Shell
## Example Installation on Ubuntu Linux

## Creating VM with Cloud SDK
- gcloud command is organized into a hierarchy of groups
- group -> subgroup -> action
  gcloud compute instances create ace-instance-1 ace-instance-2

## Creating VM with Cloud Shell
An alternativeto run gcloud commands locally is to run them in a cloud instance -- Cloud shell


# 3 Basic VM Management
## Starting and Stopping Instances

## Network Access to VM
- Need to log into a VM to perform some admin tasks: using SSh when logging into a linux server or Remote Desktop Protacol when logging into a windows server

## Monitoring a VM
## Cost of VM
- VM are billed in 1 second increments
- The cost is based on machine type
- offers discounts on sustained usage
- VMs are charged for a min of 1 min use
- Spot VMs can save up to 80% of cost

# 4 Guidelines for Planning,Deploying and Managing VMs
- Choose the machine type with fewest CPus and the smallest amount of memo which still meet the requirement
- Use the console for ad hod admin, and scripts for tasks that are repetitive
- Use startup scripts to perform software updates 
- Save the modifications and use it with new instance
- **Use SSH or RDP to accesss a VM to perform operating system level tasks**
- **Use Cloud Console,Shell or SDK to perform VM-level tasks**
