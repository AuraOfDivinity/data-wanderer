---
title: AWS IAM Cheatsheet
date: 2023-05-16 06:54:50
tags:
- IAM
- Cheatsheet    
categories: 
- AWS
---

## What is IAM?

IAM stands for Identity and Access Management which is a global service used to managing users within an AWS account. IAM provides fine-grained access control across AWS accounts. With IAM, you can specify who can access which services and resources, and under which conditions. IAM is a pillar of security and provides you with easy ways to secure AWS accounts and resources.

## What is a Root Account and a IAM Account?

A root account is the account that is created by default. This account should not be used or shared with other parties.

An IAM Account is a sub account created under the root account with fine grained access given with least privilege principle in mind.

## What are Users in IAM?

Users are people within your organization that can be grouped. 

## What are User Groups?

Groups can contain one or multiple users. A group doesn’t contain other groups. A user can not belong to any groups or belong to one or many groups at the same time.

## What is an IAM Policy?

An AWS Policy is a JSON Document that defines a set of permisssions for making requests to AWS services. These policies can be attached to IAM USers, IAM Groups or IAM Roles to provide them with fine grained access.

## What is the Structure of an IAM Policy?

### Version

The policy language version.

### Id

An identifier for the policy


### Effect

The effect can be Allow or Deny. By default, users don't have permission to use resources and API actions, so all requests are denied. An explicit allow overrides the default. An explicit deny overrides any allows.

### Action

The action is the specific API action for which you are granting or denying permission. To learn about specifying action, see Actions for Amazon EC2.

### Resource

The resource that's affected by the action. Some Amazon EC2 API actions allow you to include specific resources in your policy that can be created or modified by the action. You specify a resource using an Amazon Resource Name (ARN) or using the wildcard (*) to indicate that the statement applies to all resources. For more information, see Supported resource-level permissions for Amazon EC2 API actions.

### Conditions

Conditions are optional. They can be used to control when your policy is in effect. For more information about specifying conditions for Amazon EC2, see Condition keys for Amazon EC2.

## How can IAM Resources be kept safe from getting Compromised?

IAM resources could be safeguarded with the use of IAM PAssword policies & Multifactor Authentication.

## What is IAM MFA?

MFA stands for Multi Factor Authentication. 
MFA =  password you know + device you own

Main benefit of MFA = Even if the account is hacked the hacked account could not be used for malicious purposes because the user doesn’t have the access to the device.

MFA device options include, - Google Authenticator, Authy, Universal 2nd factor security key(u2f key)

## How can Users Access AWS?

Three different options to access AWS,

1. AWS management console - protected by password policy + MFA
2. AWS CLI - Protected by access keys.
3. AWS SDK - Protected by access keys.

Access keys are generated through the AWS console. They are just like passwords and should not be shared with other parties. Access key id - username,  secret access key - password.

## What is AWS Cloudshell?

Cloudshell is basically a terminal in the cloud. The default region is the current region of the account that’s logged in. There is also a separate repository available inside cloudshell(i.e you can create files etc within that repository in cloudshell.)

## What is an IAM Role?

Some AWS services will need to perform certain actions on your behalf. To do this we have to assign permissions to AWS services with IAM roles.

## What are IAM Security Tools?

### IAM Credentials Report

An account wide report that lists all the account’s users and the status of their various credentials.

### IAM Access advisor

Access advisor shows the service permissions granted to a user and when those services were last accessed.
