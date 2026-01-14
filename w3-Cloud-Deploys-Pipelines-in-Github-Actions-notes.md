# w3-Cloud-Deploys-Pipelines-in-Github-Actions — Notes

## Slide 1
- Cloud Expert
- Cloud Deployments: Github Actions
- Pipelines in Github Actions

## Slide 2
- Github Actions Components
- Workflows: Basics
- Jobs
- Marketplace
- Triggers

## Slide 3
- What is a Pipeline?
- Definition: "deployment pipeline" (Jez Humble and David Farley, Continuous Delivery)
- Ensures all code checked in to version control is automatically built and tested in production-like environment
- Keywords: All Code, Version control, Automatically built, Automatically tested, Production-like environment

## Slide 4
- (OCR missing for image6.png)

## Slide 5
- Recap: CI/CD Pipeline
- Continuous delivery (CD) pipeline is an automated expression of your process for getting software from version control to users and customers
- Every code change goes through complex process: building, testing, deployment
- Build software in reliable and repeatable manner
- Progress build through multiple stages of testing and deployment

## Slide 6
- Github Actions: Overview
- https://docs.github.com/en/actions

## Slide 7
- Github Ecosystem
- More than just code repositories
- Issue tracking
- Kanban & project tracking
- Wiki & documentation
- Releases
- Security scans / dependency scans
- CI/CD

## Slide 8
- Github Actions: Workflows
- A workflow is a configurable automated process that executes one or more jobs
- Defined by YAML file in repository
- Executed by triggers/events or manually
- Located in .github/workflows folder
- https://docs.github.com/en/actions/writing-workflows/quickstart

## Slide 9
- Github Actions: Components
- Runners, Actions, Events, Jobs, Steps
- https://docs.github.com/en/actions/about-github-actions/understanding-github-actions

## Slide 10
- Github Actions: Workflows
- Repository can have multiple workflows with different sets of tasks
- Builden & testing of pull requests
- Deployment of application on new release

## Slide 11
- Github Actions: Workflow Basics
- One or more events trigger workflow
- One or more jobs execute on runner with one or more steps
- Each step can run script or use extension/action
- Events → Jobs → Steps → Scripts/Actions

## Slide 12
- Github Actions: Creating Workflows
- Wizard in "actions" tab
- Manual: Create YAML file in .github/workflows folder

## Slide 13
- Github Actions: Creating Workflows
- Create new YAML file in .github/workflows folder
- Github detects Actions workflows automatically
- Naming: Must end in .yml or .yaml
- YAML is human-readable format for configuration files

## Slide 14
- YAML Definition
- YAML is a human-readable file format used for configuration files and data storage/transmission
- Format since 2001, file extension .yaml since 2006
- Formatting uses spaces, not tabs

## Slide 15
- YAML Cheatsheet
- Key-value pairs
- Lists
- Multiline script
- Multiline text
- Variables
- Github variables

## Slide 16
- Hello World Example
- Navigate to Github Actions tab
- Create new workflow.yml file
- Add basic workflow structure

## Slide 17
- Hello World Workflow
- View workflow in Actions tab
- Dashboard with general info about workflow/pipelines & runs
- Visual feedback on execution

## Slide 18
- Hello World Workflow Dashboard
- Each workflow has own dashboard with history of runs
- Can manually start with "run workflow" button

## Slide 19
- Hello World Workflow Runs
- Realtime feedback on current and previous build attempts
- Uses colors, identifiers, timestamps, user information
- Later: links with commit digests

## Slide 20
- Hello World Workflow Details
- Each run has own dashboard with information
- General metrics
- Complete log of executed jobs & steps with output
- Stored artifacts

## Slide 21
- Workflow Structure
- Fixed structure: name (pipeline metadata)
- Triggers: When pipeline starts
- Jobs: Large blocks in pipeline
- Steps: Individual steps in job
- Structure extensible with additional requirements

## Slide 22
- Runs On
- Github Actions uses VMs for CI environment
- Options: Linux, Windows, MacOS
- Free for public repos
- Charged per running minute for private repos
- Can be used for: Builds, Unit testing, Functional testing

## Slide 23
- Self-Hosted Runners
- Host your own runner
- No Github cost
- Full control
- Sometimes needed for sensitive environments/data
- https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/about-self-hosted-runners

## Slide 24
- Jobs
- Job is collection of steps executed on one virtual machine
- All steps in job run on same VM
- Multiple jobs possible
- Jobs can depend on each other
- Separation of concerns
- https://docs.github.com/en/actions/writing-workflows/choosing-what-your-workflow-does/using-jobs-in-a-workflow

## Slide 25
- Github Actions: Workflow Jobs
- Jobs: Job specification
- Runs-on: Environment (Linux, Windows, MacOS)
- Strategy: Which version of tools to use
- Steps: Job steps with uses or run

## Slide 26
- Steps
- Job consists of one or more steps
- Breakdown of job tasks
- Execute sequentially
- Output can be passed between steps
- Job stops on step failure

## Slide 27
- Github Actions: Workflow Steps
- Steps: runs or uses
- uses: External, predefined action (verified Github scripts)
- run: CLI command
- Example: actions/checkout@v4 https://github.com/actions/checkout

## Slide 28
- Github Actions: Marketplace
- "You are not special.... use the marketplace"
- For DevOps calculator with Node application, use proposed action
- https://docs.github.com/en/actions/writing-workflows/choosing-what-your-workflow-does/using-jobs-in-a-workflow

## Slide 29
- Errors & Debugging
- Workflow stops on command/plugin errors
- Digital andon cord
- Visual feedback when something fails

## Slide 30
- Errors & Debugging Details
- Technical feedback in workflow run reporting
- Per step visibility of success/failure
- Error messages and logs

## Slide 31
- Dependencies
- Specific commands/tooling needed?
- Check for existing marketplace action
- If not: manually install in runner or use self-hosted runner

## Slide 32
- Checkout Code
- First step often brings code from repository
- Github marketplace action: actions/checkout@v4
- https://github.com/marketplace/actions/checkout

## Slide 33
- Triggers
- on keyword determines when pipeline runs
- Specific events on branches
- Creating/commenting on issues
- Fixed schedules
- Manual execution

## Slide 34
- Triggers Examples
- Push to branches
- Pull requests to branches
- Cron schedules
- Manual dispatch
- Various event types

## Slide 35
- Github Actions: Workflow Example
- Complete workflow structure with jobs and steps

## Slide 36
- Github Actions: Example Implementation
- Step-by-step example of creating workflow

## Slide 37
- Github Actions: Environment Variables
- Github provides system variables about workflow run context

## Slide 38
- Learning Workflow Creation
- Create .github/workflows directory
- Create new YAML file (tearn-github-actions.yml)
- Add workflow code
- Commit and push to repository

## Slide 39
- Workflow Information Steps
- Who triggered the workflow
- Repository info (name, default branch, URL)
- Runner info (OS, architecture)
- Job info (name, workflow, run number)

## Slide 40
- Environment Variables at Step Level
- Define environment variables per step
- Override global variables
- Example: DAY_OF_WEEK, Greeting variables

## Slide 41
- Secrets and Variables
- Secrets: Encrypted, used for sensitive data
- Variables: Plain text, used for non-sensitive data
- Managed at repository level
- Used in actions workflows

## Slide 42
- Creating Repository Secrets
- Actions secrets / New secret
- Name: PRIVATE_KEY
- Secret: Encrypted private key content
- Used for authentication and secure deployments

## Slide 43
- Deploying with Secrets
- Deploy to EC2 example
- Use secrets for PRIVATE_KEY, HOST, USER
- SSH connection for deployment
- Secure secret management

## Slide 44
- Workflow Stages
- Code → Dependencies (unit test) → Build → Artifact

## Slide 45
- Checkout and Setup Steps
- Checkout code with actions/checkout@v4
- Setup Node.js with actions/setup-node@v4
- Install dependencies
- List files

## Slide 46
- Dependency Installation Output
- npm install output
- Package audit results
- Vulnerability detection

## Slide 47
- Java Unit Testing with Maven
- Set up JDK 17
- Run mvn test
- https://github.com/actions/setup-javaev4

## Slide 48
- Maven Test Output
- Test execution details
- Pass/fail counts
- Build success confirmation

## Slide 49
- Maven Workflow Report
- Unit testing report
- Detailed test results per class
- Pass/fail/skip counts
- Artifact generation

## Slide 50
- Test Report and Artifacts
- Name: Test Report
- Uses: dorny/test-reporter@v2
- Path: target/surefire-reports/TEST-*.xml
- Reporter: java-junit

## Slide 51
- Archive Production Artifacts
- uses: actions/upload-artifact@v4
- Upload app-package with compiled JAR files
- Store build artifacts

## Slide 52
- Artifacts Storage
- Produced during runtime
- Name: app-package
- Size: 5.42 KB
- Digest: SHA256 hash

## Slide 53
- Unit Testing Java Example
- Complete workflow for Java testing

## Slide 54
- Docker Image Building and Pushing
- Check out repo
- Login to Docker Hub
- Extract metadata (tags, labels)
- Build and push Docker image to registry

## Slide 55
- (OCR missing or corrupted)

## Slide 56
- Complete DevOps Pipeline
- Code → Build → Unit tests → Integration tests → Staging → Production
