# AWS Global Infrastructure 

### AWS Regions

- An aws regions is a geographical area.
    - Data replication across regions is controlled by you.

    - Communication between regions uses aws backbone network infrastructure.

- A region typically consists of two or more Availability zone.

- determine the right region for your services,applications and data based on these factors

### Availability Zones

- Each regions has multiple Availablilty Zones.
- Each Availability Zone is fully isolated partition of the AWS infrastructure.
    - There are currently 69 Availability Zones worldwide
    - Availability zones consist of discrete data centers
    - They are designed for fault isolation.

![availability zones](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/0eaa7151-dfea-4b54-bd9d-25497cf3c4f5)
    
### AWS data centers

- Aws data centers are deigned for security.
- A data center typically has  50000 to 80000 physical servers.


### Points of Presense

- aws provides a global network of 187 points of presence locations.
- consists of 176 edge locations and 11 regional edge caches.
- used with amazon cloudfront
    - a global content delivery network(CDN) that delivers content to end users with reduced latency.
    (example: web contents is stored on CDN servers geographically closer to the users and reaches their computer much faster)

### Aws infrastructure features
- elasticity and scalability
- fault tolerance
- high availabilty
