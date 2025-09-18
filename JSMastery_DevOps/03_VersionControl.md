# Version Control

- Git isn't a nice to have, it's either:
    - Git good or
    - Git out
- Git is a distributed Version control software
- Distributed cuase:
    - each dev would have a copy of the code
    - along with it's entire history of change
    - and who changed what and when
- Note: always remember to config your git credentials (and default main branch) before starting to work
```bash
git config --global user.name 'varun verma'
git config --global user.email 'varun.verma2024@gmail.com'
git config --global init.defaultBranch main
```
- It is also helpful to the know the basic commands for a git repo
```bash
git init
git status
git add . | git add <fileName>
git commit -m "commit msg"
git log # exit by pressing 'q'
git checkout <commit hash>
```
- Also it is always important to make a **.gitignore** file

## Setting up Gitlab's CICD Pipelines
- [GitLabs Docs](https://docs.gitlab.com/runner/install/?utm_source=chatgpt.com)
- Videos in order (atq chatGPT):

1. [How to install & configure a GitLab Runner](https://www.youtube.com/watch?v=3uh1Zh6Kc_g) (self-hosted). Great for getting started.
2. [More detailed, walk-through including pipeline use](https://www.youtube.com/watch?v=HqaXHsSHMjk), good for practical infra setup.
3. [Focuses on runner setup on your own machine](https://www.youtube.com/watch?v=G8ZONHOTAQk), helpful to understand runners’ executors etc.
4. [Demonstrates setting up CI/CD infrastructure](https://www.youtube.com/watch?v=aXJ4hnCJc1U). Including on-prem GitLab / Jenkins etc; useful to see what’s involved
5. [GitLab CI Pipeline Setup](https://www.youtube.com/watch?v=z7nLsJvEyMY) - 20 min video

### GitLab Runner

- Formally know as GitLab Worker (till 2015) is an app used to execute jobs in pipelines.
- It's an engine which processes your pipeline instructions
- They are lightweight, versatile and can be deployed in various environments.
- They are the backbone of CICD workflows
- There are main 3 types of runners:
    - INSTANCE RUNNERS (avaiable to all projects within a GitLab instance)
    - GROUP RUNNERS (specific to a group of projects)
    - PROJECT RUNNERS (for only a specific project)
