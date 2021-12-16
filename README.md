# Git Course (Steps Specifically for Windows)

## Git Hub Configuration Locally

### Download Git in Windows

#### Git Configuration in Git Bash

     git config --global user.name "<User_Name>"

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
  
      $ git add <file_names>    |(or)|    $ git add .    (To add all the files)
  
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

      $ eval $(ssh-agent -s)     
      (A PID will be displayed if running)

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
     
## Branch Commands

       $ git branch <branch_name>           // To create a new branch
       $ git checkout <branch_name>         // To change to that branch 
       $ git push origin <branch_name>      // To push to that branch
       
### Use case

* Create a branch locally   
 
        $ git checkout -b <branch_name11>    
                              |
        ###### If this        V  branch is not there it will create a new branch with that name
     
* Branch will create a snapshot of the project. Hence make changes here in any file and it will not effect the main one

        Made changes in one of the file in this branch and commit   
        $ git commit -am "change Performed"    (This commit will be limited to this branch - the main branch is unaffected)   
             
        Hence this branch is available locally
        
* Pushing Locally available branch to the remote repo  
   
        $ git push -u origin branch_name11    
            
        This will create a new branch remotely also
        
        
## GitHub Flow   

*  You are asked to develop a feature for a project. So you will create a branch and start working on it, here you can have as many commits as you want as this is your own branch. Now you are done with implementation of that feature and you want someone to review it - you will raise a pull request to review, then the reviewer asked for some changes you will commit it and so on and now it is finalized and the reviewer will accept the pull request and it would be merged to the main branch. The branch you have created for feature development can be deleted.

### Creating Pull Request   
     
####  Pull Request -> New Pull Request -> Select Base and compare branches -> create new Pull request -> (Usually a template will be provided for Pull request with name pull_request_template.md.   
    
    
     
## Merge Conflicts

* After creating a branch, a new change is performed over the main branch and when you finally want to merge the created branch to the main branch there will be a conflict as both are not upto date.   

We need to clear the conflict with the button displayed in the github and then we are good to merge.


## Using Git blame  
    
* For any particular file, in the commits section, the changed file will be displayed and a boxed 3 dots will be displayed where in we can select the "git blame" option to view all changes that happened to the file over the time.


## Branching vs Forking

*  What branching is basically creating a branch of code available in the repository and the created branch will be available in that repo only. It is just like creating a branch for a tree.   

* Forking is creating a copy of the repository. It is like having a new tree itself.

##### Note: An author cannot perform fork







  
