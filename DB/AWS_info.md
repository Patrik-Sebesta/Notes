# AWS: SLSP DB Connection
​
1. AWS console: https://eu-west-3.console.aws.amazon.com/console/home?region=eu-west-3#
​
2. RDS: https://eu-west-3.console.aws.amazon.com/rds/home?region=eu-west-3
​
   ![aws-db-01.png](pics/aws-db-01.png)
​
3. choose the right role according [aws repository](https://gitlab.tmloc.com/afs/aws) 
​
   eg.: */home/martin/tm/repos/afs-aws/deployments/slsp/uat1/backend.tf*
​
   ```yaml
   # All necessary variables can be found in output of afs/aws
   # Output values are in format:
   #   customers = {
   #      "customer_name(=BUCKET_NAME)" = "AWS_ACCOUNT_ID"
   
   terraform {
     backend "s3" {
       bucket = "customer-slsp-non-prod"         # BUCKET_NAME is customer account name.
       key    = "slsp-uat1.tfstate" # Name of environment. E.g. test, ift
       region = "eu-west-3"
     }
   }
   
   provider "aws" {
     region                  = "eu-west-3"
     shared_credentials_file = "~/.aws/credentials"
   
     profile = "threatmark"
   
     # AWS_ACCOUNT_ID = The ID of aws_organizations_account
     assume_role {
       role_arn = "arn:aws:iam::376951411065:role/OrganizationAccountAccessRole"
     }
     version = "~> 2.32"
   }
   ```
​
   ![aws-db-02.png](pics/aws-db-02.png)
​
4. Go to DB Instances and pick database you need, in section Connectivity & Port you will find Endpoint you need for connection
​
   ![](pics/aws-db-01.png)
​
5. Connect to Service node of specified customer, there should be mysql  client installed (install if needed) and connect to db with following  command
​
   ```bash
   mysql -u afs_0 -p -h <endpoint_from_console> -P 3306
   # only exception for username are slsp prod databases which use afs_<service>_0 "afs_apps_0" for afs_apps0 db etc.
   ```
​
   *optionally you can also specify db name (afs_core_0) but these do vary  due to old naming convention from openstack days (ie afs_core2,  afs_core112 etc etc.) so if you are not sure just use show databases;*
​
**<u>SLSP:</u>**
​
```bash
mysql -u afs_0 -p -h slsp-uat1.c6q25vlpmh4x.eu-west-3.rds.amazonaws.com -P 3306
```
​
**<u>DB Password eg. path:</u>** https://vault.tmloc.com:8200/ui/vault/secrets/kv/show/v1/afs/slsp/uat1/local/mariadb
