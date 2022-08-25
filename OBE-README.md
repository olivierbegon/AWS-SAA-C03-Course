## 0. IAM

- IAM is a globally resilient service, any data is secure accross all regions.
- Max 2 Access Key per user


## 1.2. AWS-Fundamentals

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

#### 1.2.5.5. AMI (Server Image)

AMI can be used to create an instance or can be created from an instance.
AMIs in one region are not available from other regions.

Contains:

- Permissions: controls which accounts can and can't use the AMI.

  - Public - Anyone can launch it.

  - Owner - Implicit allow, only the owner can use it to spin up new instances

  - Explicit - Owner grants access to AMI for specific AWS accounts

- Root Volume: contains the **Boot Volume**

- Block Device Mapping: links the volumes that the AMI has and
how they're presented to the operating system. Determines which volume is a
boot volume and which volume is a data volume.
