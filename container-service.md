# AWS Container Service

## Container basics
- Containers are a method of OS virtualization

- Allow the packaging and isolation of applications with their enitre runtime environment(process isolation)
#img

### Docker
- `Docker `is software platform that enables you to build , test, and deploy applications quickly

- you run continers on Docker
    - containers are created from a templated called an image
- A `container `has everything a sofware application needs to run.

## Container vs Virtual Machines

- `VM` runs directly on hypervisor but `container` run on any operting system if they have appropriate kernal feature to support docker host software and docker daemon is present.
#img



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

#img

#img


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