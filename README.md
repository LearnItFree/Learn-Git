**GIT** workflow :

``` sh
                                                GIT Structure
    -------------------------------------------------------------------------------------------------------------
   |                                                                                                             |
   |                git add                    git commit                       git push                         |
   | WORKING AREA -----------> STAGGING AREA --------------> LOCAL REPOSITORY ------------> REMOTE REPOSITORY    |
   |                                                                                                             |
   |                                                                                                             |
    -------------------------------------------------------------------------------------------------------------

```
### To initalizing the git on our local machine (it will create a local Repo). It will create the .git folder in current directory

``` bash

git init 

```

<video loop controls autoplay muted height="350px" width="550px">
<source src="./Vide/gitinit.mp4" type="video/mp4">
video not found
</video>

### The configuration must be required. Its like author information (metadata) and it's a one time activity

``` bash

git config --global user.name "give here username"

git config --global user.email "give here email address" 

```

### It will list the all of our username and email's 

``` bash

git config --gloabl --list

```

### Here we are adding the aliasname to remote repository 

``` bash

git remote add <aliasname> <Repository_url>

ex: git remote add giturl https://github.com/exampleuser/Project.git

```

### It will list all of the alias name only

``` bash

git remote

```  

### It will list the alias name's and the Repository_url's

``` bash

git remote -v

output example:

giturl https://github.com/exampleuser/Project.git (fetch)

giturl https://github.com/exampleuser/Project.git (push)

```

### It will give status of the current position

``` bash

git status

```

### We can rename our remote repo alias name

``` bash

git remote rename <old_aliasname> <new_aliasname>

ex: git remote rename giturl repourl

```

### We can remove the aliasname. It's like a removing the git repository url from the local repository

``` bash

git remote remove <aliasname>

ex: git remote remove repourl

```
### Here we are adding file to stagging area

``` bash

git add <path of directoryname/filename>

ex: git add . ---> here we moving current directory from working area to stagging area

ex: git add test.txt ---> here we moving particular file from working area to stagging area

ex: git add DevOps ---> here were moving particular folder from working area to stagging area

```
### We are moving files from stagging area to local repo.

``` bash

git commit -m "Give here message what we done actually to easilt understand"

ex: git commit -m "these is my first commiting of dev project"

```

### Here we can list all of our commit ID's

``` bash

git log 

git log options: --graph, --oneline, --all

```

### Here it will give detailed information about the commit id

``` bash

git show <commitid>

```

### Here we are pushing the files to the remote repo ( github/gitlab ). While pushing file from local repository to remote repository it will ask the credentials of the github (or) gitlab account

``` bash

git push <aliasname/Repository_url> <branch_name>

ex: git push repourl master (or) git push https://github.com/exampleuser/Project.git master

```

### It will list all of our files including the stagging area also

``` bash

git ls-files

```

### It will list files in local repository with long list

``` bash

git ls-tree <branchname> or HEAD

ex: git ls-tree HEAD

```

### It will list files in master branch with long list. we can list files from the particular branch 

``` bash

git ls-tree master

```

### It will list recuersively and list with files name only.

``` bash
git ls-tree master/HEAD -r --name-only

```

What is **GIT Revert** ?

ANS: In simple words to say it will undo the changes of new source-code/file anything.
For example, we release a webapplication:v1 and now we are creating a new version of webapplication:v2 after all getting done then wepush the v2 to remote repository then that v2 have some bug issuse (or) webapplication not comming up in that case we can use the gitrevert it will go back to previos version of the webapplication:v1 (switiching to old version).

### Here we need to give the webapplication:v2 commit id (give the latest commit id to undo changes)

``` bash

git revert <commitid>

```

What is **GIT Reset** ?

ANS: By mistakely we add file/directory to stagging area. we can take it back to the working area (unstagging)
It's opposite to git add means unstagging the file.
It will send back the files into working. (WORKING AREA <---git reset--- STAGGING AREA)

### It will gone a send back to the working area. working area nothing but unstagging

``` bash

git reset filename/directoryname

```

What is **GIT Branch** ?

ANS: Branch represents as a independnent of development. By using branch we can separate the environment like dev branch, porduction environment, qa environment like these we can work at individual branches. we can switch particular branch with out touching/changinganything on other branches.

By, default we have master branch in local repository

### It will add a new branch

``` bash

git branch <branchname>

```

### It will delete the merge merged branches

``` bash

git branch -d <branchname>

```

### It will delete the unmerged branches

``` bash

git branch -D <branchname>

```

### It will list all branches of local repository. Here * represents as a currently working on that branch.

``` bash

git branch

```

### It will list all branches of Remote repository
### remote repository like aliasname/branchname. 
### It look like origin/dev when we clone the project it will show like these aliasname/branchname

``` bash

git branch -r

```

### It will list all branches including local and remote repository

``` bash

git branch -a

```

### we can switch the branch by using checkout or switch. Now we can work on that branch. These branch is HEAD now.

``` bash

git checkout <branchname> (or) git switch <branchname>

```

### It will create and switch/checkout to that branch

``` bash

git checkout -b <branchname> (or) git switch -c <branchname>

```

Any branch add/change a file in one branch it will won't apply to other branches. We can see that file only on current branch. 
In that case merge come to picture. By using merge we are going to merge the branches then we can see all files in that merge branch

### Currently we are in master branch, we need files from the dev branch then use below command

### We can get all files from the dev branch

``` bash

git merge <branchname> (currentbranch <----- branchname)

# ex: git merge dev

```

### We can push files from local repository to remote repository particular branch

``` bash

git push <aliasname/repository_url> <branchname>

```

### Pushing files into all branches in single time (push all refs).

``` bash

git push <aliasname/repository_url> --all

```

### We can see difference of the files by using these command

``` bash

git diff <filename1> <filename2>

```

## Git ignore:

In some cases we dont need to push some files to remote repository. In that case we need to create the .gitignore file and add files name of which files need to skip.

### Add the filenames to ignore that files pushing the remote repository

``` bash

i. touch .gitignore

ii. .gitignore

iii. git add .gitignore

iv. git commit -m "ignore the files"

v. git push <aliasname/repository_url> <branchname>

```

## Tag:

Tag will create the archive of the repository with version of tag. Tag can created by master branch only and apply to master branch only. It will pushed by master only.

### Adding tag name/value

``` bash

git tag <tagname>

```

### List the tags

``` bash

git tag

```

### Tagging the remote repository

``` bash

git push <aliasname/repository_url>  master tag <tagname>  

```

### It will push all tags to remote repository

``` bash

git push <aliasname/repository_url> master --tags

```

### Deleting the tags

``` bash

git tag -d <tagname>

```

## GIT stash:

we can store the stagging area files in stash. By using stash can apply to another branches to work there. git stash work only files are present in the stagging area.
Stash can apply in any branch to modify the same file

### It will store data into stash like stash@{0}, stash@{1}

``` bash

git stash

```

### It will list the stash

``` bash

git stash list

```

### Now stagging area files can see in current branch

``` bash

git stash apply <stashvlaue>

ex: git stash apply stash@{0}

```

### It will apply stash in current branch and remove/delete the stash{0} from the stash

``` bash

git stash pop <stashvale>

ex: git stash pop stash@{0}

```

### It will delete the stash 

``` bash

git stash drop <stashvalue>

ex: git stash drop stash@{0}

```

## GIT cherry-pick:

Apply the changes introduced by some existing commits 

### what have we done in that commit-id it will apply to current branch.
### For example we add a file and commit it and copy the commit id and go to other branch apply the cherry-pick we can that file in current branch.

``` bash

git cherry-pick <commitid>

```

## GIT CLONE:

It will clone entire the repository and it will get the branches and logs also.

``` bash

i. git clone <repository_url>
 
# It will clone or download the remote repo into our local machine

ii. git branch -r

#  We can list our remote branches

iii. git log --oneline --graph

# We can also list our log's

# By using clone we can modify files or adding something and we can push directrly without adding remote repo url. By default remote alias name will be "origin" 
iv. git push origin <branchname> by defualt origin is repository alias name

```

## GIT Pull:

It will pull file from the current/particular branch. git pull require initalizate local repositpry otherwise it won't work.
git pull = git fetch + git merge

``` bash

i. git init

# It pull all files from the master branch

ii. git pull <repository_url> 

# It will pull files from the particular branch

iii. git pull <repository_url> <bramchname>

```

## GIT Fetch:

Fetch required initalizate local repository and add repository url in local other it wont work

``` bash

i. git init

ii. git remote add giturl https://github.com/exampleuser/Project.git

iii. git remote -v

     giturl https://github.com/exampleuser/Project.git (fetch) * --> see here fetch is there we can fetch now

     giturl https://github.com/exampleuser/Project.git (push)

iv. git fetch <aliasname> <branchname>

v. git merge aliasname/branchname

# ex: git merge giturl/devlpoment

# We can't see the files without mergging.

```

## Git merge vs rebase

**GIT Merge**: Git merge is a command that allows you to merge branches. When you use Git merge, only the target branch is changed. 
The source branch history remains. Git merge adds a new commit, preserving the history.

**GIT Rebase**: Git rebase is a command that allows developers to integrate changes from one branch to another.It transfers the completedwork from one branch to another. In the process, unwanted history is eliminated. Git rebase can't create new commit_id it will overwrtie the commitid. 

NOTE: If you're working alone or on a small team, use rebase. If you're working with a big team, use merge. 

## GIT ssh:

``` bash

1) ssh-keygen
# genarate the key 

2) cat ~/.ssh/id_rsa.pub
# copy the publick key and paste in github

3) Go to github Account Setting and select the SSH and GPG keys options and add (paste) ssh publick key.

4) ssh -T git@github.com
# After you've set up your SSH key and added it to your GitHub account, you can test your connection  by using these command.

5) git remote add newurl git@github.com:exampleuser/Project.git
# newurl git@github.com:exampleuser/Project.git (fetch)
# newurl git@github.com:exampleuser/Project.git (push)

6) git push 
# Now we can push files remote repository directly without aunthentication.

```
