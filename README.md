# Locsut Terraform AWS :computer: :cloud:

This repository contains Terraform configurations and a Locust file to create a Locust instance on AWS to execute load tests. ⚡️

## Setup

### 1. AWS Authentication :key:

Before using this repository, you need to authenticate with AWS. You can either export your AWS access key and secret access key in your terminal:

```bash
export AWS_ACCESS_KEY_ID=AKIAXXXXXXXXXXXXXXXX
export AWS_SECRET_ACCESS_KEY=T9HyXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

### 2. Configure your provisioning :wrench:

In the variables.tf file, you need to configure several variables to customize your provisioning:

- node_size: to define the number of nodes you want to create.
- loadtest_dir_source: to define the location and file of your Locust plan script.
- locust_plan_filename: to define the name of your Locust plan file.
- subnet_name: to provide the correct subnet name in the variable file.


```shell
variable "node_size" {
    description = "Size of total nodes"
    default = 2
}

variable "loadtest_dir_source" {
    default = "plan/"
}

variable "locust_plan_filename" {
    default = "basic.py"
}

variable "subnet_name" {
    default = "subnet-prd-a"
    description = "Subnet name"
}
```

## Usage :hammer:

### 1. Execute Terraform :rocket:
To create the infrastructure for your Locust instance, you need to execute the following commands on your terminal or CLI:

```shell
terraform init
terraform apply --auto-approve
```

### 4. Access UI :computer:
Once the process completes, you can access the UI to load Locust and perform your load tests.

### 5. Cleanup :wastebasket:
Execute the following command to delete all AWS resources that were created:

```shell
terraform destroy --auto-approve
```

##### More information :books:
For more information about this repository and how to use it, please refer to the following resources:

[Terraform aws-get-started >> install-terraform-on-linux :link:](https://learn.hashicorp.com/tutorials/terraform/install-cli?


## 📝 License

Copyright © 2023 [tooniez](https://github.com/tooniez). <br />
This project is [MIT](https://github.com/tooniez/locust-terraform-aws/blob/main/LICENSE) licensed.















