# tf-module-regions
create a module to be used twice and set modules in different regions

## Description
Create a module, create code using this module twice (in different regions).
Here we'll create a security group in Frankfurt and Stockholm

## Pre-requirements

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 
* [Terraform cli](https://learn.hashicorp.com/tutorials/terraform/install-cli)
* [AWS account and AWS Access Credentials](https://aws.amazon.com/account/)

## How to use this repo

- Clone
- Run
- Cleanup

---

### Clone the repo

```
git clone https://github.com/ayahmuhamed/tf-module-regions
```

### Change directory

```
cd tf-module-regions
```

### Run

* Init:

```
terraform init
```

_sample_:

```
terraform init

```

* Apply:

```
terraform apply
```

_sample_:

```
terraform apply

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:



Outputs:



* Confirm the SGs have been created

```
aws ec2 describe-security-groups --filter --group-ids $(terraform output -raw central-sg-id) --region=eu-central-1
aws ec2 describe-security-groups --filter --group-ids $(terraform output -raw north-sg-id) --region=eu-north-1
```

_sample_:

```

```

### Cleanup

```
terraform destroy
```

_sample_:

```

```

