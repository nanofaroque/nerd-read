# Amazon RDS
How RDS works?
![](https://github.com/nanofaroque/nerd-read/blob/master/aws_solution_architect_prep/notes/rds/Screen%20Shot%202019-09-22%20at%2011.16.55%20AM.png)
## Failover scenario
![](https://github.com/nanofaroque/nerd-read/blob/master/aws_solution_architect_prep/notes/rds/Screen%20Shot%202019-09-22%20at%2011.32.13%20AM.png)
### When failover happen?
* An Availability Zone outage
* The primary DB instance fails
* The DB instance's server type is changed
* The operating system of the DB instance is undergoing software patching
* A manual failover of the DB instance was initiated using Reboot with failover

### How to overcome failover?
* In a Multi-AZ deployment, Amazon RDS automatically provisions and maintains a
synchronous standby replica in a different Availability Zone. The primary DB
instance is synchronously replicated across Availability Zones to a standby
replica to provide data redundancy, eliminate I/O freezes, and minimize latency
spikes during system backups
