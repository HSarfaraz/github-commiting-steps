## Git & Github Learnings notes

### Git:

- Version constrol system is a tool that helps to track changes in code.
- Git is version control system it is popular, free, open source, fast, scalable.
- It helps not to override the changes of different developers.

### Github

- Github is a website that allow developer to store and manage their code using git.
- We can keep our project here, helps in showcase the work available.
- Folder of git is called repository.
- To create the profile on git go to github.com using email id.
- Pushing in git is 2 step process, We first make the change and add it --> than commit (pakka change)
- Git save the commit in the form of history

### Git:

- We can install in vs code.
- In Windows, we can install Git bash: https://git-scm.com/download/win
- git --version: to verify the version of git.

### Configuring git

  ```bash
      git config --global user.name "My name"
      git config --gloab; user.email "someone@email.com"
      git config --list
  ```

- When we need to connect git to github than above steps need to be followed.

### Clone & Status

  #### Clone
  - Cloning a repository on our local machine

  ```bash
      git clone <-- some project link -->
  ```

  - There are 2 location 1) Remote: Folder which are available on git repository 2) Local: which is out PC
  - Clone means creating the duplicate.
  - Here, cloning or coping the folde from github repo to local folder.
  - Go to the repo --> click on code --> Https --> copy the link.
  - It is better to use https to clone the project.
  - cd: change directory, here we can go inside the folder.
  - ls: list of files or folders.
  - There are 2 files are available visible and hidden, to view the hidden files we can use ls -a.

  #### status
  - Display the status of the code.

  ```bash
      git status
  ```
  - Whenever we dosome changes, VS Code shows files in yellow color with M on right. Here M means modify.
  - There are 4 stages
      1) **untracked :** new files the git doesn't yet track. As we have not commited it, Git consider it as new file.
      2) **modified :** changed. The file which is changed it becomed modified.
      3) **staged :** file is ready to be committed. When modified file or new file when added, it goes into staged.
      4) **unmodified :** unchanged.

  - commit: file is finally unchanged, we have taken the screenshot.

### Add & Commit

**add**

- Adds new or chnaged files in your working directory to the git staging area.
  ```bash
      git add <-- file name -->
      //to add all files
      git add .
  ```

**commit**

- It is record of change.
  ```bash
      git commit -m "some message"
  ```
- **-m :** means message.
- **origin :** It means remote repo by default.
- **main :** we are pushing in the main branch

### Push Command

** push ** (dhaka dena github pe apne local PC se)

- Upload local repo content to remote repo.

  ```bash
  git push origin main
  ```

- When we push 1st time then vs code ask for allow permission --> authorize vs code --> open vs code.
- Refresh remote repo to see the changes.
- To view the commit history, we can check on clicking the commits in remote repo.= which github track.

### Working with Github by creating the folder

### Init Command:

**init** Used to create a new git repo. It make repository as git repository.
```bash 
  git init git remote add origin <-- link --> //: here we are saying, we need to add new repo. Here remote means github repo.
  git remote -v (To verify remote) git branch (to check the branch)
  git branch -M main (to rename the branch)
  git push origin main //: or we can use git push -u origin main, -u means setting in upstream, next time we can directly do push main.
```

- It is advisable to create the repo first on gitub then clone rather going with git init approach.

### Workflow

- Create the repo on github --> then clone in the local --> do the changes --> add --> commit --> push to the github.

### Git branches

- Every new branch is created for every new feature.
- merge branch means keep the code in different branch same.
- We create different branches so that each developer can work independetly. Developer create a copy and work on it. once done merge with origin branch.

#### Branch commands

```bash
git branch (To check branch)
git branch -M branch (to rename branch)
git checkout <-- branch name --> (To navigate from one branch to another)
git checkout -b <-- new branch name --> (To create new branch)
git branch -d <-- To delete branch -->
````

### Merging Code

** Way 1**
```bash 
git diff <-- branch name --> (To compare comiits, branches, files & more)
git merge <-- branch name --> (To merge 2 branches)
```

** Way 2 **

- Creating a PR

### Pull request (PR)

- It lets you tell other about changes you have pushed to a branch in a repository on github.
- When many developer work together then they merge with main using pull request.
- Pull request means we are requeting to merge.
- While PR we say that, what new changes we are doing.

### Pull Command:

```bash
  git pull origin main
```

- Used to fetch and download content from a remote repo and immediately update the local repo to match that content.
- from remote --> to get into local

### Merge conflicts

- An event that take place when Git is unable to automatically resolve differences in code between 2 commits.
- Git dont understand when there is changes in files, do we need to keep changes from 1 branch or other branch. so Developer resolve it by comparing it manually.

  - **Accept the current change:** Whatever we did in current branch, keep those
  - **Accept Incoming change :** Keep the changes we are getting from main branch
  - **Accept Both changes :** If we want to keep both the changes.
  - First try to remove lines like <<<<<<<<<<<<<<<<<< or =================== or <<<<<<<<<<<<<<<< HEAD

  ```git diff main
      //comapre and resolve
      git merge main
  ```

### Undoing Changes

- Things we have commited by mistkae but dont need to commit those, so how can we undo those. (Commit nahi karna tha)

**Case 1 : Staged changes** : The changes which are added but not committed.

```bash
    git reset <!-- file name -->
    git reset
```

**Case 2 : Commited changes** (For 1 commit)

- HEAD~1 is the lastest commit by default. It means reset the HEAD with last 1 step. So git will take the old stage.
- git log: to view the all commits, basically w can check the history of commits. we quite by pressing q.

```bash
    git reset HEAD~1
```

**Case 3 : Commited changes** (For many commits) : Here we can mudo the multiple commits.

- Every commit has specific hash, hash means it is specific code.

```bash
    git reset <!-- commit hash -->
    git reset --hard <!-- commit hash -->
```

### Fork

- A fork is a new repository that shares the code and visibility settings with the original "upstream" repository.
- Fork is rough copy.
- We can copy other repository to our github basically.

<br/>
<hr/>
<br/>

### github-commiting-steps

<ul>
  <li>git status </li>
<li>git stash (Understanding: for remove all change and kept in temp branch)</li>
<li>git switch main (here, sending change to main)</li>
<li>git pull </li>
<li>git stash pop (Understanding: keep all changes form temp to main)</li>
<li>manaully see the changes and resolve the conflict --> accept and commit the changes </li>
<li>git checkout -b (Understanding: create new branch)</li>
<li>git push <new branch></li>
<li>click on merge request --> create a merge request </li>
</ul>
