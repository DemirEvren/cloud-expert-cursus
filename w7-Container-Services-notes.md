# w7-Container-Services — Notes

## Slide 1
- Cloud Services 2
- Amazon Web Services

## Slide 2
- AWS Container Services

## Slide 3
- Comparing Monolithic and Microservice Architectures
- Monolithic: Storefront UI, Account service, Cart service, Shipping service, Data access service, Database
- Microservices: Services in different languages (Node.js, Python, Java)
- Load balancer distributes traffic to services

## Slide 4
- Characteristics of Microservices
- Decentralized
- Independent
- Black boxes
- Polyglot (multiple languages)
- Specialized
- You build it, you run it

## Slide 5
- Microservices and Containers
- Microservices Design: Decentralized, evolutionary design; Smart endpoints, dumb pipes; Independent products; Designed for failure, disposable; Development and production parity
- Container Characteristics: Each service uses best suited language/technology; Components isolated, evolve separately; All dependencies packaged in immutable object; Gracefully shut down, fast fail; Development/testing/production environments consistent; Facilitates DevOps

## Slide 6
- Challenges of Managing Containers at Scale
- State of containers
- Scheduling of starts and stops
- Resources available on each server
- Maximizing availability, resilience, and performance

## Slide 7
- Container Orchestration Platforms
- Scheduling (auto-placement of containers)
- Placement (resource allocation)
- Service integration (container networking)

## Slide 8
- Amazon ECS
- Amazon Elastic Container Service (Amazon ECS)
- Fully managed container orchestration service
- Scales rapidly to thousands of containers with no additional complexity
- Schedules placement across managed clusters
- Integrates with third-party schedulers and other AWS services

## Slide 9
- Amazon ECR
- Amazon Elastic Container Registry (Amazon ECR)
- Fully managed container registry for storing, running, managing container images
- Scalable and highly available
- Integrated with Amazon ECS and Docker CLI
- Secure: Encryption at rest, Integration with IAM

## Slide 10
- Amazon ECS Solution Architecture
- Pull container image from registry (AWS ECR or other)
- Select launch type (Fargate or Amazon EC2)
- Define application
- Manage containers

## Slide 11
- AWS Fargate
- Fully managed container service
- Works with Amazon ECS and Amazon EKS
- Provisions, manages, scales container clusters
- Manages runtime environment
- Provides automatic scaling

## Slide 12
- Amazon ECS with Fargate or Amazon EC2
- Choose Fargate: Wide demand swings, large optimized workloads, small test environments, batch scheduled workloads
- Choose EC2: Predictable resource requirements, large price-optimized workloads, compliance requirements, excess capacity
- Fargate: AWS manages VMs, guest OS, Docker engine; You manage containers and apps
- EC2: You manage instances, OS, Docker engine; You manage containers and apps

## Slide 13
- Creating Amazon ECR Repository and Pushing Image
- Create repository: aws ecr create-repository --repository-name hello-world --region us-east-1
- Build and tag: docker build -t hello-world .; docker tag hello-world:latest aws_account_id.dkr.ecr.us-east-1.amazonaws.com/hello-world:latest
- Authenticate: aws ecr get-login-password --region region | docker login --username AWS --password-stdin aws_account_id.dkr.ecr.region.amazonaws.com
- Push image: docker push aws_account_id.dkr.ecr.us-east-1.amazonaws.com/hello-world:latest

## Slide 14
- Amazon EKS
- Amazon Elastic Kubernetes Service (Amazon EKS)
- Managed service that runs Kubernetes on AWS Cloud
- Built with Kubernetes community
- Conformant and compatible
- Secure by default

## Slide 15
- Amazon EKS Architecture
- Provision Amazon EKS cluster
- Deploy Fargate and EC2 nodes
- Connect to run Kubernetes applications

## Slide 16
- AWS Elastic Beanstalk
- Service for deploying and scaling web applications and services
- Automatically handles deployment details: capacity provisioning, load balancing, auto-scaling, health monitoring
- Provides variety of platforms
- Manage all resources running application as environment

## Slide 17
- Elastic Beanstalk Components
- Application: Logical collection of Elastic Beanstalk components
- Application version: Specific labeled iteration of deployable code
- Environment: Collection of AWS resources running application version
- Environment tier: Type of application (web server or worker)
- Environment configuration: Parameters and settings defining behavior
- Saved configuration: Template for creating unique configurations
- Platform: Combination of OS, language runtime, web server, application server
- Elastic Beanstalk CLI: Interactive commands for management

## Slide 18
- IAM Permissions in Elastic Beanstalk Environments
- Service Role: Assigned during creation, Elastic Beanstalk assumes to use other services, Default: aws-elasticbeanstalk-service-role
- Instance Profile: Assigned during creation, Applied to launched instances, Default: aws-elasticbeanstalk-ec2-role
- User Policies: Optionally assigned to users/groups, Full admin or read-only access available

## Slide 19
- AWS Managed Policy Example
- IAM policy excerpt showing EC2 and ELB describe permissions
- AmazonEC2ReadOnlyAccess policy example

## Slide 20
- Elastic Beanstalk Simplifies Container Deployment
- Amazon ECS setup: Create task definition, Create cluster, Create service
- Elastic Beanstalk setup: Write Dockerrun.aws.json, Provide zipped code, Select platform, Launch application

## Slide 21
- Multicontainer Docker Platform
- Elastic Beanstalk environment with ELB, Auto Scaling Group, ECS cluster
- Two URLs to Elastic Beanstalk environment

## Slide 22
- Deployment Option Namespaces
- aws:elasticbeanstalk:command: Choose deployment policy, Set timeout, Batch options, Cancel on failed health check
- aws:elasticbeanstalk:trafficsplitting: Traffic percentage to new instances, Wait time before traffic shift

## Slide 23
- Example Traffic Splitting (Canary Testing)
- Deployment configurations with TrafficSplitting policy
- NewVersionPercent: 15%
- EvaluationTime: 10 minutes
- Temporary auto-scaling for health checks

## Slide 24
- Blue/Green Deployments on Elastic Beanstalk
- Clone environment (Blue)
- Deploy and test in new environment (Green)
- Switch CNAMEs to route traffic
- Elasticsearch Beanstalk environment blue and green

## Slide 25
- Extra leermaterialen & labs
- Documentation:
- https://docs.aws.amazon.com/ecs/
- https://docs.aws.amazon.com/ecr/
