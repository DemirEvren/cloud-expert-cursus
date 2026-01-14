# w2-DevOps-Tools — Notes

## Slide 1
- Cloud Services 2
- Amazon Web Services

## Slide 2
- AWS DevOps Tools

## Slide 3
- What is DevOps?
- Cultural philosophies
- Practices
- Tools

## Slide 4
- DevOps Culture
- Dev & Ops coming together
- No more "silos"
- Shared responsibility
- Ownership
- Visibility and communication

## Slide 5
- DevOps Practices
- Microservices
- Moving away from "monolithic" application architecture to many individual services

## Slide 6
- DevOps Practices
- Continuous Integration
- Continuous Delivery & Deployment

## Slide 7
- DevOps Practices
- Infrastructure as Code
- Model your AWS resources using code

## Slide 8
- DevOps Practices
- Monitoring and Logging
- Track and analyze metrics and logs
- Understand real-time performance of infrastructure and applications

## Slide 9
- Benefits of DevOps

## Slide 10
- Five major phases of release and monitoring
**source**
- Check-in source code (such as Java files)
**Build**
- Compile code + Unit tests + Peer review
- Code metrics + Style checkers + Create new code
**Test**
- Integration tests with other systems + Load testing + Unit tests + Penetration testing
**deploy**
- Deployment to production environments
**monitor**
- Monitor code in production to quickly detect unusual activity or errors

## Slide 11
- Release processes levels
- Continues Integration
- COntinues Delivery
- Continues deployment

## Slide 12
- AWS Code Services
- Software Release Steps
- AWS CodeCommit
- AWS CodeBuild
- AWS CodeDeploy
- AWS X-Ray
- AWS CodePipeline
- Amazon CloudWatch
- Third Party

## Slide 13
**Software Development & Continuous Delivery Toolchain:**
AWS CodeStar
AWS CodeCommit
AWS CodeBuild
AWS CodeDeploy
AWS CodePipeline
**Infrastructure as Code (IaC):**
AWS CloudFormation
AWS OpsWorks
AWS OpsWorks for Chef Automate
**Monitoring and Logging:**
AWS X-Ray
Amazon CloudWatch
AWS CloudTrail
AWS Config

## Slide 14
- (OCR missing for image16.jpg - content appears corrupted)

## Slide 15
- AWS CodeBuild
- Fully managed build service that compiles source code, runs tests, and produces software packages
- Scales continuously and processes multiple builds concurrently
- You can provide custom build environments suited to your needs via Docker images
- Only pay by the minute for the compute resources you use
- Launched with CodePipeline and Jenkins integration

## Slide 16
- How can I automate my release process with CodeBuild?
- Integrated with AWS CodePipeline for CI/CD
- Easily pluggable (API/CLI driven)
- Bring your own build environments
- Create Docker images containing tools you need
- Open source Jenkins plugin
- Use CodeBuild as the workers off of a Jenkins master

## Slide 17
- CodeBuild buildspec.yml
- version: 0.1
- environment_variables: Variables to be used by phases of build
- JAVA_HOME: "/usr/lib/jvm/java-8-openjdk-amd64"
- install: Install packages or run commands to prepare your environment
- pre_build: Run syntax checking commands
- build: Build started, build commands
- post_build: Test your app further or ship a container
- artifacts: Create and store an artifact in S3 (e.g., target/messageUtil-1.0.jar)

## Slide 18
- Building Your Code
- "Building" code typically refers to languages that require compiled binaries
- .NET languages: C#, F#, VB.net, etc.
- Java and JVM languages: Java, Scala, JRuby
- Go
- iOS languages: Swift, Objective-C
- We also refer to the process of creating Docker container images as "building" the image

## Slide 19
- Testing Your Code
- Testing is both a science and an art form!
- Goals for testing your code:
  - Want to confirm desired functionality
  - Catch programming syntax errors
  - Standardize code patterns and format
  - Reduce bugs due to non-desired application usage and logic failures
  - Make applications more secure

## Slide 20
- What service and release step corresponds with which tests?
- Third Party Tooling
- AWS CodeBuild

## Slide 21
- (OCR missing for image23.jpg - content appears empty)

## Slide 22
- AWS CodeDeploy
- Automates code deployments to any instance
- Handles the complexity of updating your applications
- Avoid downtime during application deployment
- Rollback automatically if failure detected
- Deploy to Amazon EC2 or on-premises servers, in any language and on any operating system
- Integrates with third-party tools and AWS

## Slide 23
- appspec.yml Example
- version: 0.0
- os: linux
- files: Send application files to one directory and configuration files to another
- Destination: /var/www/html
- object: /var/www/html with pattern "*.html"
- Set specific permissions on specific directories & files (group: root, mode: 755)
- hooks:
  - ApplicationStop: Remove/add instance to ELB
  - BeforeInstall: Install dependency packages
  - ApplicationStart: Start Apache
  - ValidateService: Confirm successful deploy

## Slide 24
- Choose Deployment Speed and Group
- Deployment options: half at a time, Prod Deployment group, all at once

## Slide 25
- (OCR missing for image27.jpg - content appears corrupted)

## Slide 26
- AWS CodePipeline
- Continuous delivery service for fast and reliable application updates
- Model and visualize your software release process
- Builds, tests, and deploys your code every time there is a code change
- Integrates with third-party tools and AWS

## Slide 27
- CodePipeline Example: MyApplication
- Source stage with CodeBuild
- Build stage
- Deploy stage (JavaApp)
- Pipeline has stages, actions, and transitions

## Slide 28
- CodePipeline with Parallel Actions
- MyApplication
- Source (CodeBuild, NotifyDevelopers)
- Build
- Deploy (JavaApp)

## Slide 29
- CodePipeline with Sequential Actions
- MyApplication
- Source, Build (CodeBuild, NotifyDevelopers)
- TestAPI
- Deploy (JavaApp)

## Slide 30
- CodePipeline with Manual Approvals
- MyApplication
- Build (CodeBuild)
- Staging-Deploy (JavaApp)
- QATeamReview
- Manual Approvals Review
- Prod-Deploy (JavaApp)

## Slide 31
- AWS CodeCommit
- Secure, scalable, and managed Git source control
- Use standard Git tools
- Scalability, availability, and durability of Amazon S3
- Encryption at rest with customer-specific keys
- No repo size limit
- Post commit hooks to call out to SNS/Lambda

## Slide 32
- AWS CodeCommit Architecture
- Git objects in Amazon S3
- Git index in Amazon DynamoDB
- SSH or HTTPS git pull/push to CodeCommit
- Encryption key in AWS KMS

## Slide 33
- AWS X-Ray
- Debug and analyze production applications in cloud or on-prem
- Visualize service graph to identify performance bottlenecks
- Troubleshoot and fix performance issues
- Quantify Customer Impact
- Integration with Lambda allows you to monitor Serverless applications
- X-Ray SDK available in Java, .NET, Node.js, and Python

## Slide 34
- DevOps Engineering Best Practices
- Develop on main line
- Only Build Your Binaries Once
- Deploy the Same Way to Every Environment
- Smoke-Test Your Deployments
- Deploy into a Copy of Production
- Each Change Should Propagate through the Pipeline Instantly
- If Any Part of the Pipeline Fails, Stop the Line

## Slide 35
- Extra leermaterialen & labs
- Bronvermelding slides: AWS Techtalk https://www.slideshare.net/AmazonWebServices/devops-on-aws-devops-day-san-francisco
