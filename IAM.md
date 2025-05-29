# IAM

### what is IAM
AWS IAM (Identity and Access Management) is a service provided by Amazon Web Services that enables you to securely control access to AWS resources

### Key Features of AWS IAM:

- User Management: Create and manage individual users and their security credentials (like passwords and access keys).
- Group Management: Organize users into groups to apply common permissions.
- Permissions and Policies: Define what actions users or services can perform on which resources using JSON-based policies.
- Role Management: Create roles that can be assumed by users or services to gain temporary access to resources.
- Fine-Grained Access Control: Apply specific permissions to individual resources and operations.

### what is IAM policy

- Policy are set of permission that are applied to users and group 
- policy is a JSON document that defines permissions—what actions are allowed or denied on which AWS resources, and under what conditions.

### Key Concepts of a Policy:

- Effect: Either Allow or Deny. By default, all actions are denied unless explicitly allowed.
- Action: The specific AWS service operation, such as s3:PutObject or ec2:StartInstances.
- Resource: The ARN (Amazon Resource Name) of the resource the action applies to (e.g., a specific S3 bucket).
- Condition (optional): Specifies conditions for when the policy is in effect (e.g., based on IP address, time, MFA status).

### What is Role 
- IAM Role in AWS is an identity that you can assume to gain temporary permissions to perform actions on AWS resources.
- Unlike an IAM user, a role does not have long-term credentials (like a password or access key).

- Instead, roles are intended to be assumed by trusted entities such as:

  - AWS services (e.g., Lambda, EC2, ECS)
  - IAM users (for cross-account access or temporary privilege escalation) 
  - Federated users (e.g., logging in via Google, Okta, or corporate SSO)
  - Other AWS accounts (for cross-account access)
  
### Difference between identify based policy and resource based policy.

identity-based policies and resource-based policies are both used to control access, but they apply to different things and have different scopes.

🔹 Identity-Based Policies
Attached To: IAM identities — users, groups, or roles
Purpose: Grants permissions to users or roles to perform actions on AWS resources

📌 Example Use Case:
Allow a developer (IAM user) to read objects from a specific S3 bucket.

🧩 Example:

```
{
  "Effect": "Allow",
  "Action": "s3:GetObject",
  "Resource": "arn:aws:s3:::my-bucket/*"
}
```

🔸 Resource-Based Policies
Attached To: AWS resources directly (e.g., S3 bucket, SQS queue, SNS topic, etc.)
Purpose: Grants permissions to a principal (IAM user, role, or account) to access the resource

📌 Example Use Case:
Allow another AWS account to write to your S3 bucket.

🧩 Example:
```
{
  "Effect": "Allow",
  "Principal": { "AWS": "arn:aws:iam::123456789012:user/ExternalUser" },
  "Action": "s3:PutObject",
  "Resource": "arn:aws:s3:::my-bucket/*"
}
```
This is placed on the S3 bucket itself, allowing access to someone external.

✅ Key Differences at a Glance:
```
Feature	                      Identity-Based Policy	                    Resource-Based Policy
Attached To	                  IAM users, groups, or roles	              AWS resources (e.g., S3, SQS)
Grants Permissions To	        The identity itself	                      External or internal principals
Principal Specified?	        No (applies to the attached identity)	    Yes (Principal must be defined)
Common Services	Works with    all IAM identities	                      Only supported by specific services (e.g., S3, SQS, Lambda)
Cross-Account Access	        Needs a role or trust setup	               Can directly allow external access
 
```
