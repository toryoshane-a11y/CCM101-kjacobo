# Cloud Infrastructure Components

## Compute Resources
Compute resources refer to the processing power that runs applications, executes 
instructions, and handles workloads on a server. In cloud computing, compute is one 
of the most critical resources because it directly determines how much workload a 
virtual machine or instance can handle, and it is typically the resource that cloud 
providers scale up or down based on demand. On my KillerCoda environment, the compute 
resource is represented by a single-core Intel Xeon E312xx (Sandy Bridge) virtual CPU, 
running under a KVM hypervisor. This shows that even a small virtual machine is built 
on top of physical hardware that has been virtualized and allocated to my instance 
specifically, which is the core principle behind cloud compute services like AWS EC2 
or Azure Virtual Machines.

## Storage Resources
Storage resources refer to the space and systems used to store data, files, and the 
operating system itself. Storage matters in cloud computing because applications and 
users need persistent places to save data, and cloud providers offer multiple types 
of storage (block, object, file) depending on performance and durability needs. In my 
KillerCoda environment, the primary storage is the `/dev/vda1` disk, a 19GB ext4 
filesystem mounted at `/` with about 13GB available. There are also separate partitions 
for `/boot` and `/boot/efi`, which store boot-related files separately from the main 
system. This separation of storage into distinct mounted filesystems reflects how cloud 
providers often separate storage by purpose (e.g., boot volumes vs. data volumes).

## Networking Resources
Networking resources are the components that allow a server to communicate with other 
systems, whether on a private network or over the internet. Networking is essential in 
cloud computing because cloud services are inherently distributed and accessed remotely, 
so reliable connectivity, IP addressing, and routing are what make cloud resources usable 
at all. On my KillerCoda instance, the networking resource is represented by the 
`enp1s0` interface, which has a private IP address of `172.30.1.2/24`. There is also a 
`docker0` virtual bridge interface with its own IP range (`172.17.0.1/16`), which shows 
that networking in a cloud/virtualized environment can involve multiple layers — a 
primary network interface for external connectivity and virtual/internal interfaces 
for containerized services.

## Operating System
The operating system is the software layer that manages hardware resources and provides 
the environment in which applications run. In cloud computing, the OS matters because 
cloud providers typically let users choose their OS image when deploying a virtual 
machine, and the OS determines compatibility, security patching, and available tools. 
My KillerCoda environment runs Ubuntu 24.04.4 LTS (Noble Numbat) with kernel version 
6.8.0-138-generic. This is a common example of how cloud compute instances are 
provisioned from a base OS image, and the kernel version specifically reflects how 
cloud providers keep systems updated with the latest security and performance patches.
