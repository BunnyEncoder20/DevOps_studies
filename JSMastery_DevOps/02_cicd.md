# CICD

- CI = Continuous Integration
    - when new code is pushed, tests run automatically
    - if something breaks, the the pipeline is stopped until the issue it resolved
- CD = Continuous Deployment
    - when the code passes all tests, the code is shipped automatically to staging or production
- Our job as a DevOps Engg is to code these pipelines, using tools like:
    - GitHub Actions
    - GitLab CI
    - Jenkins
    - Circle CI
- We need to define each step from build, test, release and deploy.

## Running Apps on Servers

- Till recently, most apps were installed directly on the servers and if some code needed a different version of node.js (and other server softwares needed another) then there would be conflict everywhere
- Containers solve this by packaging everything a app needs to run, The most popular tool here is **Docker**
- Now in real world cases there are going to be *hundreds of containers* (for each services, cause of scalling the servers, etc) running at once
- As a DevOps Engg, we need to control:
    - Where do these containers run?
    - How many copies do we need right now?
    - What happens if one crashes?
    - How do they securely talk to each other?
- This is called **Orchestration** and the go to tool here is **Kubernetes**, it cordinates all the containers and scales them automatically when needed.

## IaC (Infra as Code)

## Cloud

- Most companies don't run there own servers anymore, instead they rent the compute power from cloud providers like AWS, GCP, Asure
- But for us, we can only use on-prem servers

## Monitoring

- Needed to monitor the technical performace metrics for the apps
- Go to tools:
    - Prometheus
    - Grafana

## Scripting

- DevOps Engg should be fimiliar with bash or shell scripting and also a programming langguage like Pyhton or Js.
- Cause Automation is at the heart of DevOps work
- Eg: when onboarding a new developer, to grant him the access and git permissions, we don't click through several dashboards, we just run a script for this user for this role.
