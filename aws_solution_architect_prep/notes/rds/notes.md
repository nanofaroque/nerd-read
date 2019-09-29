# Amazon RDS

## Failover scenario

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
