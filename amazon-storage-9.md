# Amazon Storage

- AWS offers various storage services
- Scalable & durable

- Key Storage Services
    - ***Amazon S3 (Simple Storage Service)***
        - This is an `object storage service` that offers industry-leading scalabilty,data availability,security and performance.It is commonly used to store and retrieve any amount of data at any time.

        - Amazon S3 Storage Classes
            - ***Amazon S3 Glacier***
                - This is a `low-cost storage service` for archiving and long-term backup of `infrequently accessed data.`    

    - ***Amazon EBS (Elastic Block Store)***
        - This provides block-level storage volumes for use with `Amazon EC2 instance`.It's suitable for database storage, boot volumes, and more.

    
    - ***Amazon EFS (Elastic File System) ***
        - This is a scalable file storage service for use with `Amazon EC2 instances`


## Amazon EBS (Elastic Block Store)

- This provides block-level storage volumes for use with `Amazon EC2 instance`
-` Non Volatile `& automatically `replicated`


- AWS storage options
    -` block storage `which is Amazon EBS
    -` object storage `which is Amazon S3

#img


- Amazon EBS enables you to` create individual storage volumes `and `attach them `to an Amazon EC2 instance

- Uses include -
    - `Boot volumes `and storage for Amazon Elastic Compute Cloud instance
    - `Data storge` with a file system
    - `Database hosts`
    - `Enterprise applications`

- EBS is commonly used for various purposes, including storing data for applications, databases (both relational and NoSQL), and providing storage for EC2 instances

#img

## Lab Overview
#img

    - create an amazon ebs volume
    - attach and mount your volumne to an EC2 instance
    - create a snapshot of your volume
    - create a new volume from your snapshot
    - attach and mount the new volumne to your EC2 instance


## Amazon S3 (Simple Storage Service)

- Amazon S3 is `highly scalable` and widely used `object storeage service.`

- What objects in S3 can be:
    - `Files`
        - text,images,videos,audio files,PDFs,Words,SpreadSheets etc
    - `Databases`
        - Backups or snapshots of databases can be stored as objects in S3
    - `Logs`
    - `Static Website Content`
        - S3 is commonly used to host static website content.
    - `Containers and Images`
        - Container images for services like Docker can be stored in S3.

- S3 is designed to store and retrieve any amount of data from anywhere on the web.

- S3 is an object storage service,meaning it stores data as objects.
    - Each object consists of data, a unique key and metadata.

- S3 stores data as objects in resources that are called `Bucket`.
    - `Bucket` is a fundamental container for storing and organizing objects.
    - It is a top-level container with a `globally unique name ` within the S3 service.

#img

- `path-style` url endpoint is normally used when you need to access objects
- `virtual-hosted-style` url endpoint is used when you are using `bucket as a website` for static data.


- Access the data anywhere thru
    - `aws management console`
    - `aws command line interface`
    - `sdk`

# Amazon EFS (Elastic File System)

- Amazon EFS is a scalable and fully managed file storage service provided by AWS.

- Its simply a file system

- It is designed to provide scalable , elastic and `shared file storage` for use with `Amazon EC2 instances`.

- Also works well for big data and analytics,media processing workflows, content management, web serving etc


#img


#img

#img


# Amazon S3 Glacier

- Amazon S3 Glacier is a `data archiving service` that is designed for `security`,`durability` and an `extremely low cost.`

- In S3 Glacier, data is organized into `vaults` and each valut contains archives. An `archive` is essentially a file and each archive can be up to `40 terabytes` in size.

#img

- use cases
    - media asset archiving
    - healthcare information archiving
    
- to store and access data:
    - restful web services
    - java or .net sdks
    - amazon s3 with lifecyle policies
        #img


#img
