# Mission Reflection

**1. Why is object storage better suited for storing millions of photos compared to a traditional block storage hard drive?**

Object storage is better suited for storing millions of photos because it is designed 
to scale massively without the limitations of a fixed folder hierarchy or drive 
capacity. Each photo is stored as an independent object along with its metadata, 
making it easy to retrieve and manage files individually through simple API calls. 
Block storage, on the other hand, is optimized for structured, high-performance 
read/write operations like databases, not for storing huge volumes of unstructured 
files like images.

**2. How did using Docker make it easier to deploy the MinIO storage server?**

Docker made deploying MinIO much easier because I didn't need to manually install or 
configure the software on the host machine. A single `docker run` command downloaded 
the MinIO image, set up the environment variables for authentication, and started the 
server with both the API and web console ports exposed. This meant the entire object 
storage server was up and running in seconds, without complicated setup steps.

**3. What is a "bucket" in the context of cloud storage?**

A bucket is a container used in object storage to organize and store objects, similar 
to a top-level folder. In this lab, the `client-photos` bucket was created to hold all 
of the client's uploaded images. Buckets also allow administrators to apply access 
policies, permissions, and configurations that apply to everything stored inside them.

**4. How do you think large enterprise companies ensure their object storage data is not lost if the physical server crashes?**

Large enterprise companies typically use data replication and redundancy across 
multiple physical servers and even multiple geographic data centers. This means that 
if one server or location fails, copies of the data still exist elsewhere and can be 
retrieved without loss. Cloud providers like AWS also offer built-in durability 
guarantees by automatically storing multiple copies of every object across different 
storage devices.

**5. How is your confidence in navigating the Linux command line growing?**

My confidence in navigating the Linux command line has grown significantly throughout 
these laboratory activities. I am now comfortable running system inspection commands, 
managing Docker containers, and troubleshooting permission issues, which are all 
practical skills I did not have before starting this course.
