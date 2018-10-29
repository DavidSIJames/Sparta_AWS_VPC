# Sparta AWS VPC

1) when logged into the AWS Console Homepage, select Services in the navbar
2) click on the VPC link under Networking & content delivery
3) click your VPCs in the nagivation pane on the left hand side
4) click create VPC
5) give your VPC a name
6) enter the CIDR block for your VPC (e.g 10.0.0.0/16) and click the "Yes,Create" button
7) You have created a VPC! however it is empty and doesnt even have a gateway
8) click on internet gateways in the navigation pane
9) click on create internet gateway button
10) enter name of your gateway and create
11) select created gateway, click actions and select attach to VPC
12) select your vpc and click attach
13) click subnets in navigation pane
14) click create subnet
15) enter name of subnet (e.g: DavidsPublicSubnet)
16) select what VPC the subnet is for
17) select what Availability zone you want this subnet to be in
18) enter the CIDR block for the subnet (e.g 10.0.0.0/24), if /16 used for VPC use /24 for subnets
19) click create
20) if you select your subnet in the subnet list you can now see that it is attached to the VPC that you made
21) if you want to create more subnets follow steps 13 - 20 for each subnet
22) newly created subnets are private. To make one of the subnets public, select Route Tables from the navigation pane
23) click create route table,give it a name and select the VPC it is for.
24) select Route table from list and select edit button under Routes tab
25) enter 0.0.0.0/0 into the Destination box and select the VPCs gateway from the Target box. click save
26) select edit button under Subnet assoications tab and click the checkbox of which subnet you want to be public
27) to add application security, select Security groups in the navigation pane
28) click create security group 
29) enter name and description for security group as well as what VPC its for, then click create
30) select security group from list and click edit under inbound rules pane
31) select connection type (http, ssh, etc.), enter 0.0.0.0/0 (for public access) under source, and enter a description.
32) add as much as you need then click save
33) create another security group for private subnet
34) in inbound rules create a custom TCP rule for mongoDB (can be anything else) 
35) in type enter custom TCP Rule, in port range enter the port the application runs on (mongo is 27017)
36) enter public security group into source and description then click save
37) to add network security, click on network ACLs in navigation pane
38) click create Network ACL
39) give it a name and a VPC to work on, then click create
40) your ACL will deny all traffic by default, to change this click the edit button on the inbound rules tab
41) add a rule by clicking the Add another rule.
42) enter the Type, the source and wheter to allow or deny
43) when done click save
44) as ACL is stateless you must declare the outbound rules as well
45) click edit in the outbound rules tab
46) add the same rules as the inbound rules and click save
47) to assoicate the ACL with a subnet click edit on the subnet associations tab
48) select the subnets to be associated with the ACL and then click save




