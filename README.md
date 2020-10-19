# terraform-aws-lambda-auto-update-security-group-ips

This repo contains the terraform code to create the necessary resources in order to be able to update a Security Group's rules based on the IPs of an Autoscaling Group in AWS.

This repo's README file is autogenerated using [terraform-docs](https://github.com/terraform-docs/terraform-docs)!

## Lambda Golang Source Code  
https://github.com/karvounis/aws-lambda-auto-update-security-group-ips

## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.13, < 0.14 |
| aws | ~> 3.0 |

## Providers

| Name | Version |
|------|---------|
| aws | ~> 3.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| autoscaling\_group\_name | Autoscaling Group name | `string` | n/a | yes |
| cloudwatch\_event\_rule\_name | Name of the cloudwatch event rule | `string` | n/a | yes |
| enabled | Enables/Disables this module | `bool` | n/a | yes |
| lambda\_function\_name | A unique name for your Lambda Function | `string` | n/a | yes |
| security\_group\_id | ID of the security group to auto update | `string` | n/a | yes |
| lambda\_tags | The tags to be added to the lambda function only | `map(string)` | `{}` | no |
| lifecycle\_hook\_heartbeat\_timeout | Heartbeat timeout for the lifecycle hook | `number` | `3600` | no |
| log\_group\_namespace | Namespace of the log group | `string` | `"/aws/lambda/"` | no |
| log\_group\_retention\_in\_days | Specifies the number of days you want to retain log events in the specified log group. Possible values are: 1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653, and 0. If you select 0, the events in the log group are always retained and never expire. | `number` | `7` | no |
| memory\_size | Amount of memory in MB your Lambda Function can use at runtime. Defaults to 128 | `number` | `128` | no |
| prefix | Prefix all resources with this string | `string` | `"tf-"` | no |
| reserved\_concurrent\_executions | The amount of reserved concurrent executions for this lambda function. A value of 0 disables lambda from being triggered and -1 removes any concurrency limitations. Defaults to Unreserved Concurrency Limits -1 | `number` | `-1` | no |
| tags | The tags to be added to all the resources | `map(string)` | `{}` | no |
| timeout | The amount of time your Lambda Function has to run in seconds. Defaults to 10 | `number` | `10` | no |
| vpc\_security\_group\_ids | List of security group ids | `list(string)` | `null` | no |
| vpc\_subnet\_ids | List of subnet ids | `list(string)` | `null` | no |

## Outputs

| Name | Description |
|------|-------------|
| this\_lambda\_cloudwatch\_event\_rule\_arn | The ARN of the Cloudwatch Event Rule |
| this\_lambda\_cloudwatch\_event\_rule\_name | The name of the Cloudwatch Event Rule |
| this\_lambda\_cloudwatch\_log\_group\_arn | The ARN of the Cloudwatch Log Group |
| this\_lambda\_function\_arn | The ARN of the Lambda Function |
| this\_lambda\_function\_invoke\_arn | The Invoke ARN of the Lambda Function |
| this\_lambda\_function\_kms\_key\_arn | The ARN for the KMS encryption key of Lambda Function |
| this\_lambda\_function\_last\_modified | The date Lambda Function resource was last modified |
| this\_lambda\_function\_name | The name of the Lambda Function |
| this\_lambda\_function\_qualified\_arn | The ARN identifying your Lambda Function Version |
| this\_lambda\_function\_source\_code\_hash | Base64-encoded representation of raw SHA-256 sum of the zip file |
| this\_lambda\_function\_source\_code\_size | The size in bytes of the function .zip file |
| this\_lambda\_function\_version | Latest published version of Lambda Function |
| this\_lambda\_role\_arn | The ARN of the IAM role created for the Lambda Function |
| this\_lambda\_role\_name | The name of the IAM role created for the Lambda Function |

