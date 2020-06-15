# EBS
## Encryption
* You can now encrypt data stored on an EBS volume at rest and in motion by setting a single option.

* The encryption occurs on the servers that host the EC2 instances, providing encryption of data as it moves between EC2 instances and EBS storage.

* Adding encryption to a provisioned IOPS (PIOPS) volume will not affect the provisioned performance

* The snapshots that you take of an encrypted EBS volume are also encrypted and can be moved between AWS Regions as needed. You cannot share encrypted snapshots with other AWS accounts and you cannot make them public.

* you cannot enable encryption for an existing EBS volume

* When you launch an instance, the root device volume contains the image used to boot the instance. When we introduced Amazon EC2, all AMIs were backed by Amazon EC2 instance store, which means the root device for an instance launched from the AMI is an instance store volume created from a template stored in Amazon S3. After we introduced Amazon EBS, we introduced AMIs that are backed by Amazon EBS. This means that the root device for an instance launched from the AMI is an Amazon EBS volume created from an Amazon EBS snapshot.

You can choose between AMIs backed by Amazon EC2 instance store and AMIs backed by Amazon EBS. We recommend that you use AMIs backed by Amazon EBS, because they launch faster and use persistent storage.

### Attaching EBS volume and mount a directory
* Storing data with EBS persistently: https://angus.readthedocs.io/en/2014/amazon/setting-up-an-ebs-volume.html
