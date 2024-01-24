# AWS Cloud Security 

## AWS Shared Responsibility Model

- aws responsibilities
    - physical security of data centers
    - hardware and software infrastructure
    - network infrastructure
    - virtualization infrastructure
    (example of service managed by aws: 
        - aws lambda,
        - amazon relational database,
        - aws elastic beanstalk
    these are the PaaS(customers doesnot need to manage the underlying infrastructure,aws handles the os ,database,patching,firewall configuration and disaster recovery))

- customer responsibilities
    - amazon elastic compute cloud (amazon ec2) instance os
        - including patching,maintainance
    - applications
        - passwords,role-based access etc,
    - security group configuration
    - os or host-based firewalls
        - including intrusion detection or prevention systems
    - network configurations
    - account management
        - login and permission settings for each users
    (example of services managed by customer:
        - amazon EC2,
        - amazon virtual private cloud(amazon VPC),
        - Amazon Elastic Block Store (Amazon EBS)
    these are the IaaS(Customer has more flexibility over configuring networking and storage settings,customer is responsible for managing more aspects of the security and configures the access controls))


## AWS Identity and Access Management (IAM)

- Use IAM to manage access to AWS resources:
    - A resource is an entity in an AWS account that you can work with.Example resources,An amazon EC2 instance or an amazon s3 bucket.
- Example - Control who can terminate Amazon EC2 instances

- Define fine-grained access rights
    - who can access the resource
    - which resource can be accessed and what can the user do to the resource.
    - How resource can be accessed
- IAM is a no-cost AWS account feature.

### IAM:Essential components
    - IAM user : A person or application that can authenticate with an AWS account.
    - IAM group : A collection of IAM users that are granted identical authorization.(Example:admins,developer,tester)
    - IAM role : Useful mechanism to grant a set of permissions for making aws service requests.(role provides temporary security credentials)
    - IAM policy : The document that defines which resources can be accessed and the level of access to each

### Authenticate as an IAM user to gain access

- type of access the user is permitted to use
    - programmatic access
        - authenticate using
            - access key ID
            - secret access key
            (key pair)
        - provide aws cli and aws sdk access
    - aws management console access
        - authenticate using
            - 12-digit account id or alias
            - IAM user name
            - IAM password
        - if enabled multi-factor authentication (MFA) prompts for an authentication code.

### IAM:Authorization
- Assign permissions by creating an IAM policy.
- Permission determine which resources and operations are allowed:
    - all permissions are implicitly denied by default
    - if something is explicitly deined, it is never allowed
- NOTE: The scope of IAM service configurations is global.Setting apply across all AWS Regions.

### IAM policies
- An IAM policy is a document written in javascript object notation (or visual way to do so) that defines permissions
    - enables fine-grained access control

- Two types of policies - identity-based and resource-based
    - Identity-based policies
        - Attach a policy to any IAM entity
            - An IAM user, An IAM group or An IAM role
        - Policies specify:
            - actions that may be performed by the entity
            - actions that may not be performed by the entity
        - A single policy can be attached to mutiple entites
        - A single entity can have multiple policies attached to it
    - Resource-based policies
        - attached to a resource (such as an ec2, s3 bucket) 


## Securing a new AWS Account

## Securing Accounts
- use of saas like amazon cognito(features like adds user sign-up , sign-in, and access control to your web and mobile applicaitons)
- use of saas like aws shield(features like safeguards(DDos attacks))

## securing Data
- Encryption encodes data with a secret key, which make it unreadable
    - only those who have the secret key can decode the data
    - aws kms (key management service) can manage your secret keys

- aws supports encryption of data at rest
    - data at rest = Data stored physically (on disk or on tape)
    - you can encrypt data stored in any service that is supported by aws kms including
        - amazon S3
        - amazon EBS
        - amazon elastic file system(amazon EFS)
        - amazon RDS managed databases

### encryption of data in transit
    - encryption of data in transit(data moving across a network)
        - tansport layer security(TLS)-Formely SSL
        - aws certificate manager provides a way to manage ,deploy and renew TLS or SSL certificates
    - secure HTTP(HTTPS) creates a secure tunnel
    # img here

### securing amazon s3 buckets and objects

- newly created s3 buckets and objects are private and protected by default

- tools and options for controlling access to s3 data include
    - amazon s3 block public access feature
    - IAM policies: A good option when the user can authenticate using IAM 
    - Bucket policies
    - Acess control lists(ACLs):A legacy access control mechansim
    - AWS Trusted Advisor buckt permission check

## working to Ensure compliance

### AWS complicance programs
- customer are subject to many different security and compliance regulations and requirements

- complicane programs can be broadly categorized
    - Certifications and attestations
        - assessed by a third party , independent auditor
            Examples:ISO 27001,27017,27018 and ISO/IEC 9001
    - laws,regulations and privacy
        - aws provides security feature and legal agreements to support compliance
            Examples: EU general data protection regulation(GDPR),HIPAA

### AWS config
- assess,audit and evaluate the configurations of AWS resources.
- simplify compliance auditing and security analysis.

### AWS artifact
- is a resource for complicance-related information
- provide access to security and compliance reports and select online agreements

