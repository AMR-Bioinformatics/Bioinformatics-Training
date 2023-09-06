# Git and Github

<img src="https://images.datacamp.com/image/upload/v1651047046/image8_0e61d0dad8.png" width="1200" height="300">


If you’ve never used git or github before, there are a bunch of things that you need to do. It’s [very well explained on github](https://help.github.com/articles/set-up-git), but repeated here for completeness.
- Get a github account
- Download and install git. For Linux users, this comes already preinstalled. To check, simply type ```git --version``` on your terminal
  - To install git on ubuntu, `$ sudo apt-get update` followed by `$ sudo apt-get install git`

## Setting up ssh on your computer
To get us started, we will use [Github’s guide to generating SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh).
This simply includes 4 basic steps:-
  - Check for an existing SSH key
  - Generate new SSH key
  - Add the new SSH key to github
  - Test your ssh connection

# Working on Github from the command line
## Cloning a github repo to your local machine
1. Create a Github repo called 'Working_with_Git'
2. Clone the repository into your current working directory
  - Each GitHub repo has a green `<> Code` button you can click to get either an HTTP, CLI or SSH URL that allows the repo to be cloned.
  - Copy your repository’s SSH URL and you’re ready to perform the GitHub SSH clone operation
  - Type `git clone (copied_url)` on your terminal
3. cd into the Working_with_Git folder

## Manipulate your local repository
1. Create a python script in your directory:
    ```nano myFirstFile.py```
2. Inside the file, write code to print the text “Hello World!”
    ```print(“Hello World!”)```
3. Save the file `Ctrl+S` then press `Ctrl+X` to exit
4. Run python file in terminal:
```$python myFirstFile.py```

## How to Add/remove the file to/from the cloud repository:
  - working directory = Untracked files (red)
    working directory - you can make changes in file and don’t have to commit those changes; git won’t care about these files
  - staging area = Tracked files (green). Changes that are ready to be committed, meaning git will keep track of the changes in these files
  - commit = Officially saving the repository at a point in time (i.e. saving the current state of all the tracked files in our git record)

![Git staging](https://res.cloudinary.com/practicaldev/image/fetch/s--D7nJOADN--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://cl.ly/569e7f0bbfaf/download/Image%25202018-08-29%2520at%25208.26.35%2520PM.png)

`Note:` You can read more on the staging area at https://git-scm.com/about/staging-area

### How to Commit changes in your local repo to the Cloud repo
#### Using git commands
1. ```$git status``` Use git status to help you see staged files and unstaged files

2. ```$git add .``` Tracks all changes in the local repo (move into the staging area)

3. ```$git status``` 

4. ```$git rm --cached (fileName)``` Untrack a file (move back into working directory)

5. ```git status```

6. ```git commit -m "your_message_here"``` This command commits everything that is in
staging area. `NB` Add a concise description or summary within the quotation marks of what you
changed/added/deleted. This helps other programmers who might look through your commits. If you don’t provide a description, then you will get prompted to add one

7. ```git log --oneline``` Presents a oneliner of what your commit looks like

8. ```git push```  Uploads the changes in your local repo to your github repo

**Now Check your pushed repository on GitHub: (it should be synced on GitHub) .Re-click the name of the repository you created on GitHub and your pushed data should appear**

## Make the following changes on the cloud repo and append them to your local repo
Edit the myFirstFile.py file and add the following line of code

```print("Today is a great day! I have learnt how to use github from the command line")```

Once you have done this, commit your changes to the repo

## How to update your local repository
Now that you already cloned your repo, you don't have to delete and reclone your github repo

Simply cd into the local repo directory 'Working_with_Git' and run the command ```git pull```

The command `git pull` is used to fetch and download content from a remote
repository and immediately update the local repository to match that content

### To confirm the success of the pull operation
Run ```python myFirstFile.py``` and check the output
