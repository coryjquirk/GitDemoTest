# GitDemoTest

This is a GitHub demo to demonstrate my Git method for the purposes of our Java bootcamp cohort. I am using the command line method using the [BASH shell](https://git-scm.com/downloads).  

This guide focuses on creating a new GitHub repository and making your first couple of pulls and commits. The audience is Java students managing versions for solo projects. I may add further detail about navigating branches in the future.  

### Definitions
<strong>Local machine</strong>: the PC/device that you're coding on.  
<strong>Remote repository</strong>: the repository hosted by GitHub which can be pulled down to any authorized machine in the world.  
<strong>Git</strong> is a technology for version management, whereas <strong>GitHub</strong> is a platform for Git provided by just one company of several others.  
<strong>repo</strong>: short for 'repository'.  

### Prerequisites    
- Have Git installed on your machine.  
- Authenticate your GitHub account.
- SSH keys  
    - GitHub.com > Settings > SSH and GPG Keys  
    - You will need to set up keys with each machine you code on.  
- Have some kind of project files on your local machine that you want to store in a GitHub repository.  

### Steps  
1. Initialize a new repository on the GitHub website.  
    GitHub.com > Your repositories > New  
    - Choose whether the repo is public or private (public repositories are a good idea for showcasing your skills)  
    - `gitignore` files are optional but may help to greatly declutter and minimize the size of your applications for more complex projects in the future.
    - License: As a software development student I typically just select `The Unlicense`.  
2. Clone the repository to your local machine.  
    - e.g. `git clone git@github.com:coryjquirk/GitDemoTest.git`  
    - This will only need to be done one time for this repository on this machine.  
    - This step initializes the empty repo to your machine.  
    - At this point, move the desired local files into the empty git directory (e.g. GitDemoTest). 
3. Add your local files to the git repo.  
    - `git add .`  
        - [alternatively](https://git-scm.com/docs/git-add) `git add -A`  
    - When this step is complete, your modified files are now staged for the commit step.  
4. Commit the staged files.  
    - `git commit -m "my commit message"`  
    - You must enter a commit message or this command will be rejected.  
5. Push your committed files to the remote repository.  
    - `git push origin main`, `main` could be whichever branch.
    - If you do not have the latest version of the branch on your local machine, you will need to perform a `git pull` first, otherwise trying to push will kick you an error. 
        - Be careful not to overwrite the changes you have made locally, and be aware of the differences between your local code and the remote repository's code.  
6. Keep performing this cycle as you make improvements to your code. Keep the remote repo up to date and make frequent commitments of working code.

Please see `bashcommands.txt` for a log of the commands used in my class demonstration on Thursday 10 March 2022.

### Notes on the above process  
- At any point in these steps, use `git status` to get a report on whether the shell's present working directory is up to date with the remote repo.  
- All of the commands listed can take other optional arguments, but these command templates are what work for me.  
- When you clone a repository to your local machine, a  `.git` folder will be created, which identifies that directory as a repo on your machine (this is also done through the `git init` command, but I use the above method as an alternative). However, there is a default setting in Windows called "hidden files" which hides some of the more technical directories/files in your File Explorer. This contains Git configuration settings for this particular repo.
    - To view hidden files, look for the setting to reveal them under View in File Explorer.    

### Best practices  
Never commit broken code.  

Get in the habit of making short but meaningful commit messages to describe what you changed (e.g. 'added x new functionality' or 'removed references to unsupported dependency', not things like 'asdfasdfasdf' or 'tuesday commit')  

In group projects, work on large project changes on a new branch and merge it once you know the code works.  

For complex applications, use test deployments to ensure your hosting platform will accept the new changes.
    - For example, there are a few GitHub repos I have configured to automatically deploy to [Heroku](https://id.heroku.com/login). 
    - My [Portfolio website](https://github.com/coryjquirk/portfolio) is an app where I want an uninterrupted deployment, so I have a [test deployment](https://portfolio-tester.herokuapp.com/) sourced from a test branch and a [main deployment](https://coryjquirk.herokuapp.com/) sourced from the main branch. 
        - This is similar to a CI/CD pipeline.   
        
Communicate with other developers about which branch you are working on.  

### Other general notes on Git 
- GitHub offers free hosting via [GitHub Pages](https://pages.github.com/). To deploy an application, visit the webpage for your GitHub repo > Settings > Pages.
    - example:  
        - repo: https://github.com/coryjquirk/weather-dashboard/ 
        - deployed page: https://coryjquirk.github.io/weather-dashboard/index.html
- GitHub along with many other platforms/companies have abandoned `master`/`slave` terminology in the past few years. Previously, `master` was the default name for the primary Git branch, but this has been changed in favor of `main` as the default branch name. 
    - Some companies have replaced this with `parent`/`child` depending on the situation and technology.
    - `git init` may still initialize a repository with `master` as the main branch name. 
         - [To remedy this](https://superuser.com/questions/1419613/change-git-init-default-branch-name), use `git config --global init.defaultBranch main`
- Fun fact, you can hit the `.` key while on the web page for any GitHub repository, and the code will open in a rudimentary Visual Studio Code-esque IDE.   
![GitHub Dev screenshot](/github-dot-dev-screenshot.png)

- To change your default IntelliJ terminal to Git BASH: File> Settings > Tools > Terminal > Shell path  
![IntelliJ default shell](/IntelliJ-shell-screenshot.png)

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
