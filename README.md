# Lark IT Ansible AWS EC2 Role

Creates AWS EC2 instance with a security group that allows all outbound and a encrypted EBS volume mounted on root. 

## Dependencies
- Assumes a VPC and a subnet exists
- This role is not dependent on any other roles

## Variables
| Variable | Required? | Default Value | Type | Description |
|----------|-----------|---------------|------|-------------|
| ec2_name | Yes | N/A | String | The value of the Name tag for the EC2 instance |
| ec2_image | No | ami-01ed306a12b7d1c96 (CentOS 7) | String | The id of the AMI image to use | 
| ec2_instance_type | Yes | N/A | String | The EC2 instance type or size |
| ec2_subnet_name | Yes | N/A | String | The name of the subnet to be connected to the EC2 instance |
| ec2_root_volume_size | No | 16 | Int | The size of the root EBS volume in Gigabytes |
| ec2_root_volume_delete_on_termination | No | true | Boolean | Whether or not to delete the attached EBS volumes upon instance termination |
| ec2_exact_count | No | 1 | Int | The number of instances to create | 
| ec2_assign_public_ip | No | false | Boolean | Whether to assign a dynamic public IP to the instance, not to be confused with EIP |
| ec2_state | No | present | String | Set to present to create or absent to destroy |
| vpc_key | Yes | N/A | String | The SSH key to install on the instance |
| aws_region | Yes | N/A | String | The AWS region name for the instance, can also be overridden with AWS_REGION environment variable |