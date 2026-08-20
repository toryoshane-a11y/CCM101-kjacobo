# Laboratory Activity 2: Build the Cloud Infrastructure Blueprint

## Mission Overview
In this laboratory activity, I investigated the components of cloud infrastructure 
by exploring a Linux server hosted on the KillerCoda Playground. The goal was to 
simulate the planning phase of a cloud deployment by identifying compute, storage, 
networking, and identity resources, comparing services across major cloud providers, 
and documenting a simple cloud architecture design.

## Objectives
- Explain the major components of cloud infrastructure.
- Investigate the hardware and software resources available in a Linux environment.
- Differentiate compute, storage, networking, and identity resources.
- Interpret the relationship between cloud infrastructure components.
- Create professional technical documentation using Markdown.
- Continue building a structured GitHub Cloud Computing Portfolio.

## Cloud Infrastructure Components
- **Compute Resources:** Investigated using `lscpu` and `nproc`, revealing a 
  single-core Intel Xeon E312xx virtual CPU running under a KVM hypervisor.
- **Storage Resources:** Investigated using `df -h` and `mount`, showing a 19GB 
  ext4 root filesystem (`/dev/vda1`) plus separate boot partitions.
- **Networking Resources:** Investigated using `hostname` and `ip a`, showing a 
  private IP address (`172.30.1.2`) assigned to the `enp1s0` interface.
- **Operating System:** Investigated using `cat /etc/os-release` and `uname -r`, 
  showing Ubuntu 24.04.4 LTS running kernel version 6.8.0-138-generic.

## Tools Used
- KillerCoda Playground (Ubuntu 24.04 LTS Linux environment)
- Git and GitHub for version control and portfolio hosting
- draw.io for creating the cloud architecture diagram
- Markdown for technical documentation

## Linux Commands Executed
| Command | Purpose |
|---|---|
| `cat /etc/os-release` | Identify the operating system |
| `uname -r` | Check the kernel version |
| `lscpu` | View CPU model and architecture |
| `nproc` | Count available CPU cores |
| `free -h` | Check total and available RAM |
| `df -h` | Check disk capacity and usage |
| `mount \| column -t` | List mounted filesystems |
| `hostname` | Display the system hostname |
| `ip a` | Display network interfaces and IP addresses |

## Skills Learned
- How to inspect a Linux server's hardware and software specifications using 
  built-in system commands.
- How to relate raw system information to real-world cloud infrastructure concepts 
  (compute, storage, networking, IAM).
- How to compare equivalent services across AWS, Azure, and GCP.
- How to design a basic cloud architecture diagram.
- How to manage a technical portfolio using Git and GitHub, including authentication 
  with a Personal Access Token.

## Challenges Encountered
- Initially had trouble authenticating with GitHub since password-based git push is 
  no longer supported; resolved this by generating and using a Personal Access Token.
- Needed to set up Git's global username/email configuration on a new Linux user 
  account before commits would work.
- Had to think through how to translate raw Linux command output into cloud 
  infrastructure concepts covered in the course material.
