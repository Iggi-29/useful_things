# Git commands
I will be using this very simple repository in order to have a fast access to the most used commands in git and operations in git and Git-Hub.

## Adding an SSH key
### On windows
GO to C:\Users\username\.ssh and check that you have the id_rsa, id_rsa.pub, known_hosts and known_hosts.old, if this files are there, go to id_rsa.pub and add it into your account if it is not there. If the files do not appear or some is missing remove all the contents of the folder and start generating them. To do so open power shell and pass the following commands: ssh-keygen -o -t rsa -c "your email if wanted", do not specify any file anme and any passphrase (it is not necessary), this will create the id_rsa and the id_rsa.pub files. Add the ssh key to your account and the next time you use it (only first) when cloning for example a repo you will be asked if you want to use it, type yes and the ssh key has been enabled !
<br>
Here a guide on how to do it: https://www.youtube.com/watch?v=Irj-2tmV0JM&lc=Ugzh8-D4uZ83ENeMkwp4AaABAg

### On Linux
On Linux this commands will be enough:<br />
`cd ~/.shh`<br />
`ssh-keygen -t rsa -b 4096 -C "your email if wanted"`<br />
`eval $(ssh-agent -s)`<br />
`ssh-add "/home/username/.ssh/ssh_file_name"`<br />

Add then the add public key to your account.<br />
<br />
Here a guide on how to do it: https://www.youtube.com/watch?v=EoLrCX1VVog&t=77s

## Introducing Git into a repository. 
This are the commands that we will be using in order to start a git instance in any directory and connect it with a remote repo in Git-Hub.<br />
`git init`<br />
`git add .`<br />
`git commit -m "first commit"`<br />
`git remote add origin git@github.com:username/name_of_repo` Connect the local directory to Git-Hub.<br />
`git push -u origin main` Normally the main branch is the first created.<br />

## The basic commands staging your changes
`git init` Start a git instance, now files in the directory will be tracked.<br />
`git status` Check the status of your files.<br />
`git add name_of_files` Add the files to git so it tracks them.<br />
`git commit -m "message"` Commit the changes done staged by the add command.<br />
`git push` Push the changes to the remote version of the repository in Git-Hub.<br />

## Create and work with branches
`git branch` Get the branches of the project and locate the working branch.<br />
`git checkout -b name_of_the_branch` Create a new branch.<br />
`git checkout name_of_the_branch` Change the branch you are in.<br />
`git push --set-upstream origin name_of_the_branch` Push that new branch to the remote repository. <br />
`git merge name_of_the_branch_to_merge_in`<br /><br />

#### Special case (Change the the name of a branch)
`git branch -m new_branch_name`<br />
`git push origin -u new_branch_name`<br />
`git push origin --delete old_branch_name `

## Get information from the remote version of the repository to our machine
`git clone ___` Download the remote repository from Git-Hub to the local machine.<br /> 
`git fetch` Get all the info from all the existing branches remotely.<br />
`git pull origin name_of_the_branch` Pull a branch.<br />
`git push origin name_of_the_branch` Push a branch.<br />

#### Special case (Clone a single branch of a project)
`git clone --single-branch --branch name_of_the_branch ___`

# ZSH-Terminal
This is an extended version of the Bourne Shell (sh) - default terminal for Linux systems - which supports the use of plug-ins and is higly personalizable. In this section I will save some useful code to use this terminal.

## Install ZSH
`sudo apt install zsh` <br />
`sh -c $(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)`
`sudo chsh -s $(which zsh)` To make the zsh as default terminal.<br /> 

## ZSH Terminal setup
#### Themes
We will download and install the MesloLGS NF font which can be found at the github link below. <br /> 
We will also use the powerlevel10k theme to get a good and visually atractive and also useful terminal: https://github.com/romkatv/powerlevel10k.<br /> 

#### Plug-ins
Syntax highlighting: https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md
Autosuggestion: https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md<br /> 
You-should-use: 

## Uninstall ZSH
`sudo apt-get --purge remove zsh`

# Anaconda 
Anaconda is a python (and R) open-source which includes multiple tools that can make it quite easy to download, install and work with different bioinformatic  tools. The key pro to learn anaconda is the use of different environments which enable us to work with different versions of R and Python and libraries with ease. I will put here some useful commands I normally use or that I have to use and that in some cases I tend to forget.

## Anaconda environments management
`conda create --name "env name"` Create an environment. <br /> 
`conda activate/deactivate "env name"` Activate or Deactivate an environment. <br />
`conda remove --name "env name" --all` Remove an environment. <br />
`conda env list` List all the installed environments.<br /> 
`conda list "name of package"` All the packages/tools installed in your.<br />  environment, if we specify a package/tool it will show them only. <br /> 

### Use-case (Install STAR 8.9.3 with python3)
`conda create -n star_env python=3.9` <br />
`conda install -c bioconda star=8.9.3` <br />

## Import and export 
`conda env export | grep -v "^prefix: " > environment.yml` Save the environment state of the current environment.<br />
`conda env create -f environment.yml` Create an environment from a .yml file.

