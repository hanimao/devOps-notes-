

**Edge locations**

- The closer an edge location is to your end user the faster AWS can deliver your content
- Data is stored in local warehouses for quicker access.


**IAM Policies Structure**

Version - version of the policy
id - name of the policy
Statement
Effect - allow or deny access
principle - accounr/usr/role to which this policy applies to
Action - downloading and uploading objects to an S3 bucket
Resource - what the action applies to for ex s3 bucket
condition(optional) - condition for when this policy is in effect. 
for ex this policy only works if the request comes from a certain ip address

![[Screenshot 2025-06-17 at 17.45.14.png]]

AWS CLI 
- a tool that lets you interact with AWS services right away from the terminal
- access AWS from command line interface ( CLI)
- Direct access to the public APIs of AWS service 
- Develop scripts to manage your resources

AWS SDK (Software development Kit)

- Tool that lets you interact with AWS services programmatically by using a programme lang
- What is the SDK? A set of language specific APIs (bunch of prebuilt libraries for diff programming languages that make it easier to work with AWS for ex python, javascript)
- Embedded within your application - you can spin up EC2 instances, upload file to s3 bucket direct from your application code.
- Build powerful cloud integrated applications. 

IAM roles for AWS services
1. Some AWS services will need to peform actions on your behalf - assign permissions to AWS services with IAM roles
2. Common roles - EC2 instances (access s3 dynamo db), Lambda Function roles, Roles for CloudFormation
3. IAM roles gives AWS services temp access to other AWS services

IAM security tools
Manage AWS users and their permissions

1. IAM credentials report (account-level)
- lists all your account users and the status of their credentials.

2. IAM Access Advisor (user-level)
- Shows the service permissions granted to a user and when those services were last accessed. 

**EC2 = Iaas**
- Renting EC2, choose OS and configure it to your need 
- Storing data on virtual drives (EBS) like a hard drive
- Distributing load across machines (ELB) When you have multiple EC2 instances running you have to make sure that the traffic is shared evenly. It helps distribute incoming request to your instances so one machine isnt overloaded.
- Scaling the services using an auto-scaling group (ASG)

**Sizing and Configuration**

-  OS: Linux,Window,Mac OS
- How much compute power and cores (CPU)
- RAM
- How much storage space: Network attached (EBS) - Like a hard drive attached to an EC2. (EFS) - shared storage for multiple EC2. 
  Hardware (EC2 instance store)-hardware level storage thats physically attached to the host machine. When the instance is stopped all the data is lost.
- Network card: speed of the card depending how much traffic you expect + public ip address (your instance can be accessed from the internet)
- firewalls rules:Security group acts as firewalls for your instance. You can set up rules who can access your instance and which traffic can get through
- Bootstrap script/EC2 user data (configure at first launch) - This is a script that runs auto when your instance launches. You can use it to install softwarre, updates etc. 

**EC2 User Data** - automated deployment 

1.  Launching an instance and making sure it is up to date with the latest patches. The user data script takes care of this
2. Install software - deploy engine X OR apache on your instance, instead of doing it manually you can have the user data script handle it.
3. downloading files from internet ex application code, config files. 
4. EC2 user data script runs with the root.

**Choosing the right EC2 instance types**

1. General Purpose - go to instances, ex web servers 


2. Compute Optimized - choose this if you need lots of processing power, gives you extra CPU for heavy cal, batch processing 

3. Memory Optimized - When your app needs a lot of memory/RAM for big data processing, in memory database.

4. Storage Optimized - fast, high throughput storage for if you are dealing with large data sets or running databases that require quick access to storage 

5. Acceleration Computing - GPUs. If you are doing machine learning, video processing

6. HPC (High Performance Computing) - designed for intensive computing tasks that needs fast networking

Example

m5.2xlarge

m= instance class (general purpose)
5= instance generation
large = size within the class. The bigger the size the more resources ex CPU

Security Group

- Control how traffic is allowed into or out of our EC2 instances
- only contain allow rules
- Control which ports are open in your instance. You dont want to expose every port because that will expose your instance to every traffic.
- can reference by IP or by security group
- Set rules that specify what traffic is allowed based on ip addresses.
- Security groups are stateless meaning if you allow inbound traffic you also allow outbund traffic.

Control of inbound access
- ssh access
- database access
- web traffic

Outbound traffic
- controls what your instance is connected to for ex preventing it accessing the internet

If you set up a web server on an EC2 instance (like using Apache, Nginx, or another HTTP server), you would allow **inbound traffic on port 80** because When users visit your website by typing `http://yourdomain.com`, their browsers automatically try to connect to your server using **port 80**.
**You allow inbound traffic on port 80 to let users access your website over HTTP.** Without it, your EC2 instance won’t respond to normal web requests.
The web server listens for incoming requests — typically on **port 80 (HTTP)** or **port 443 (HTTPS)**.
 To allow users (like people visiting your website) to reach your server, **traffic must be allowed into your EC2 instance** on that port.



![[Screenshot 2025-06-21 at 15.14.55.png]]

**Steps**

**Inbound**

1. The SG is filtering traffic based on IP and ports. Any income you request has to match the rules you set up. 
2. Lets say your computer is trying to connect to your EC2 instance on port 22. Since the IP address of your computer is authorised to use port 22 the SG allows this connection
3. You can now secure your SSH into EC2 instance

**Outbound**  - meaning data going out from instance to the internet 

1. Your EC2 instance can make request to any IP address on any pool unless your SG says otherwise. 
2. If your instance needs to download updates of fetched data from external API the outbound traffic will be allowed by default. 

- Security group live outside the EC2 - if traffic is blocked the EC2 instance won't see it.
- Its good practice to have one SG dedicated just for SSH access so you don't affect other rules for web traffic or even app connections.
- If your application is not accessible (time out) then its a security group issue
- If your application gives a "connection refused" error, then its an application error or  service in your instance not running or its not launched
- ALL INBOUND traffic is blocked by default
- ALL OUTBOUND traffic is authorised by default


What if you want to control access between instances and those instances might change ips?

EC2 Instance - using SG1 to manage its inbound traffic.
SG1 not only references other IP it references other Sgs. It authorises SG1,SG2,SG3 to send on port 123. From authorising SG1 you allow any traffic from any instances to SG1, same thing for SG2 and SG3. 

ex
you might want all instances in one Sg a database tier to communicate to to all instances in another sg like app tier. Simplifies the configuraition by using sgs and not ip addresses. 

Why is it useful?
- Managing security easier

Ports



