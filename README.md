# Git Course (Steps Specifically for Windows)

## Git Hub Configuration Locally

### Download Git in Windows

#### Git Configuration in Git Bash

* git config --global user.name "<User_Name>"

#### Making Git open into default Code Editor

* Make sure you have the Environment vairiables defined for that Editor in "Path"  
  If VS Code --> we will be having "C:/....../Microsoft VS Code/bin"
  
  If set, then in Git Bash    
  $ code (and Enter) --> This is automatically opens up the VS Code
  
** Further settings related to Editor   

   $ git config --global core.editor "code --wait --new-window"   
   $ git config --edit --global
   
### Suppose you want some folder to be looked by Git for version control

* Then initialize Git    
  $ git init  (After Navigating to that respective folder)
  
* You have intialized Git have some files and you think these files are ok to be pushed to main repo

** Whats Main Repo ? 

*** Git works in a way that it has a working directory (That is where you have initialezed Git)    
    --> Then a staging Area (The files with git add but not yet committed will stay here)      
    --> Then there is a local repository (which not the main one)  
    --> Then there is a remote repository and this is the main one   
    
### Next Steps after init and files ready in working directory

* Now to now what are the files, use command:   
  $ git status   
  
  (Files will be displayed in red color that are not committed)
   
* Add those files which are in red color (becoz those are the files not in sync)   
  
  $ git add <file_names>  |(or)|  $ git add .    (To add all the files)
  
* Now the files are ready to be committed to the local repo   

  $ git commit -m "Some_commments_for_tracking"
  
## Connecting with GitHub 

### There are 2 ways for conneting to gitHub

* HTTP ( requires username/password everytime )
* SSH ( Link the SSH Key and thats it - a lot easier to work )

#### Generate SSH Key from Git Bash

##### $ ssh -keygen -t rsa -b 4096 -C "provide_email_of_gitHub"

###### Points to note after generating Key

* Check if SSH is running 

$ eval $(ssh-agent -s)   (A PID will be displayed if running)

* To add SSH Key   

$ ssh-add ~/.ssh/id_rsa   

A path will be displayed where the key is saved. Navigate to that path and Copy

* Now open your GitHub account -> Settings -> SSH and GPG Keys -> New SSH Key -> Paste, What is copied -> save

* Finally, from git bash we can directly connect using 

$ ssh -T git@github.com

## Pushing files from local repo to main(Remote) Repo

* Assuming all the steps till commit to local repo are done, Time to push to the Main Repo   

$ git push origin main

### Note: We can also make changes after pushing to github and commit, but then our local repo files will not be getting the latest changes

    * For that case we need to perform 2 more steps for updating local repo with changes from main repo
     
     $ git fetch   (To fetch changes)
     $ git pull 
     
     





  
