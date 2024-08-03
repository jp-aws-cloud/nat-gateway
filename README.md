# Network Address Translation (NAT)

A `NAT` gateway is a Network Address Translation (NAT) service. You can use a NAT gateway so that instances in a private subnet can connect to services outside your VPC but external services cannot initiate a connection with those instances.

When you create a NAT gateway, you specify one of the following connectivity types:

1. Public – (Default):
   - Instances in private subnets can connect to the internet through a public NAT gateway, but cannot receive unsolicited inbound connections from the internet.
   - You create a public NAT gateway in a public subnet and must associate an elastic IP address with the NAT gateway at creation.
   - You route traffic from the NAT gateway to the internet gateway for the VPC.
   - Alternatively, you can use a public NAT gateway to connect to other VPCs or your on-premises network.

In this case, you route traffic from the NAT gateway through a transit gateway or a virtual private gateway.

2. Private –
   - Instances in private subnets can connect to other VPCs or your on-premises network through a private NAT gateway.
   - You can route traffic from the NAT gateway through a transit gateway or a virtual private gateway.
   - You cannot associate an elastic IP address with a private NAT gateway.
   - You can attach an internet gateway to a VPC with a private NAT gateway, but if you route traffic from the private NAT gateway to the internet gateway, the internet gateway drops the traffic.
