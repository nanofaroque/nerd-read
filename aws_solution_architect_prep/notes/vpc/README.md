#VPC

## VPC peering
* You can not create a VPC peering with overlapping IPV4 CIDR block

## Networking
Layer 3-> the Network layer, allows/denies traffic based on IPs and ranges.
Layer 4-> the Transport layer will allow/deny traffic based on TCP/UPD and port information.

![](https://github.com/nanofaroque/nerd-read/blob/master/aws_solution_architect_prep/notes/vpc/osi_model.png)

* https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/

* NACL(Network access control list)-> you have to create your own inbound and outbound rules explicitly

* Security Group-> you have to create your own inbound policy only and outbound is automatically created

* Each VPC comes with one automatic route table

* VPC has a virtual router called vpc router. It is highly available and scalable in whatever scale
* Internet Gateway is highly scalable and available by design

## Bastion Host/ Jumbo Box
* A host sits in the perimeter of VPC
* Bastion host act as a trusted authority for the VPC


## NAT Network address translation
* Static NAT -> a private IP mapped to public IP (Like an internet gateway does)
  * When the IGW receives a packet from a resource with a public IP, it will adjust the packets. It replaces the private IP with the associated public IP address. This process is known as SNAT.
* Dynamic NAT -> group of private IP mapped to a public


### VPC flow logs
* VPC flow logs can show IP traffic and metadata
* But to show the content, you need IP snipper 

### NAT Gateway
* You must also specify an Elastic IP address to associate with the NAT gateway when you create it. The Elastic IP address cannot be changed once you associate it with the NAT Gateway. After you've created a NAT gateway, you can not change it. 
### VPC CIDR block
![](https://github.com/nanofaroque/nerd-read/blob/master/aws_solution_architect_prep/notes/vpc/Screen%20Shot%202021-03-31%20at%2012.44.46%20AM.png)
https://www.youtube.com/watch?v=z07HTSzzp3o

IPv6 Subnetting: 
https://www.youtube.com/watch?v=UIGVPvxnCtk&t=460s&ab_channel=itfreetraining
