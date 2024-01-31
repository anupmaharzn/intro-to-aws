# AWS Container Service

## Container basics
- Containers are a method of OS virtualization

- Allow the packaging and isolation of applications with their enitre runtime environment(process isolation)
  
![container](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/b8fb5dfc-4a3f-45be-9a97-ebad6d77f799)


### Docker
- `Docker `is software platform that enables you to build , test, and deploy applications quickly

- you run continers on Docker
    - containers are created from a templated called an image
- A `container `has everything a sofware application needs to run.

## Container vs Virtual Machines

- `VM` runs directly on hypervisor but `container` run on any operting system if they have appropriate kernal feature to support docker host software and docker daemon is present.
- 
![container1](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/4f86ed97-b591-4f28-8d47-d134eb014dce)




## Amazon Elastic Container Service (Amazon ECS)

- Amazon Elastic Container Service 
    - A highly scalable , fast , container Management service

- key benefits
    - orchestrates the running of Docker containers
    - maintains and scales the fleet of nodes that run containers

- integrated with deatures that are familiar to Amazon EC2 service users - 
    - Elastic Load Balancing
    - Amazon EC2 security groups
    - Amazon EBS volumes
    - IAM roles

![container2](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/8a6b6781-08fe-4309-9b4b-99825b0f74c5)


![container3](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/56c855b6-232a-4d17-835d-59ac194d849d)



## Kubernetes
- Kubernetes is open source software for container orchestration
    - Deploy and manage containerized application at scale

- complements Docker
    - Docker enables you to run multiple containers on a single OS host.
    - Kubernetes orchestrates multiple Docker hosts(nodes)

- automates
    - container provisioning
    - networking 
    - load distribution
    - scaling


## Amazon Elastic Kubernetes Services (Amazon EKS)

- Amazon EKS
    - enables you to run kubernetes on aws
    - supports linux and windows containers

- use amazon eks to 
    - manage cluster of amazon EC2 compute instances
    - run containers that are orchestrated by kubernates on those instance.

## Amazon Elastic Container Registry

- Amazon ECR is a fully managed Docker container registry that makes it easy for developers to store,manage and deploy docker container images.

![container4](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/a2ee8c18-5b0c-4917-a83e-5f0349901a35)
