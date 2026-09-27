# Types of Cloud Storage

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| Block Storage | Stores data in fixed-size blocks, each with a unique address, similar to a traditional hard drive. The operating system manages how the blocks are organized into files. | Best for structured data that requires fast, low-latency read/write access, such as databases and operating system boot volumes. | AWS EBS (Elastic Block Store) |
| File Storage | Stores data as files organized in a hierarchical folder structure, accessed through standard file system protocols (like NFS or SMB). | Best for shared file access across multiple servers or users, such as shared drives and content management systems. | AWS EFS (Elastic File System) |
| Object Storage | Stores data as individual objects (files plus metadata) in a flat structure, each with a unique identifier, accessed via HTTP APIs. | Best for storing large amounts of unstructured data such as images, videos, backups, and static website content. | AWS S3 (Simple Storage Service) |

## Why Object Storage is Best for Client Photos
Object storage is the best choice for storing the client's user-uploaded images because it can scale to handle millions of files without being limited by a rigid folder structure or fixed storage capacity. Since each photo is stored as an independent object with its own metadata, the system can efficiently manage, retrieve, and serve large volumes of images through simple API calls. Object storage is also more cost-effective and durable for this type of unstructured data compared to block or file storage.
