# GitHub commands
I will be using this very simple repository in order to have a fast access to the most used commands in git and operations in Git-Hub.

## Adding an SSH key
### On windows
GO to C:\Users\username\.ssh and check that you have the id_rsa, id_rsa.pub, known_hosts and known_hosts.old, if this files are there, go to id_rsa.pub and add it into your account if it is not there. If the files do not appear or some is missing remove all the contents of the folder and start generating them. To do so open power shell and pass the following commands: ssh-keygen -o -t rsa -c "your email if wanted", do not specify any file anme and any passphrase (it is not necessary), this will create the id_rsa and the id_rsa.pub files. Add the ssh key to your account and the next time you use it (only first) when cloning for example a repo you will be asked if you want to use it, type yes and the ssh key has been enabled !
<br>
Here a guide on how to do it: https://www.youtube.com/watch?v=Irj-2tmV0JM&lc=Ugzh8-D4uZ83ENeMkwp4AaABAg

### On Linux
On Linux this commands will be enough:
cd ~/.shh
ssh-keygen -t rsa -b 4096 -C "your email if wanted"
eval $(ssh-agent -s)
ssh-add "/home/username/.ssh/ssh_file_name"

Add then the add public key to your account.
<br>
Here a guide on how to do it: https://www.youtube.com/watch?v=EoLrCX1VVog&t=77s

## Introducing Git into a repository. 
This are the commands that we will be using in order to start a git instance in any directory and connect it with a remote repo in Git-Hub.
git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:username/name_of_repo; connect the local directory to Git-Hub.
git push -u origin main; normally the main branch is the first created.

## The basic commands staging your changes
git init; start a git instance, now files in the directory will be tracked.
git status; check the status of your files.
git add name_of_files; add the files to git so it tracks them.
git commit -m "message"; commit the changes done staged by the add command.
git push; push the changes to the remote version of the repository in Git-Hub.

## Create and work with branches
git branch; get the branches of the project and locate the working branch.
git checkout -b name_of_the_branch; create a new branch.
git checkout name_of_the_branch; change the branch you are in.
git push --set-upstream origin name_of_the_branch; push that new branch to the remote repository. 
git merge name_of_the_branch_to_merge_in
#### Special case
git branch -m new_branch_name
git push origin -u new_branch_name
git push origin --delete old_branch_name -> To change the name of a branch localy and remotely.

## Get information from the remote version of the repository to our machine
git clone ___; download the remote repository from Git-Hub to the local machine 
git fetch; get all the info from all the existing branches remotelly
git pull origin name_of_the_branch; pull a branch
git push origin name_of_the_branch; push a branch
#### Special case
git clone --single-branch --branch name_of_the_branch ___; Download a single branch of the project


