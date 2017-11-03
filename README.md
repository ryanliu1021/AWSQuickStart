## Aviatrix - AWS Quickstart script for CloudFormation

### Description
This CloudFormation script will create the following:

* One Aviatrix Controller EC2 Instance (named AviatrixController).
* One Aviatrix Security Group (named AviatrixSecurityGroup).
* One Aviatrix Role for EC2 (named aviatrix-role-ec2) with corresponding role policy (named aviatrix-assume-role-policy). [Click here for this policy details](https://s3-us-west-2.amazonaws.com/aviatrix-download/iam_assume_role_policy.txt)
* One Aviatrix Role for Apps (named aviatrix-role-app) with corresponding role policy (named aviatrix-app-policy) [Click here for this policy details](https://s3-us-west-2.amazonaws.com/aviatrix-download/IAM_access_policy_for_CloudN.txt)

> Quickstart lite:
>
If you only need to create the roles and policies, and plan to manually start the Aviatrix controller instance, use the Quickstart lite version. For lite version instructions click [here](./README-lite.md)

### Pre-requisites:

* An existing VPC.
* A public subnet on that VPC.
* An internet gateway attached to the VPC.
* KeyPair.
* In order to use the Aviatrix Controller first you need to accept the terms and subscribe to it in the AWS Marketplace.  Click [here](https://aws.amazon.com/marketplace/pp?sku=zemc6exdso42eps9ki88l9za)

> Note: this script does **NOT** check that the subnet selected is on the same VPC selected, you need to make sure you are selecting the right combination.

> Note 2: this script does **NOT** check that an Internet Gateway is created and attached to the VPC. If this is missing there will be no way to access the Aviatrix Controller.

### Step by step Procedure:

1. Access your AWS Console.

2. Under Services -> Management Tools.
```
 Select CloudFormation.
 ```
 OR
```
 Search for CloudFormation.
```

3. At the CloudFormation page, Select Create stack.

4. On the next screen, Select "Upload a template to Amazon S3".
```
  Choose file -> aviatrix-aws-quickstart.json
```

  > Note: the [aviatrix-aws-quickstart.json file](https://github.com/AviatrixSystems/AWSQuickStart/blob/master/aviatrix-aws-quickstart.json) can be found in this project, click [here](https://raw.githubusercontent.com/AviatrixSystems/AWSQuickStart/master/aviatrix-aws-quickstart.json)   for direct download.

5. Click next.

6. On the Stack Name textbox, Name your Stack -> Something like *AviatrixController*

7. Select the following parameters:

  * VPC
  * Subnet
  * KeyPair Name
  * Aviatrix IAMRole (select no if this is the first time you are launching Aviatrix Controller, i.e., no aviatrix-role-ec2 IAM role and associated security policies have been created.)

8. Click next

9. Especify your options/tags/permissions as per your policies, when in doubt just click next.

10. On the review page, scroll to the bottom and check the button that reads:
*I acknowledge that AWS CloudFormation might create IAM resources with custom names.*

11. Click on Create.

12. Verify that the instance, roles and policies has been created and associated accordingly.

13. Enjoy! You are welcomed!

### Caveats:

* There is no current automated way to check if the VPC/Subnet/IGW are all in place and correctly configured. Manual creation of those elements is required.
