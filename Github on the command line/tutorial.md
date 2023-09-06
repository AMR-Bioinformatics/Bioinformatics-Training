# Git and Github

If you’ve never used git or github before, there are a bunch of things that you need to do. It’s [very well explained on github](https://help.github.com/articles/set-up-git), but repeated here for completeness.
- Get a github account
- Download and install git
  - For ubuntu users `$ sudo apt-get update` followed by `$ sudo apt-get install git`

## Setting up ssh on your computer
To get us started, we will use [Github’s guide to generating SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh).
This simply includes 4 basic steps:-
  - Check for an existing SSH key
  - Generate new SSH key
  - Add the new SSH key to github
  - Test your ssh connection

## Working on Github from the command line
1. Create a Github repo called 'Working_with_Git'
2. Clone the repository into your current working directory
3. cd into the Working_with_Git folder
4. Create a python script in your directory:
    ```nano myFirstFile.py```
5. Inside the file, write code to print the text “Hello World!”
    ```Print(“Hello World!”)```
6. Save the file `Ctrl+S` then press `Ctrl+X` to exit
7. Run python file in terminal:
```$python myFirstFile.py```
