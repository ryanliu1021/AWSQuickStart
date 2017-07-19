## Aviatrix - AWS Quickstart lite script for CloudFormation

### Description
This CloudFormation script will create the following:

* One Aviatrix Role for EC2 (named aviatrix-role-ec2) with corresponding role policy (named aviatrix-assume-role-policy). [Click here for this policy details](https://s3-us-west-2.amazonaws.com/aviatrix-download/iam_assume_role_policy.txt)
* One Aviatrix Role for Apps (named aviatrix-role-app) with corresponding role policy (named aviatrix-app-policy) [Click here for this policy details](https://s3-us-west-2.amazonaws.com/aviatrix-download/IAM_access_policy_for_CloudN.txt)

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
  Choose file -> aviatrix-aws-quickstart-lite.json
```

  > Note: the [aviatrix-aws-quickstart-lite.json file](https://github.com/AviatrixSystems/AWSQuickStart/blob/master/aviatrix-aws-quickstart-lite.json) can be found in this project, click [here](https://raw.githubusercontent.com/AviatrixSystems/AWSQuickStart/master/aviatrix-aws-quickstart-lite.json)   for direct download.

5. Click next.

6. On the Stack Name textbox, Name your Stack -> Something like *AviatrixRoles*

7. Click next

8. Especify your options/tags/permissions as per your policies, when in doubt just click next.

9. On the review page, scroll to the bottom and check the button that reads:
*I acknowledge that AWS CloudFormation might create IAM resources with custom names.*

10. Click on Create.

11. Verify that the instance, roles and policies has been created and associated accordingly.

12. Enjoy! You are welcomed!
