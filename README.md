# GitDemoTest

This is a GitHub demo to demonstrate my Git method for the purposes of our Java bootcamp cohort. I am using the command line method using the [BASH shell](https://git-scm.com/downloads).  

This guide focuses on creating a new GitHub repository and making your first couple of pulls and commits. The audience is Java students managing versions for solo projects. I may add further detail about navigating branches in the future.  

### Definitions
<strong>Local machine</strong>: the PC/device that you're coding on.  
<strong>Remote repository</strong>: the repository hosted by GitHub which can be pulled down to any authorized machine in the world.  
<strong>Git</strong> is a technology for version management, whereas <strong>GitHub</strong> is a platform for Git provided by just one company of several others.  

### Prerequisites    
- Have Git installed on your machine.  
    - GitHub.com > Your repositories > New
- Authenticate your GitHub account.
- SSH keys  
    - GitHub.com > Settings > SSH and GPG Keys  
    - You will need to set up keys with each machine you code on.  
- Have some kind of project files on your local machine that you want to store in a GitHub repository.  

### Steps  
1. Intialize a new repository on the GitHub website.  
2. Clone the repository to your local machine.  
    - e.g. `git clone git@github.com:coryjquirk/GitDemoTest.git`  
    - This will only need to be done one time for this repository on this machine.  
    - This step initializes the empty repository to your machine.  
    - At this point, move the desired local files into the empty git directory (e.g. GitDemoTest). 
4. Add your local files to the git repository.  
    - `git add .`  
        - [alternatively](https://git-scm.com/docs/git-add) `git add -A`  
    - When this step is complete, your modified files are now staged for the commit step.  
5. Commit the staged files.  
    - `git commit -m "my commit message"`  
    - You must enter a commit message or this command will be rejected.  
7. Push your committed files to the remote repository.  
    - `git push origin main`, `main` could be whichever branch.
    - If you do not have the latest version of the branch on your local machine, you will need to perform a `git pull` first, otherwise this will kick you an error. 
        - Be careful not to overwrite the changes you have made locally, and be aware of the differences between your local code and the remote repository's code.  

Please see `bashcommands.txt` for a log of the commands used in my class demonstration on Thursday 10 March 2022.

### Notes on the above process  
- At any point in these steps, use `git status` to get a report on whether the shell's present working directory 
- All of the commands listed can take other optional arguments, but these command templates work for me.  
- There will be a `.git` folder in every Git repository, but there is a default setting in Windows called "hidden files" which hides some of the more technical directories/files in your File Explorer. 
    - To view hidden files, look for a setting in File Explorer.    
- When you clone a repository to your local (this is also done with the `git init` command, but I use the above method as an alternative)

### General notes on Git 
- GitHub along with many other platforms/companies have abandoned `master`/`slave` terminiolgy in the past few years. Previously, `master` was the default name for the primary Git branch, but this has been changed in favor of `main` as the default branch name. 
    - Some companies have replaced this with `parent`/`child` depending on the situation and technology.
- Fun fact, you can hit the `.` key while on the web page for any GitHub repository, and the code will open in a rudimentary Visual Studio Code-esque IDE. 

### Git BASH shell useful commands  
`cd`: change directory  
`cd ..`: move back one step towards the root directory  
`cd ../..`: move back two steps  

`pwd`: present working directory    
`ls` and `dir`: lists files and directories in the present working directory  
`mkdir`: creates a directory  
`touch`: creates a file 

### Future topics I may add
- Creating a new branch to work on your own copy of the code, then merging this branch into the `main` branch when it's "ready for production".  
- GitHub integration for IDEs such as IntelliJ and Visual Studio Code  
- [GitHub Desktop](https://desktop.github.com/)
