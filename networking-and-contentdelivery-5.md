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


### Route tables and routes

- A route table contains a set of rules(or routes) that `you can configure ` to direct network traffic from your subnet.
- Each route specifies a destination and a target.(to or from your subnet)
- By default, every route table contains a `local route` for communication within the VPC.
- Each `subnet must be assocaited with a route table` (at most one).

![vpc5](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/83459eac-4458-43b2-a88c-fe1ef7b05771)

### Internet Gateway

- An internet gateway is a device that allows you to connect your devices to the Internet.
- In AWS an Internet Gateway is a VPC component that allows communication between the VPC and the Internet.

![vpc6](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/8b0537ad-9ea4-4f6e-bd72-2829f2efe875)

- `NAT Gateways`
    - A NAT gateway is a Network Address Translation (NAT) service. You can use a NAT gateway so that instances in a private subnet can connect to services outside your VPC but external services cannot initiate a connection with those instances.
    - `NOTE` Instance in the private subnet can establish outbound connections to the internet via the public subnet using `NAT`.
