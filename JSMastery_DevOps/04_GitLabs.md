# GitLabs

## Setting up Gitlab's CICD Pipelines
- [GitLabs Docs](https://docs.gitlab.com/runner/install/?utm_source=chatgpt.com)
- Videos in order (atq chatGPT):

1. [How to install & configure a GitLab Runner](https://www.youtube.com/watch?v=3uh1Zh6Kc_g) (self-hosted). Great for getting started.
2. [More detailed, walk-through including pipeline use](https://www.youtube.com/watch?v=HqaXHsSHMjk), good for practical infra setup.
3. [Focuses on runner setup on your own machine
](https://www.youtube.com/watch?v=G8ZONHOTAQk), helpful to understand runners’ executors etc.
4. [Demonstrates setting up CI/CD infrastructure
](https://www.youtube.com/watch?v=aXJ4hnCJc1U). Including on-prem GitLab / Jenkins etc; useful to see what’s involved
5. [GitLab CI Pipeline Setup](https://www.youtube.com/watch?v=z7nLsJvEyMY) - 20 min video

## Self Hosting GitLab
- Reasons:
  - Complete control: over data, how it is managed and stored
  - Cost efficient: no scription fees
  - Customizabiulity: configure exactly as needed
  - Privacy: data is not leaked outside org - best for sensitive or properitor softwares
- Over view of steps:
  - Setup Env:
    - setup server
    - install dependencies 
    - ensure we have a domain name
  - Install Gitlab or get he docker image for containerized deployment
  - Config GitLab:
    - setup domain
    - SSL certificates
    - Runners
  - Testing our setup
    - making sure everyone can access Gitlab
  - Advanced Conifgurations
    - Setup CICD pipelines
    - Backups 
    - User permissions 
 
**NOTE:** GitLab is heavy and we would need a beefy server to run it. Recommended specs: 4 CPU cores | 8 GB RAM | 100 GB Stoage | Latest Linux OS (not windows yuck)

## GitLab installations

- Follow the commands give in [docs](https://docs.gitlab.com/topics/offline/quick_start_guide/)
- Install Postfix for Email notifications
- Remember that **external url** setting is the domain. We will be accessing our Gitlab there (Better to have our own domain)
- For security purposes, we usually block the defualt admin account (we can unblock it if we need it later)
- Also we disable the create account feature so that only the users we create can access it with selected permissions.
- Advisble to make a group first. Makes giving permissions and assignment easier for later 
- Make Project 
- Make Pipeline (pre-req GitLab Runners)
- 

**NOTE:** most the cmds are for enterprize versions (...gitlab-ee...), which is the same codebase as the community version (...gitlab-ce...) but minor EE features. Technially we can still install EE verison for free, just can't use the EE features so it basically behaves like CE only. It mostly better when applied with a paid license. The paid features include:
  - Advanced CI/CD features
  - Security and compliance tools (SAST, DAST, dependency scanning, etc.)
  - Project management features (roadmaps, iterations, epics)
  - Enterprise support from GitLab



## GitLab Runner

- Formally know as GitLab Worker (till 2015) is an app used to execute tochjobs in pipelines.
- It's an engine which processes your pipeline instructions
- They are lightweight, versatile and can be deployed in various environments.
- They are the backbone of CICD workflows
- There are main 3 types of runners:
    - INSTANCE RUNNERS (avaiable to all projects within a GitLab instance)
    - GROUP RUNNERS (specific to a group of projects)
    - PROJECT RUNNERS (for only a specific project)
