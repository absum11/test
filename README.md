# Basic steps to get started with GIT

In order to install git visit git-scm.com and follow the necessary steps to complete the installation as mentionedithub on 
the website.

# Git initial setup

We will assume a few information about a hypothetical person so as to proceed with the setup.

Assumoptions :
1. Github username            : sampleuser
2. Github email               : samplemail@gmail.com 
3. A demo project folder name : DemoProject

Now, we set the username and email in the config list

**View config list**
```
git config --list
```

**Set the username and email**

1. Setting the email
```
git config --global user.email "samplemail@gmail.com"
```

2. Setting the username
```
git config --global user.name "sampleuser"
```


# Creating our own project and managing it

We will begin with learning how to create our own project and how to manage it; followed by how to contribute to someone 
else's project.


**General things one must know**

1. The URL of your github account is always of the form

```
https://github.com/your-github-username
```
which in our case will be 

```
https://github.com/sampleuser
```

2. Your repositories / project folder / project directories will have URL of the form

```
https://github.com/your-github-username/your-repository-name
```

which in our case will be

```
https://github.com/sampleuser/DemoProject
```
there can be more than one projects/repositories but they should have different names and their links will follow the pattern
accordingly as mentioned above.


**Step-1 : Making a local git repository**

Navigate to the folder where you want to create your project folder. Let's say we want to name it *DemoProject*.

1. Create a folder named DemoProject.
2. Open your gitbash or command prompt or terminal within this DemoProject folder.
3. Now, we need to initialize this folder as a git repository so that we can make use of git in order to track the folder.
   Type the following command to initialize the folder as a git repository:
   
   ```
   git init
   ```
   Once you type this command, a folder by the name *.git* is created within the *DemoProject* folder. Incase if it's not 
   visible then try to enable show hidden files and folders options.
   
   This *.git* folder is responsible to log every commit history and every other information required for your remote 
   repository, version control, commits etc. **WARNING : DO NOT DELETE THIS FOLDER EVER**
   
**Step-2 : Creating a repository on Github**

1. Open github and click on create new repository. (The placement of button may differ from time to time depending upon 
   changes in the UI.
2. Write the name and description (optional) for the repository. Then hit create repository.
3. Once created, it shows a link which will be of the following form
   
   ```
   https://github.com/your-github-username/your-repository-name.git
   ```
   Copy the link.

**Step-3 : Linking the local repository with the repository created on github**

1. Open the terminal / command prompt / git bash in the local repository created in **Step-1**. 
2. Type the following command in order to add the origin
   
   ```
   git remote add origin "<Link-you-copied-in-Step-2>"
   ```
3. In order to check if this executed successfully, type 

   ```
   git remote -v
   ```
   This should show an output something like
   
   ```
   origin https://github.com/your-github-username/your-repository-name.git (fetch)
   origin https://github.com/your-github-username/your-repository-name.git (push)
   ```
 
**Step-4 : Creating a file and commiting it**

1. Create a file inside the ProjectDemo folder. Let's say we create a file by the name *samplefile.txt*.
2. (Optional Step) Type **git status** in order to see if the file is tracked or not. Any file/folder shown in red color has been created/modified/deleted after the last commit. Whereas any file/folder shown in green has been added to the staging area.

3. Now in order to add the file to staging area so that we can commit it, type the following command :
   ```
   git add <file-name>
   ```
   which in our case will be
   ```
   git add samplefile.txt
   ```
   Note that in case of multiple files, one can use of follwoing command in order to stage all the files that were  created    /modified/deleted after the last commit, in one go :
   ```
   git add .
   ```
   
4. Now, that the files are staged, we will commit the staged files. Type the following command :
   
   ```
   git commit -m "Your commit message"
   ```
   
   This command commits all the changes that were staged. Make sure to write a meaningful commit message as this helps
   provide context, helps you get the most out of version control. Meaningful messages do more than state the obvious, they    indicate why a change happened.Effective commit messages help you and your team understand why certain changes were          introduced.
   
5. Now the commit has been made. You can view all of the commit history with the help of
   
   ```
   git log
   ```

**Step-5 : Pushing to the remote**

Now that we made some local changes and committed the same, it is time to push these changes to the repository we created on github. So that the code is available for others to view and use (repository will be visible to others if it is public).

```
git push origin master
```
We push the master branch to the remote. 
**Note :** Although it is not mandatory but it is a good practice to keep the working code in master branch and make any kind of changes in another branch and merge it with master once it's tried and tested. We will be covering branches in upcoming sections.  


With these basic 5 Steps, your basic project management with git is achieved. However it is not everything that one uses. There are other needful commands too that one uses while managing his/her project. Let's have a look at one such aspect of git : **Branches**
