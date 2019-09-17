* Amazon Elastic File System (Amazon EFS) provides a simple, scalable,
fully managed elastic NFS file system for use with AWS Cloud services and
on-premises resources.
It is built to scale on demand to petabytes without disrupting applications,
growing and shrinking automatically as you add and remove files, eliminating the
need to provision and manage capacity to accommodate growth.

* Amazon EFS offers two storage classes: the Standard storage class, and the
Infrequent Access storage class (EFS IA). EFS IA provides price/performance
that's cost-optimized for files not accessed every day. By simply enabling EFS
Lifecycle Management on your file system, files not accessed according to the
lifecycle policy you choose will be automatically and transparently moved into
EFS IA. The EFS IA storage class costs only $0.025/GB-month*.

* While workload patterns vary, customers typically find that 80% of files are infrequently
accessed (and suitable for EFS IA), and 20% are actively used (suitable for EFS Standard),
resulting in an effective storage cost as low as $0.08/GB-month*. Amazon EFS
transparently serves files from both storage classes in a common file system namespace.

* Amazon EFS is designed to provide massively parallel shared access to
thousands of Amazon EC2 instances, enabling your applications to achieve
high levels of aggregate throughput and IOPS with consistent low latencies.

* Amazon EFS is well suited to support a broad spectrum of use cases from home
directories to business-critical applications. Customers can use EFS to
lift-and-shift existing enterprise applications to the AWS Cloud.
Other use cases include: big data analytics, web serving and content management,
application development and testing, media and entertainment workflows,
database backups, and container storage.

* Amazon EFS is a regional service storing data within and across multiple 
Availability Zones (AZs) for high availability and durability. Amazon EC2
instances can access your file system across AZs, regions, and VPCs, while
on-premises servers can access using AWS Direct Connect or AWS VPN.
