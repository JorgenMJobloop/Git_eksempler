# Git commands

````sh
git init # initalize the repository

git branch -M main # creates the main branch

git status # checks the status of the source-control

git add . # add all the files we are working with

git commit -m "inital commit" # commits with the message we choose in string format with the -m flag.

git -set--upstream origin <branch_name> # sets the remote upstream for a github repo

git push # push the changes

git fetch # fetch changes

git pull # pull existing changes
````

# Collaborating in a repository

* automated shell scripts for commits, can help workflow

```sh
#!/bin/bash
message = "made changes to a file!";
echo $message; # sjekker at vi har riktig commit melding.
git commit -m $message
echo -e  "\nPaste your repository url here:";
read github_url;

git remote add origin $github_url;
git pull origin main; # pull eventual changes
git push origin main;

author = "https://github.com/jorgenmjobloop";

echo "written by $author"; 
```

```python
import os
import argparse
import subprocess

git_parser = argparse.ArgumentParser(
    prog="git",
    description="the git CLI",
    epilog="git is a distributed version control system"


)

commit_message = input(str("What changes did you make to the codebase? "))
print(commit_message) # print out the message to check that it is the correct message and that it is not too long.
if len(commit_message) > 32:
    print("Commit message is above max characters, please limit your message!")

else:
    print("...")
    
commit_changes = subprocess.Popen(f"git commit -m {commit_message}")
        

```