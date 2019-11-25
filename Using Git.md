# **Notes from Cesar's talk on Github**

## Setting up a git folder on your local comp

Below is a chunk of bash code (do in terminal) you can use to setup your own directory to work from:
```{bash, echo=TRUE, eval = FALSE}
ls #list the files present
cd Documents #change directory
mkdir our_amazing_project #make a directory
cd our_amazing_project
touch intro.md #create a new folder in directory
open -e intro.md #open editor
git init #initialise git
```
Response will be something like:

```Initialized empty Git repository in /Users/#####/Documents/our_amazing_project/.git/``` 

Basically, where all the magic happens.

### Check your git status
To see what's going on:
```{bash, echo= TRUE, eval=FALSE}
git status
```
RESPONSE:

```On branch master```

```No commits yet```

```Untracked files:```

```(use "git add <file>..." to include in what will be committed)```

```intro.md```
  
```nothing added to commit but untracked files present (use "git add" to track)``` 
  
  

*intro.md* will be in RED to change to GREEN:
```{bash, echo = TRUE, eval = FALSE}
git add intro.md
git status
```
RESPONSE:

```On branch master```

```No commits yet```

```Changes to be committed:```
  ```(use "git rm --cached <file>..." to unstage)```

	```new file: intro.md```
	
	
Finally, to commit it with a message (*-m*):
```{bash,  echo = TRUE, eval = FALSE}
git commit -m "create file, and write project description" # -m is for message w/ commit
```
RESPONSE:

```[master (root-commit) 71d0c43] create file, and write project description```
``` 1 file changed, 0 insertions(+), 0 deletions(-)```
``` create mode 100644 intro.md```

### To keep track of changes

Tells you what has happened so far:
```{bash,  echo = TRUE, eval = FALSE} 
git log
```
RESPONSE:

```commit 71d0c43a84c6a124a17ca1d20ddbc7d7c5b5deaa (HEAD -> master)```

```Author: ###### <####4@###.com>```

```Date:   Mon Nov 25 11:19:30 2019 +1000```

```create file, and write project description```


### Edit file:
```{bash,  echo = TRUE, eval = FALSE}
open -e intro.md
# add a new sentence to file
git status # still red
git add intro.md
git status # green
git commit -m "1st sentence"
```

### New file:
```{bash,  echo = TRUE, eval = FALSE}
git add contributors.md
open -e contributors.md
#add our names
git add contributors.md
git commit -m "list of peeps"
```

### New directory for data
```{bash,  echo = TRUE, eval = FALSE}
mkdir data
cd data
touch sensible_data.md
#go back to main folder
cd ..
vi .giignore
# write instructions in .gitignore e.g. to ignore 'data/' and '*.jpeg' any phtoto files
#write by pressing i and save and close by doing 'esc +:wq'
git add .gitignore
git commit -m "what to ignore"
git status
git log
```

'ls -ls' see all files and permissions

### Other tidbits:

```{bash,  echo = TRUE, eval = FALSE}
git checkout head # see begining work
git checkout master # where you're at now
```

## PUBLISH TO GIT:

- Go to git hub page
- Click '+ new' or, 'add repository'
- Fill in deets
- Don't tick/click bottom box (readme and gitignore)
- Click next

A README file is needed so create one:

```{bash,  echo = TRUE, eval = FALSE}
touch README.md #create
open -e README.md #edit
git status #check
git add README.md #add
git commit -m "readme uploaded" #commit
```

### Connect to git repository through local comp:
**Think this part is incorrect, Cesar can you edit please?**
```{bash, eval= FALSE, echo = TRUE}
 git remote add origin git@github.com:#####/our_amazing_project.git # insert your name
 git remote -v
 git push origin -master 
``` 
 
### Clone someones repository
```{bash,  echo = TRUE, eval = FALSE}
 cd ..
 git clone https://github.com/CexyNature/our_amazing_project.git # copy from 'clone' tab on repository
```
 
 
```{bash,  echo = TRUE, eval = FALSE}
 git push # push to repository, if you don't have permission then you can do
 git fetch # compare what is on m local machine and what is on my github
```
 

 
