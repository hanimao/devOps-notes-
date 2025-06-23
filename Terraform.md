
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
- Terraform can deploy kubernettes resources, deploy certain things to vault

IaC
- can be stored in version control system such as git to allow you to track changes, rollback to certain versions. 

