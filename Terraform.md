
A tool used to deploy resources in the form of code instead of doing it manually

Benefits
- Easy to replicate
- Easy to scale
- minimises error
- Easy to adjust

What does that actually look like in production environment?

Writing scripts/templates writing it in terraform/cloudformation and then deploying their code to aws/cloud/azure. 

How is Terraform deploying things to aws,cloud or azure?
- Terraform is a cloud agnostic tool. Terraform can deploy to any cloud. This is done through the Terraform registry where it will install certain plugins. It will use certain API calls in order to be able to deploy to 2 different providers.
- Terraform can deploy kubernetes resources, deploy certain things to vault

IaC
- can be stored in version control system such as git to allow you to track changes, rollback to certain versions. 

Infrastructure Orchestration vs Config Management;

**Config Management** - how these tools link in the DevOps space.

ex; **Ansible, Puppet, Chef**

Ansible - configuring your EC2 instances and these servers in order to run certain things such as hosting a wordpress server.


**Infrastructure Orchestration****

ex; **AWS CloudFormation**, **Terraform** 

- arranging in a orderly manner - orchestration
- Using Terraform to deploy EC2 instances - how does a config management tool integrate into this.


Steps
1. Developer-IaC-Plan-Apply
2. Terraform - wants to deploy an EC2 instance 
3. Plan - What your code is trying to do for ex the resources you're trying to create.

Tips
1. When you are configuring IaC it is important to know the implication of your code in a production environment. 
2. Testing and Validating your terraform plan. Don't want to break anything or deleting important resources. Make it aligns with what you are trying to deploy. 
3. Start small with an MVP (minimum viable product) then iterate. Configuring the resources, that you need in order to deploy it into the cloud. 
4. Then you could iterate. Maybe implementing variables, turning your code into a terraform module. 
5. Implement dry software engineering principle. Dry means do not repeat yourself. 
6. Important when it comes to Terraform, with terraform you have modules, things that can be used as templates 

Current state file 
- a record of your existing/up to date infrastructure. Helps ensure idem potency. Your terraform config no matter how many times you run it, it will produce the exact same thing. 
- Will not deploy multiple things
- .tfstate 

Desired state file 
- Changes you are trying to implement - resources you are deploying 
- .tf


How is connection being established between Terraform and AWS?

Terraform Providers

- A plugin that allows you to interact with cloud platforms, services.
- Enables terraform to manage your resources in the cloud.

Terraform Provider code
- Source - your getting the AWS provider from the Hashicorp registry 
- This blocks tells Terraform you are configuring AWS provider.
- Terraform 0.13 - The version AWS is compatible with.

![[Screenshot 2025-06-26 at 12.00.00.png]]

**STEPS;**
1. **Terraform init** 
- Initialising the backend where Terraform stores the state of your infrastructure
-  The terraform state can be stored in a local file on your machine or it can be stored remotely in a storage space S3 so terraform can track your resources properly.
- Downloads your provider. 

2. **Terraform plan** 
- Previewing the changes will make before they happen. 'seeing the future'
- Analysis your config file and compares them to the current state of your infrastructure then generates a plan
![[Screenshot 2025-06-27 at 15.28.20.png]]


+ create: Resources that will be created
+  - update-in-place: Resources that will be modified 
+ destroy: Resources that will be deleted.

2. **Terraform apply**
- Once the plan looks good time to apply!
- Generate another execution plan. 

3. **Terraform Destroy**
- Destroys all remote objects managed by a particular Terraform config.

**Resource Block** 
- used to define a piece of infrastructure (EC2) you want to manage.
- AMI - template for your EC2
- T2.mico - CPU and memory. 
- tags - labels and tags your resources.
- 
![[Screenshot 2025-06-27 at 16.29.50.png]]
Terraform Importing

- What if a resource already exists in your cloud environment? 
- Using terraform import to bring your existing resources you created manually under terraform management and into terraform environment 
Steps
1. First identify the resource in the cloud
2. Create a resource block in Terraform config.