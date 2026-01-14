# w8-Cloudformation-deep-dive — Notes

## Slide 1
- Cloud Services 2
- Configuration Management in the cloud
- Introduction to CloudFormation

## Slide 2
- Operations course: Module 11 - Creating Automated and Repeatable Deployments

## Slide 3
- Configuration Management in the Cloud
- Module 11: Creating Automated and Repeatable Deployments

## Slide 4
- AWS CloudFormation
- Models and provisions cloud infrastructure resources
- Supports most AWS services
- Creates, updates, deletes set of resources as single unit (stack)
- Detects drift on stack and individual resources
- Components: Template (YAML/JSON), Stack (instantiation), Change set

## Slide 5
- AWS CloudFormation Terminology
- Template: Basic definition of resources in JSON or YAML
- Stack: Collection of AWS resources, instantiation of template, can be instantiated multiple times
- Create, update, or delete: Manage AWS resources
- Resources: VPC, DynamoDB, RDS, EC2 Instances, S3 Glacier Buckets

## Slide 6
- Template Structure
- Parameters: Inputs into template
- Mappings: Static variables (typically latest AMIs)
- Resources: AWS assets to create
- Init: Custom applications to run during startup
- WaitCondition: Signal from instance that user data completed
- Outputs: Values of custom resources (URLs, usernames, etc.)

## Slide 7
- Launch and Delete Stacks
- Templates launched via AWS Management Console, AWS CLI, AWS API
- On error: All resources rolled back by default
- On deletion: Resources rolled back
- Optional: Enable termination protection on stack

## Slide 8
- Define Parameters in a Template
- Use optional Parameters section to customize templates
- Parameters enable custom values per stack creation/update
- Supported data types: String, Number, List, CommaDelimitedList, AWS-specific parameter, SSM parameter
- Example: KeyPairName parameter

## Slide 9
- Reference a Parameter
- Use Ref intrinsic function to reference named parameter
- Converts to string regardless of type
- Use Fn::Select function to select values from comma-delimited list
- Example: AvailabilityZone with Fn::Select

## Slide 10
- Ref and Other Intrinsic Functions
- Ref function: Reference components in template
- Necessary for: Referencing parameters, Using maps, Joining strings, Using other functions
- Example: AWS::EC2::EIP with Ref to MyEC2Instance

## Slide 11
- Pseudo Parameters
- Use Ref function to access runtime environment information
- Examples: Region, Stack Name, AWS Account ID
- Predefined: No need to specify in Parameters section
- Example: Output MyStacksRegion with AWS::Region

## Slide 12
- Define Mappings in a Template
- Define lookup tables of name-value pairs in two-level map
- Combine multiple mapping tables for nested lookups
- Most commonly used to lookup current AWS AMI values

## Slide 13
- Mapping Example
- Use Fn::FindInMap intrinsic function for lookups
- AWSRegionToAMI mapping table with regions and AMI IDs
- Example: ImageId lookup by region

## Slide 14
- Define Resources in a Template
- Resources section declares AWS resources to create
- Specify resource type (e.g., AWS::RDS::DBInstance, AWS::EC2::Instance)
- DependsOn attribute: require creation order
- Properties: Resource-specific configuration

## Slide 15
- CloudFormation::Init
- Resource type providing access to metadata from EC2 instances
- Used with cfn-init helper script
- cfn-init reads template metadata from AWS::CloudFormation::Init key
- Can: Install packages, Manage users/groups, Write files, Run commands, Enable/disable services

## Slide 16
- User Data vs. CloudFormation::Init
- User data: Script file, greater control, greater potential for error
- CloudFormation::Init: Can rollback automatically, Cleaner, Metadata within template, Configsets

## Slide 17
- WaitCondition and WaitConditionHandle
- Used when bootstrapping instances
- WaitCondition blocks completion until WaitConditionHandle called or timeout reached
- Specify number of successful signals (default: 1)
- Signal success/failure with cfn-signal command

## Slide 18
- WaitCondition and WaitConditionHandle Example
- Define WaitConditionHandle (resource type)
- Define WaitCondition (depends on instance, references handle, set timeout)
- UserData: Call cfn-signal with handle reference

## Slide 19
- Define Outputs in a Template
- Return values for resources created in stack
- Use intrinsic functions to get resource values
- Example: WebSiteURL output with Fn::GetAtt for ELB DNSName

## Slide 20
- Additional AWS CloudFormation Stack Options
- Prevent rollback on failure
- Set stack policy for update control
- Enable termination protection
- Example: aws cloudformation create-stack with on-failure DO_NOTHING

## Slide 21
- Override for Failed Update Rollbacks
- Continue rolling back update even after rollback failed
- UPDATE_ROLLBACK_FAILED state
- Remedy the cause and continue rollback
- Command: aws cloudformation continue-update-rollback --stack-name

## Slide 22
- AWS CloudFormation Best Practices (1 of 3)
- (Visual content not fully captured in OCR)

## Slide 23
- AWS CloudFormation Best Practices (2 of 3)
- (Visual content not fully captured in OCR)

## Slide 24
- AWS CloudFormation Best Practices (3 of 3)
- (Visual content not fully captured in OCR)

## Slide 25
- Leermaterialen & Labs
- (Links not fully specified in OCR)
