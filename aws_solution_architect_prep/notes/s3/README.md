## S3 notes

### Understanding S3 Encryption
* https://jgmsoftware.co.uk/2018/10/15/understanding-aws-s3-encryption/

* if you enable versioning in a bucket, you can never disable it.
you can only suspend it.

* if you delete a bucket with versioning enable, you mark for delete.

* Signed URL: https://advancedweb.hu/2018/10/30/s3_signed_urls/

### Scaling S3
CRR(Cross Regional Replication) is one way only between one source and one destination bucket, so this is not a workable solution.


### Good FAQ
* https://www.amazonaws.cn/en/s3/faqs/

### S3 performance improvement

* https://aws.amazon.com/blogs/aws/amazon-s3-performance-tips-tricks-seattle-hiring-event/

### S3 Transfer acceleration
* Amazon S3 Transfer Acceleration enables fast, easy, and secure transfers of files over long distances between your client and an S3 bucket

### Why Use Amazon S3 Transfer Acceleration?
You might want to use Transfer Acceleration on a bucket for various reasons,
including the following:

* You have customers that upload to a centralized bucket from all over the world.
* You transfer gigabytes to terabytes of data on a regular basis across continents.
* You are unable to utilize all of your available bandwidth over the Internet
when uploading to Amazon S3.

### Replication
* To support replication, versioning on the both bucket has to be enabled 
