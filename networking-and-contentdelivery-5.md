# Networking and Content Delivery

## Networking Basics

- IPv4(32bits),IPv6(128bits)

    - 192.0.2.0/24 (IPv4) 
        - 24 tells you that 24 bits are fixed (means class c network)
        - meaning 256 ip address are available for the network
          
![networking1](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/2b9320c1-de61-40d2-99f6-9c0e4496a207)

- OSI model (open systems interconnection) model describes seven layers that compyter systems use to communicate over a network.

![networking2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/2baee9c5-dcd5-4563-95bf-a3636cc6ac83)


## Amazon VPC

- Enables you to provision a `logically isolated` section of the AWS Cloud where you can launch AWS resoruces in a virtual network that you define.
- Gives you `control over your virtual networking ` resources including:
    - selection of ip address range
    - creation of subnets
    - configuration of route tables and network gateways
- Enables you to `customize the network configuration` for you VPC
- enables you to use `multiple layer of security`
- 
![vpc1](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/99300dbd-4be9-4e48-a342-7f74aede914f)

### IP addressing

![vpc2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/1058bb3f-8dc4-493b-82e8-2a84f20ec4b4)

### Reserved IP address

![vpc3](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/ac4d95e2-9042-4479-aec2-117f8801153b)

### Public IP address types
- IP address is private in VPC.
- you can also request public IP address to be assigned to virtual machine when you create a instance 

    - Public IPv4 address
        - manually assigned through an Elastic IP address
        - Automatically assigned throught the auto-assign public IP address settings at the subnet level.

    - Elastic IP address
        - Associated with an AWS account 
        - can be allocated and remapped anytime
        - additional cost might apply


### Elastic network interface

- An elastic network interface is a `virtual network interface` that you can:
    - attach to an instance.
    - detach form the instance and attach to another instance to redirect network traffic.

- Its attribute follow when it is reattached to a new instance.

- Each instance in your VPC has a `default network interface` that is assigned a private IPv4 address from the IPv4 address range of your VPC.
  
![vpc4](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/017d200b-42ec-40a5-a4ae-ceb69b9a7f1a)


## VPC Networking

### Route tables and routes

- A route table contains a set of rules(or routes) that `you can configure ` to direct network traffic from your subnet.
- Each route specifies a destination and a target.(to or from your subnet)
- By default, every route table contains a `local route` for communication within the VPC.
- Each `subnet must be assocaited with a route table` (at most one).

![vpc5](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/83459eac-4458-43b2-a88c-fe1ef7b05771)

`NOTE`
- `Destination`: the packet's final destination

- `Target`: where the packet should go next, to get it one step closer to the intended destination.

    - e.g.

        - You are planning a business trip from the US to Paris.

        - `Destination`: Paris
        - `Target`: US airport, fly to Paris.
      
### Internet Gateway

- An internet gateway is a device that allows you to connect your devices to the Internet.
- In AWS an Internet Gateway is a VPC component that allows communication between the VPC and the Internet.

![vpc6](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/8b0537ad-9ea4-4f6e-bd72-2829f2efe875)

![gateway1](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/925dada8-b8b4-4d9d-87e4-e641a0a16174)


- `NAT Gateways`
    - A NAT gateway is a Network Address Translation (NAT) service. You can use a NAT gateway so that instances in a private subnet can connect to services outside your VPC but external services cannot initiate a connection with those instances.
    - `NOTE` Instance in the private subnet can establish outbound connections to the internet via the public subnet using `NAT`.
  
 ![gateway2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/97d76f75-6f85-4b52-a7e4-3c09656b466d)


### VPC sharing
- allows `multiple aws accounts` to `create` their applicaiton resources , such as amazon ec2 instances, amazon relational database services, amazon redshift clusters and aws lambda function into `shared` ,`centrally-managed` virtual private clouds `(VPCs)`.

![vpcsharing](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/a33047bf-7189-4e04-b199-28563dbd1ee5)

### VPC peering
- A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network.

![vpcpeering](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/eccba992-da3c-485d-8c33-c9eba9fe0852)

### VPC endpoints
- A VPC endpoint enables customers to ` privately connect ` to `supported AWS services` and `VPC endpoint services ` powered by AWS PrivateLink. Amazon VPC instances do not require public IP addresses to communicate with resources of the service. Traffic between an Amazon VPC and a service does not leave the Amazon network.

![vpcendpoints](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/b59f12c8-4f73-4679-a93e-58e73091d055)


### some of advance topic
    - aws site-to-site VPN
    - aws direct connect
    - aws transit gateway

## VPC Security

### Network ACLs
- Networking ACLs manage access to a network. To do this, they provide instructions to switches and routers as to the kinds of traffic that are allowed to interface with the network. They also dictate what each user or device can do once they are inside.
- In a way, an Access control lists (ACLs) is like a guest list at an exclusive club. Only those on the list are allowed in the doors.

![networkacls](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/9008585a-d3de-4810-bfe5-c886c8eb074f)

![acls](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/c8d8e6b7-cec6-4a5c-89e6-499f5b0a1c26)

![acls2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/ee505ccd-82e2-456c-8c95-e2791872993a)


### Security Groups
- A `security group controls the traffic` that is `allowed to reach and leave the resource` that it is associated with.
- For example , after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

![securitygroup1](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/95e820bb-7808-4a04-89e9-dd6a3a2452a5)

![securitygroup3](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/c40ea762-dbd2-4512-bef8-9b585ed1654c)

![securitygroup2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/2824b91b-6c05-4a12-9af3-38bc5ce3742a)


`Note:Security groups and network ACLs are similar in that they allow you to control access to AWS resources within your VPC. But security groups allow you to control inbound and outbound traffic at the instance level, while network ACLs offer similar capabilities at the VPC subnet level. `

![acls vs security group](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/8065e4db-96b2-4a62-9c46-a4a334b7945f)

