The below is a basic code block for a terraform script

```
terraform {
  # can get the below from the terraform registry
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

# specifies the provider
# can get the below from the terraform registry
provider "aws" {
  region  = "us-west-2"
}

# the below is a resource block
resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}
```

## terraform-resources

this is how you define a resource
```tf
resource "resource_type" "resource_name" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}
```