# CLI USE CASE 1

## Compute with Storage in Network using CLI

1. Create a VPC in any region 
2. Add 3 Subnets 
    Web
    Business
    Data
3. Create 1 t2-micro machine in Web Subnet with public ip enabled
4. Create 1 t2-micro machine in Business Subnent with out public ip
5. Create 1 t2-micro/RDS mysql instance in Data Subnet without public ip
6. Configure NACL such that  
..* Business Tier Allows incoming only from Web not from Data
..* Data Tier Allows incoming only from Business Not from Web
..* Web Tier Allows incoming on port 80, 22 from any where

7. Create a new ebs volume in Web Subnet & Mount it to any folder
8. Create an Efs mount on any folder in all the three ec2 machines
9. Create an s3 bucket with 3 folders web , business , data & sync web tiers ec2 machines home directory to web folder , business tier home directory to business folder & data tier home directory to data folder in s3 bucket