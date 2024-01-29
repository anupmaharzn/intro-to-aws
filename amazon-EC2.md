# Amazon Elastic Compute Cloud

 - Topics we gonna cover
    - Amazon EC2
    - Elastic Load Balancing (ELB)
    - Amazon EC2 Auto Scaling

- Other Compute services
    ![compute1](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/10591926-249c-451f-8b99-b96691524e2a)


## Amazon EC2

- Infrastructure as a service (Iaas)
- Instance based
- Virtual machnies (referred to as EC2 instances)
- Provision virtual machines that you can manage as you choose.
- Lauch instances from Amazon machine Images (AMI)
- you can control traffic to and from instances by using security group.

### 9 key decisions to make when you create an EC2 instance

- 1. **`AMI`** (Amaon Machine Image)
    - template that is used to create an instance (contains windows or linux operating system)
    - often also has some software pre-installed

      
- 2. **`Instance Type`**
    - the instance type that you choose determines 
        - Memory(RAM)
        - Processing power (CPU)
        - Disk space and disk type (Storage)
        - Network performance
          
     ![compute2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/5bbe2503-5086-4f20-a985-7237d6f71621)

     ![compute3](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/a56b6094-730d-42a2-b079-21a8a77e5bda)

- 3. **`Network settings`**
    - Network location where EC2 should be deployed.
    - Where should the instance be deployed?
        - Identify the VPC and optionlly the subnet.(if not assigned i will deployed in default VPC)
    - Should a public IP address be automatically assigned?
        - To make it internet-accessible.
          
- 4. **`IAM role`**
    - Will software on the EC2 instance need to interact with other AWS services ?
        - if yes, attach an appropriate IAM Role
    - An AWS identity and Access Management (IAM) role that is `attached `to an `EC2 instance `is kept in an `instance profile`.
    - you can also attach a role to instance that already exists.
      
      ![compute4](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/501a8178-b944-4519-9cd9-91fe49004047)

- 5. **`User data`**
    - Optionally specify a user data script at intance launch.
    - Use `user data` scripts to customize the runtime environment of your instance.
        - Script executes the first time the instance starts
          
    ![compute5](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/fde73237-50d1-4f6b-981b-6d687a61d7ce)

- 6. **`Storage options`**
    - Configure the `root volume`
        - where the guest OS is installed
    - For each volume,specify
        - the size of the disk (in GB)
        - the volume type
            - SSDs or HDDs
        - the volume will be deleted when the instance is terminated
    - Storage options
        - Amazon Elastic Block Store (amazon EBS)
            - block-level storage volumes
            - `you can stop the instance and star it again,and the data will still be there `
        - Amazon EC2 `Instance Store`
            - storage is provided on disks that are attached to the host computer where the EC2 instance is running.
            - `if the instance stops,data stored here is deleted.`
        - Other options for storage(not for the root volume)
            - Mount an Amazon Elastic File System (Amazon EFS)
            - Connect to Amazon Simple Storage Service (Amazon S3)
              
![compute6](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/91aa22de-9adb-4432-b6e3-6441638ced61)


- 7. **`Tags`**
    - A tag is label that you can assign to an AWS resource.
        - consists of a key and an optional value
    - Tagging is how you can attach metadata to an EC2 instance.

- 8.**`Security group`**
    - A security group is a set of firewall rules that control traffice to the instance
    
- 9. **`Key Pair`**
    - At instance launch , you specify an existing key pair or create a new key pair
    - A key pair consists of
        - A `public key `that `aws stores `
        - A `private key file` (Eg .pem file) that `you store`
    - It enables secure connections to the instance
    - For Windows AMIs
        - use the private key to obtain the admin password that you need to log in to your instance
    - For Linux AMIs
        - use the private key to use SSH to securely connect to you instance
    

### Another option to launch an EC2 instance with AWS CLI

![compute7](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/eabd4ab1-910b-49c2-a4be-b40d55e2a79f)


### Amazon EC2 instance lifecycle

![compute8](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/780bc146-687f-4b6f-9eeb-2955ab8ce122)


### Consider using an Elastic IP address

- `Rebooting `an instance will `not change `any IP address or DNS hostnames
- when an instance is `stopped `and then `started `again
    - `the public ipv4 address and exteranl DNS hostname will change`
    - `the private ipv4 address and internal DNS hostname do not change.`

- If you require a `persistent public IP address`
    - Associate an `Elastic IP address `with the instance.

- Elastic IP address characteristics
    - can be associated with instances in the Region as needed.
    - reamins allocated to you account until you choose to release it.

### EC2 instance metadata
- instance metadata is data about your instance
- while you are conneted to the instance, you can view it
    - in a browser: `` http://169.254.169.254/latest/meta-data/``
    - in a terminal window: ``curl http://169.254.169.254/latest/meta-data/``

### Lab Overview

![ec2-lab](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/91b7472c-51e1-42b6-ae91-fdb363259f61)


    
## Elastic Load Balancer

- Elastic Load Balancing (ELB) automatically distributes incoming application traffic across multiple targets and virtual appliances in one or more availability zone (AZ)

    - `Application Load Balancer`
        - ALB operates at the application layer(layer 7) of the OSI model and is best sutied for ditributing HTTP/HTTPS, gRPC,Websockets.
   ![loadbalancer1](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/b837b05b-cbdc-43d6-b5d9-1a924af605b9)
    - `Gateway Load Balancer`
        - GLB is designed fro routing traffic to third-party secrity appliances like firewalls and intrusion detection systems.
    - `Network Load Balancer`
        - NLB operates at the transport layer (layer 4) and is designed for handling TCP,UDP and TLS traffic.



## Application Load Balancer for EC2 instance

- To create a load balancer using the AWS Management Console, complete the following tasks.

 - Step 1: Configure a target group
 - Step 2: Register targets
 - Step 3: Configure a load balancer and a listener
 - Step 4: Test the load balancer

![loadbalancer2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/1e0b9e05-d0e7-4f01-9279-666f863894f3)


**Link for more detail**: - `https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-application-load-balancer.html`

- `Target Group`
    - Target groupos route request to individual registered targets, such as EC2 instanaces,using the protocol and port numbers that you specify.
    - Each target group is used to route requests to one or more registered targets.
- **`NOTE`**
    - ** when we create application load balancer we need to have default + another new security group for incomming traffice from http port 80 (allow http request) or any other internet access **
### Application Load Balancer Practise

![applicationloadbalacer-practise](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/d772154f-ca12-4582-9fdd-0ad766bd633f)

## AWS EC2 Auto Scaling
    
- `Auto Scaling Groups`

- Amazon EC2 auto scaling helps you maintain application availability and allows you to `dynamically adjust `the `capacity` of your Amazon EC2 instances based on the demand for your applications.

- commonly used for following secnarios:
    - maintaining application availability
    - cost optimization
    - fault tolerance
    - elasticity: scale seamlessly 

#img

- **For More Detail**
    - `https://docs.aws.amazon.com/autoscaling/ec2/userguide/get-started-with-ec2-auto-scaling.html`


- `NOTE`
    - Instances of EC2 are typically created and managed using `Auto Scaling Policies`
    - The Purpose of Amazon EC2 auto scaling is to autmatically adjust the number of instances in an `auto scaling group `based on `changes in demand `or other specified condition.
- `While create the instance from autoscaling group we need **Lauch Template**`
- `Amazon EC2 Launch Templates` provide a way to specify the configuration of an EC2 instance in a resuable format.
    - A lauch template includes settings such as the
        - `AMI`
        - `instance type`
        - `key pair`
        - `security groups`
        - `other launch configuration parameters`

- `we just have to create one lauch template and auto scaling will automatically scale that instance into multiple instance`

### Practise this Architecture

#img