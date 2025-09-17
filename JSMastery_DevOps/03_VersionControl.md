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
