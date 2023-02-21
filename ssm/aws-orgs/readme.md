# AWS Organizations Tredn Micro SSM Automation
---

AWS Systems Manager Distributor is a feature integrated with AWS Systems Manager that you can use to securely store and distribute software packages in your accounts. 
By integrating Workload Security with AWS Systems Manager Distributor, you can distribute agents across multiple platforms, control access to managed instances, and automate your deployments.


This solution will distribute Workload Security Software across member accounts that are spread across regions in an AWS Organization.

## Requirements

1. Download the Yaml Template contain the code needed.

2. In the Cloud One Workload Security console.
  - Click Support > Select Deployment Scripts.
  - Copy down the manager URL
  - Copy down the activation URL
  - Copy down the token

---

## How to Deploy

To deploy the solution, launch this CloudFormation template in your organization’s management account.

1. Provide the following inputs for the template:
  - IsDelegatedAdminstrator: Specify if the solution will use a delegated administrator account within the Organization to manage the software packages. CloudFormation StackSet IAM roles should be provisioned.
  - DelegatedAdminAccountId: (Optional) Delegated administrator account ID.
  - ManagementAccountId: (Required) AWS Organization’s Management account ID.
  - DeploymentTargets: Specify AWS account IDs and/or the organizational unit IDs within AWS Organization whose accounts have the target instances (e.g., ou-name, 123456789123) for distribution
  - TargetKey: Specify which instances have to be targeted for this solution. Allowed values – ParameterValues, ResourceGroup or begin with tag:, AWS::EC2::Instance, InstanceIds (default), instanceids. Refer to Target for more details.
  - TargetValues: Specify the target key values specified above. Default is *.
  - dsActivationUrl
  - dsManagerUrl 	
  - dsTenantId
  - dsToken

---

## Adding new accounts, OUs, and Regions
TBD
