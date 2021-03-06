# mail-server

Creates a Mail Server in Aws. By default, Overlord will also use the iRedMail script to configure the mail server.

# Example

```hcl
module "create_mail_server" {
  source = "./modules/aws/mail-server"

  vpc_id = "<VPC ID>"
  subnet_id = "<Subnet ID>"
  instance_type = "t2.micro"
}
```

# Arguments

| Name                      | Required | Value Type | Description
|---------------------------| -------- | ---------- | -----------
|`vpc_id`                   | Yes      | String     | ID of VPC to create instance in.
|`subnet_id`                | Yes      | String     | Subnet ID to create instance in.
|`count`                    | No       | Integer    | Number of instances to launch. Defaults to 1.
|`instance_type`            | No       | String     | Instance type to launch. Defaults to "t2.medium"
|`install`                  | No       | List       | Scripts to run on instance creation. Defaults to "./scripts/core_deps.sh".

# Outputs

| Name                      | Value Type | Description
|---------------------------| ---------- | -----------
|`ips`                      | List       | IPs of created instances.
