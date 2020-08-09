# GITFLOW WORKFLOW

Resource: https://nvie.com/posts/a-successful-git-branching-model/

#### clone a remote git repository
				
`git clone <remote-repository-url>`
- example: `git clone https://github.com/username/repository.git`
- clone a remote git repository to a local system.

----------------------------------------------------------------------------------------------------------

#### create **develop** branch - this is the main code-line

1. `git checkout -b develop`
- create and switch to a branch called **develop**

2. `git push -u origin develop`
- links local **develop** branch with remote corresponding **develop** branch
- push local branch to remote repository for the first time (first time only)

----------------------------------------------------------------------------------------------------------

1. `git checkout -b featureBranch`
- create and switch to a branch called featureBranch

##### add or modify files

`git add .`

`git commit -m "ADD/MODIFY File/s"`

2. `git push -u origin featureBranch`
- links local branchName with remote corresponding branch

----------------------------------------------------------------------------------------------------------

#### integrate featureBranch branch with the main code-line i.e., the **develop** branch
 
1. `git checkout develop`

2. `git pull`

3. `git merge featureBranch`

4. `git push`

----------------------------------------------------------------------------------------------------------

#### release code from **develop** branch (Normally code is released from a dedicated **release** branch taken from **develop**). In this case assume develop contains valid releaseable code.

1. `git checkout master`

2. `git pull`

3. `git merge develop`

4. `git push`

----------------------------------------------------------------------------------------------------------

#### create a tag representing the release

##### a **tag** is a special branch which can be setup to read only, giving us the certainity to always have a branch we can go back to in-order to reproduce releaseable code

1. `git tag "1.0.0.RELEASE" -m "Releasing version 1.0.0"`

2. `git push --tags`

----------------------------------------------------------------------------------------------------------

### git commands' logs

**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**

$ `git clone https://github.com/AnanthaRajuC/Git-Flow-Workflow.git`
~~~
Cloning into 'Git-Flow-Workflow'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**

$ `cd Git-Flow-Workflow/`

**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git/Git-Flow-Workflow (master)**

$ `ls`
~~~
LICENSE  README.md
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git/Git-Flow-Workflow (master)**

$ `git checkout -b develop`
~~~
Switched to a new branch 'develop'
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git branch`
~~~
* develop
  master
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git push -u origin develop`
~~~
Total 0 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'develop' on GitHub by visiting:
remote:      https://github.com/AnanthaRajuC/Git-Flow-Workflow/pull/new/develop
remote:
To https://github.com/AnanthaRajuC/Git-Flow-Workflow.git
 * [new branch]      develop -> develop
Branch 'develop' set up to track remote branch 'develop' from 'origin'.
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git checkout -b feature1`
~~~
Switched to a new branch 'feature1'
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (feature1)

$ `git branch`
~~~
  develop
* feature1
  master
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (feature1)

$ `git status`
~~~
On branch feature1
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        feature1.txt

nothing added to commit but untracked files present (use "git add" to track)
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (feature1)

$ `git add .`

**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (feature1)

$ `git commit -m "ADD feature1.txt to feature1 branch"`
~~~
[feature1 6b9a811] ADD feature1.txt to feature1 branch
 1 file changed, 1 insertion(+)
 create mode 100644 feature1.txt
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (feature1)

$ `git push -u origin feature1`
~~~
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 339 bytes | 339.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'feature1' on GitHub by visiting:
remote:      https://github.com/AnanthaRajuC/Git-Flow-Workflow/pull/new/feature1
remote:
To https://github.com/AnanthaRajuC/Git-Flow-Workflow.git
 * [new branch]      feature1 -> feature1
Branch 'feature1' set up to track remote branch 'feature1' from 'origin'.
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (feature1)

$ `git branch`
~~~
  develop
* feature1
  master
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (feature1)

$ `git checkout develop`
~~~
Switched to branch 'develop'
Your branch is up to date with 'origin/develop'.
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git branch`
~~~
* develop
  feature1
  master
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git pull`
~~~
Already up to date.
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git merge feature1`
~~~
Updating ea6a7a9..6b9a811
Fast-forward
 feature1.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature1.txt
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git push`
~~~
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/AnanthaRajuC/Git-Flow-Workflow.git
   ea6a7a9..6b9a811  develop -> develop
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git branch`
~~~
* develop
  feature1
  master
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git**/Git-Flow-Workflow (develop)

$ `git checkout master`
~~~
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git/Git-Flow-Workflow (master)**

$ `git branch`
~~~
  develop
  feature1
* master
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git/Git-Flow-Workflow (master)**

$ `git pull`
~~~
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), done.
From https://github.com/AnanthaRajuC/Git-Flow-Workflow
   ea6a7a9..d3b63b8  master     -> origin/master
Updating ea6a7a9..d3b63b8
Fast-forward
 feature1.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature1.txt
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git/Git-Flow-Workflow (master)**

$ `git push`
~~~
Everything up-to-date
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git/Git-Flow-Workflow (master)**

$ `git tag "1.0.0.RELEASE" -m "Releasing version 1.0.0"`

**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git/Git-Flow-Workflow (master)**

$ `git push --tags`
~~~
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 184 bytes | 184.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To https://github.com/AnanthaRajuC/Git-Flow-Workflow.git
 * [new tag]         1.0.0.RELEASE -> 1.0.0.RELEASE
~~~
**johndoe@lp28 MINGW64 /c/John-Doe/eclipse-workspace/WS_E_2020/Learning-Git/Git-Flow-Workflow (master)**
~~~
$ `git branch`
  develop
  feature1
* master
~~~
----------------------------------------------------------------------------------------------------------