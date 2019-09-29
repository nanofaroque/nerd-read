## EC2

### Pre-baked EC2
* https://www.journaldev.com/25609/aws-ami-amazon-machine-image

### Load balancers
Application Loadbalancer:

* https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html
* It runs on the application level. 7th layer on OSI

![](https://github.com/nanofaroque/nerd-read/blob/master/aws_solution_architect_prep/notes/ec2/Screen%20Shot%202019-09-23%20at%2011.24.16%20AM.png)

Network Loadbalancer:
A Network Load Balancer functions at the fourth layer of the Open Systems Interconnection (OSI) model. It can handle millions of requests per second. After the load balancer receives a connection request, it selects a target from the target group for the default rule. It attempts to open a TCP connection to the selected target on the port specified in the listener configuration.


### Spot instances
* A Spot Instance is an unused EC2 instance that is available for less than the On-Demand price. Because Spot Instances enable you to request unused EC2 instances at steep discounts, you can lower your Amazon EC2 costs significantly. The hourly price for a Spot Instance is called a Spot price

* Spot instances can be interrupted.
* Default price is on-demand price, you have bid the highest price to get spot instance

### schedule instances
Scheduled instance is a good choice if not interruption is not allowed for a scheduled task.

### Placement groups
When you launch a new EC2 instance, the EC2 service attempts to place the instance in such a way that all of your instances are spread out across underlying hardware to minimize correlated failures. You can use placement groups to influence the placement of a group of interdependent instances to meet the needs of your workload. Depending on the type of workload, you can create a placement group using one of the following placement strategies:

* Cluster – packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of HPC applications.

* Partition – spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka.

* Spread – strictly places a small group of instances across distinct underlying hardware to reduce correlated failures.
