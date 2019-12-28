# Documentation and helpful link for big data speciality preparation

### Kinesis/Firehose Streaming
* https://aws.amazon.com/blogs/compute/amazon-kinesis-firehose-data-transformation-with-aws-lambda/

* Real world Evidence platform on AWS: https://aws.amazon.com/blogs/big-data/building-a-real-world-evidence-platform-on-aws/

* Scaling Kinesis Stream: https://aws.amazon.com/blogs/big-data/scaling-amazon-kinesis-data-streams-with-aws-application-auto-scaling/

### Kinesis Data flow diagram
![image](https://github.com/nanofaroque/nerd-read/blob/master/aws_big_data_speciality_prep/imges/KDF_to_destination.png)

### Amazon S3
* Etags can ensure integrity of files
    * For simple files(less than 5GB), it is the md5 hash
    * For multi-part uploads, it is more complicated
    
    * As of july 17th 2018, we can scale up to 3500 RPS for PUT and 5500 RPS for GET
    for EACH PREFIX. 
    * >5GB always use multipart
    
### REDSHIFT
![image](https://github.com/nanofaroque/nerd-read/blob/master/aws_big_data_speciality_prep/imges/redshift_slice.png)

![image](https://github.com/nanofaroque/nerd-read/blob/master/aws_big_data_speciality_prep/imges/redshift_distribution.png)

* It is better to split the files for uploading by using COPY command. You dont have to split equal to the number of node but you can split more since each slice can run parallel to process the query(insert or read)
