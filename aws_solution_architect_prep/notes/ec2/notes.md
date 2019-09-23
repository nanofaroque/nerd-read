## EC2

### Pre-baked EC2
* https://www.journaldev.com/25609/aws-ami-amazon-machine-image

### Load balancers
Application Loadbalancer:

* https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html
* It runs on the application level. 7th layer on OSI
* It

Network Loadbalancer:
A Network Load Balancer functions at the fourth layer of the Open Systems Interconnection (OSI) model. It can handle millions of requests per second. After the load balancer receives a connection request, it selects a target from the target group for the default rule. It attempts to open a TCP connection to the selected target on the port specified in the listener configuration.
