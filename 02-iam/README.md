# Identity and Access Management (IAM)

- It helps to control the access to AWS resources.
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
- Direct AWS access.
- Ex: A developer logging in to the AWS Management Console with their own username and password.

### Groups

- Collection of IAM users (developers, admins, QA).
- Group helps to manage persions for multiple users at once.
- Ex: An "Admin" group with full access permissions; all users in this group inherit those permissions.

### Policies

- JSON document that defines the persmissions for users and groups.
- Policies can be attached to users, groups, or roles.
- Ex: Allow DynamoDB read, deny delete.

### Roles

- Role is an identiy with a set of permissions.
- Roles are temporary and do not have long-term credentials.


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