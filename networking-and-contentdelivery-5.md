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

### IP addressing
### Reserved IP address
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


### Routeee tables and routes

- A route table contains a set of rules(or routes) that `you can configure ` to direct network traffic from your subnet.
- Each route specifies a destination and a target.(to or from your subnet)
- By default, every route table contains a `local route` for communication within the VPC.
- Each `subnet must be assocaited with a route table` (at most one).