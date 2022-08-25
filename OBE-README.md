## 0. IAM

- IAM is a globally resilient service, any data is secure accross all regions.
- Max 2 Access Key per user


1.2.4. AWS Default VPC
VPC is a virtual network inside of AWS. A VPC is within 1 account and 1 region which makes it regionally resilient. A VPC is private and isolated until decided otherwise.

One default VPC per region. Can have many custom VPCs which are all private by default.

1.2.4.1. Default VPC Facts
VPC CIDR - defines start and end ranges of the VPC. IP CIDR of a default VPC is always: **172.31.0.0/16**

Configured to have one subnet in each AZ in the region by default.

Subnets are given one section of the IP ranges for the default service. They are configured to provide anything that is deployed inside those subnets with public IPv4 addresses.

In general do not use the Default VPC in a region because it is not flexible.

Default VPC is large because it uses the /16 range. A subnet is smaller such as /20 The higher the / number is, the smaller the grouping.

Two /17's will fit into a /16, sixteen /20 subnets can fit into one /16.

Default VPC comes with default IG, NACL, SG. 

Can be removed and recreated

Subnet assigns public IPs
