# Identity and Access Management (IAM)

- IAM helps to control the access to AWS resources.
- You can manage who(users, groups, roles), can access what(resources) and how(permission and policies).
- It handles authentication(identity/who you are) and authorization(permissions/what you are allowed to do).
- IAM is global.

## Why use IAM?

- Control Access: Defines who can access AWS services and resources.
- Least privilege: Grant the minimum required permissions.
- Centralized control: Single point for managing access across multiple systems/applications.
- Multi-Factor Authentication (MFA): Add an extra layer of protection for user accounts.
- Compliance: Provides audit trails of who accessed what.

## Core IAM Components

### Users

- Single person or an application.
- Each user has unique credentials(Password, Access Key) for direct access to AWS.
- Ex: A developer logging in to the AWS Management Console with their own username and password.

### Groups

- Collection of IAM users (developers, admins, QA).
- Group helps to manage permisions for multiple users at once.
- Ex: An "Admin" group with full access permissions; all users in this group inherit those permissions.

### Policies

- JSON document that defines the persmissions for users and groups.
- It is set of rules that defines what actions are allowed or denied on which resources and under what conditions.
- Policies can be attached to users, groups, or roles.
- Ex: Allow DynamoDB read, deny delete.

#### Key components of a policy

- Version: Policy language version, always include "2012-10-17".
- Statement: Can contain one or multiple permission blocks. Each block defines one rule.
- Effect: Statement allowed or denied access. ("Allow" or "Deny").
- Action: What operation. (e.g., s3:GetObject, ec2:StartInstances, iam:CreateUser, \* → all actions).
- Resource: On which resource the action is applied. (e.g., a specific EC2 instance, an S3 bucket, or \* for all resources).
- Principal: Account/user/role to which the policy applies (not required for IAM policies).
- Condition: Conditions for when the policy is in effect (optional).

### Roles

- Roles grant permissions to AWS services or applications.
- Roles are temporary and do not have long-term credentials.

## Account Alias

- It is a unique name for your AWS account.
- It is used to login to the AWS account.
- It is used to create a custom URL for your AWS account.

- Your AWS account's sign-in page has this URL by default: https://Your_Account_ID.signin.aws.amazon.com/console/
- If you create an AWS account alias for your AWS account ID, your sign-in page URL looks more like: https://Your_Account_Alias.signin.aws.amazon.com/console/

## Best Practices (Very Important)

- Never use root for daily work.
- Use roles instead of access keys.
- Avoid long-term access keys.
- Always enable MFA.
- Follow least privilege.
- Review permissions periodically.

**Creating a IAM user**

**Add permission to the user after the user is created**

- Go to users and click on the users
- In the permission ploicies tab click on add permissions
- then select Attach policies directly, which will have aws managed permissions
- select the policy, click next
- click on add persmission button after reviewing.

> We can also impliment custom policies

**Creating a group**

- Go to User groups click on that and then click on create group
- Give an appropriate name
- Select the policies and create user group

**Addding user to the group**

- Click on the group name
- click on add users button
- Select user and click on Add users button

**Adding policy to the group**

- Click on group name
- click on permission tab
- click on add permission dropdown and choose attach policies
- Select the policies and click on attach policies
