# w2-Systems-Tools — Notes

## Slide 1
- Cloud Expert
- Amazon Web Services

## Slide 2
- AWS System Tools

## Slide 3
- AWS Systems Manager
- A collection of capabilities to help you manage your applications and infrastructure running in the AWS Cloud
- Systems Manager simplifies application and resource management
- Shortens the time to detect and resolve operational problems
- Helps you manage your AWS resources securely at scale

## Slide 4
- (OCR missing for image6.png)

## Slide 5
- (OCR missing for image7.png and image8.png)

## Slide 6
- AWS Systems Manager
- Operations Management: Explorer, OpsCenter, Incident Manager
- Application Management: Application Manager, AppConfig, Parameter Store
- Change Management: Change Manager, Automation, Maintenance Windows
- Node Management: Fleet Manager, Compliance, Inventory, Session Manager, Run Command, State Manager, Patch Manager, Distributor

## Slide 7
- AWS Systems Manager

## Slide 8
- Session Manager
- VPC architecture with public/private subnets
- Secure shell access to EC2 instances without SSH ports

## Slide 9
- Bastion Host Alternative
- VPC with bastion host for access to private instances
- SSH access through bastion with security groups

## Slide 10
- What do I need?
- SSM Agent (installed by default on Amazon Linux, macOS, Ubuntu, Windows)
- Supports Linux, Windows, macOS
- EC2 or Hybrid ("advanced instances")
- IAM Role with AmazonSSMManagediInstanceCore policy or custom policy

## Slide 11
- Instance Connection Options
- EC2 Instance Connect
- Session Manager
- SSH Client
- EC2 Serial Console
- Session Manager connects without SSH keys or bastion host
- Sessions secured using AWS Key Management Service key
- Log session commands in Amazon S3 bucket or CloudWatch Logs
- Example: whoami returns ssm-user

## Slide 12
- Session Manager Advanced Features
- Use IAM permissions to control access
- Control StartSession actions and access specific instances
- Define resource ARNs and document permissions

## Slide 13
- Session Manager Advanced Features
- Port forwarding: Forward ports from local machine to remote instance
- Example: aws ssm start-session with PortForwardingSession document

## Slide 14
- Session Manager Advanced Features
- SSH and SCP support
- Use AWS-StartSSHSession document
- Leverage existing SSH keys and SCP commands
- Works with ProxyCommand for seamless SSH integration

## Slide 15
- Session Manager Advanced Features
- Logging and auditing
- CloudTrail integration
- S3 storage for session logs
- CloudWatch Logs for detailed logging
- EventBridge for event-driven workflows

## Slide 16
- OpsCenter Architecture
- Security Hub, EventBridge, SNS integration
- Personal Health Dashboard
- Incident Manager
- Automation
- CloudTrail, AWS Managed Guru, DevOps Guru integration
- Auto Scaling and CloudWatch coordination

## Slide 17
- Parameter Store
- Centralized way to manage configuration data
- Store different logins and reference streams
- Receive notifications when secrets and passwords are or aren't changed

## Slide 18
- Parameter Store Key Features
- Change notification
- Organize and control access
- Label versions
- Data validation
- Reference secrets
- Accessible from other AWS services
- Integrate with other AWS services

## Slide 19
- Parameter Store Architecture
- AWS Management Console
- AWS Command Line Interface (CLI)
- AWS Tools and SDKs
- Public Parameters: AMI, Global Infrastructure, References
- Private Parameters: EC2, ECS, AWS CodeBuild, AWS CloudFormation, AWS Secrets Manager

## Slide 20
- Parameter Store Visualization
- Tier: Standard, Advanced
- Type: String, SecureString, StringList
- Version tracking

## Slide 21
- Parameter Store History
- Version management with labels
- Track parameter changes
- View modification dates and users
- Version-based rollback capability

## Slide 22
- Parameter Store Advanced Features
- Change notifications (EventBridge)
- Standard and Advanced Tier
- Parameter Policies (expiration, no-change notification)
- Standard Tier: 10,000 parameters, 4KB max size, no policies, no cost
- Advanced Tier: 100,000 parameters, 8KB max size, policies available, charges apply

## Slide 23
- Automation Runbooks
- Automation Action flows
- Call AWS APIs and wait for properties
- Interact with Instances, AMIs, CloudFormation Stacks
- Run Automations or Commands
- Execute Lambda Functions or Step Functions
- Execute scripts (Python or PowerShell)

## Slide 24
- Automation Advanced Usage
- Trigger based on events (EventBridge, State Manager, Maintenance Window)
- Target groups of instances
- Use rate controls
- Run across regions and accounts

## Slide 25
- Use Cases for Automation
- One-click configuration tasks
- Performing routine maintenance tasks
- Automatic remediation through AWS Config
- Stopping EC2 instances with approvals
- Taking backups of AWS resources (DynamoDB, etc.)

## Slide 26
- Automation Key Features
- Scripting support in runbook content
- Run automations from centralized location
- Enhanced operations security
- Safely perform disruptive tasks in bulk
- Define constraints for inputs
- Log automation action output to Amazon CloudWatch Logs
- Share organizational best practices

## Slide 27
- How does Automation work?
- Assumes current user context by default
- Option to specify service role
- Leverage AWS provided playbooks
- Create custom Automation documents
- Define actions to perform
- Provide dynamic parameters
- Conditionally branch based on step results
- Configure approvals as part of workflow

## Slide 28
- Automation Execution Models
- Run the Automation playbook directly
- Multi-account and multi-Region
- Register as Maintenance Window task
- Remediation with OpsCenter
- Trigger based on CloudWatch Event rules
- Automatic remediation with AWS Config

## Slide 29
- Extra leermaterialen & labs
- Lab: https://cloudexpert.dubbadub.be/#/2_system
- Documentation: https://docs.aws.amazon.com/systems-manager/
- Bronvermelding slides: Ben Bridts (Cloudar) https://speakerdeck.com/benbridts/aws-systems-manager
- AWS Techtalk https://pages.awscloud.com/AWS-Systems-Manager-Gain-Operational-Insights-and-Take-Action-on-AWS-Resources_2020_0220-MGT_OD.html
