# 1 Managing Single VM instances
## Managing single VM instance in the console

**Start, Stop and Delete Instances**
- When a VM is restarted,the content of memeory are lost. If you need to preserve data between reboots or for use on other VMs, save the data to a persistne disk or Cloud Storage

**Viewing VM Inventory**
- Filter based on Labels, Internal IP, External IP, etc..

**Attaching GPUs to an Instance**
- GPU is used for math intensive application such as visualizationa nd ml, they perform math calculations and allow some work to be offloaded from the CPU to GPU
- Compute engine has a machine family specifically designed for VMs with GPUs
- To use GPU, you need to install GPU drivers or use an image that has GPU drivers already installed

**Working with SnapShot**
- Snapshots are copies of data on a persistent disk. You can use snapshots to save data on a disk so that you can restore it.
- Snapshots is a way to make multiple persistent disks with the same data or back up a disk so that you can recover the state of the disk 
- When running a database or other application that may buffer data in memo before writing to disk,
flush the disk buffers before creating the sanpshots, otherwise the data in mom that should be written to disk may be lost
- User need Compute Storage Admin Role to work with snapshots

**Working with Images**
- Images are similar to Snapshot in that way that they are also copies of disk contents.
- Snapshots are used to make data availabel on a disk , while images are used to create VMs
- VMs can also be created from snapshots, as long as the snapshots is made from a boot disk
- Main diff is that snapshots offer increamental backups, images are a single compelte backup
- Imgaes can be made from: disk,snapshot,image,cloud storage file, virtual disk

***In summary, an image is a static representation of a system or application, typically used for deployment purposes, while a snapshot is a dynamic point-in-time copy of a system or data, often used for backup and recovery.***

**Image**

An image generally refers to a static copy or representation of a system, application, or data at a particular point in time. It's often used in the context of virtual machines or containers.
An image is typically created before runtime, and it's a complete package containing all the necessary files, configurations, and dependencies to run the desired system or application.
Images are often used for deployment, distribution, and replication of systems across different environments.

**Snapshot**
A snapshot, on the other hand, is a point-in-time copy of a specific state of a system or data.
Snapshots are dynamic and are usually created during runtime. They capture the current state of a system or data at the moment the snapshot is taken.
Snapshots are commonly used for backup, recovery, and system state preservation purposes.
In virtualization environments, like VMware or Hyper-V, snapshots are used to capture the state of a virtual machine at a certain point, allowing administrators to revert back to that state if needed.
In storage systems, snapshots are used to capture the state of data, providing a point-in-time copy that can be used for data recovery or analysis without affecting the original data.


## Managing single VM insatnce in Shell and Command Line
- gcloud global flags
    - --account,--configuration,--format,....
- starting/stop/delete/instances
- viewing VM inventory
- Working with snapshots, images

# 2 Intro to Instance Group
- Managed groups: Groups of identical VMs. Created using an instance template. Can automatically scale the number of instances in a group and be used with load balancing to distribuet workloads across the instance group.

- Unmanaged groups should be used only when u need to work with diff config within diff VMs in the group

## Creating and Removing Instance Groups and Templates
- To create group, first create an instance group template
- U can also specify an existing VM as the stouce of the instacne template
- Instance group can contain instances in a zone or across a region: regional managed instance group is reconmended as it increases resiliency
- Distribution Policy

## Instance Groups Load Balance and Autoscaling
- To deploy a scalabel, highly available application, you can run that application on a load-balanced set of instances.
- In addition to load balancing, managed instance group can be configured to autoscale.U can config an aitoscaling policy to trigger, adding or removing instances based on CPU utilization, monitoring metirc, load balancing capacity or queue based workload


# 3 Guideline for Managing VMs
- Use Labels and descriptions
- Use managed instance groups to enable autoscaling and laod balancing
- Use GPUs for numeric intensive processing
- Use Snapshots to save the state of a disk or to make copies
- Use preemptible instances for worlloads that can tolerate disruptions