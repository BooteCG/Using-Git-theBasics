# **Notes from Cesar's talk on Github**

## Setting up a git folder on your local comp

Below is a chunk of bash code (do in terminal) you can use to setup your own directory to work from:

> Please observe some bash command in the following code will work fine in operating systems based on UNIX (i.e. Linux and MacOS) but not in Windows OS. If you are working in Windows you can use a shell container (e.g. Cygwin or Windows 10 Linux Bash shell). Alternatively, you can use equivalent commands (e.g. instead of ```ls``` use ```dir```).

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

> Use the imperative mood for writing your commit messages. Commit messages describe not only what have changed, but more importantly these describe the reasons of the changes and the context. Please observe that using the flag ```-m``` only will allow you to write a subject line. If you need to write a more detailed commit message use ```git commit```, this will prompt an editor window where you can add a subject line and additional text.

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

> Windows OS users can use ```notepad intro.md``` instead of ```open -e intro.md```
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

> Windows users can use ```type nul > sensible_data.md``` instead of ```touch sensible_data.md```

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

## PUBLISH TO GIT:

GitHub will expect a ```README.md``` file, so create one:

```{bash,  echo = TRUE, eval = FALSE}
touch README.md #create
open -e README.md #edit
git status #check
git add README.md #add
git commit -m "readme uploaded" #commit
```

- Go to git hub page
- Click '+ new' or, 'add repository'
- Fill in deets
- GitHub will ask you if you want to create ```README.md``` and ```.gitignore``` files in your new repo. You have already created these files, so don't create these.
- Click next



### Connect to git repository through local comp:

> You will get the link for your new repository in GitHub, copy and paste it after ```git remote add origin ```

```{bash, eval= FALSE, echo = TRUE}
 git remote add origin git@github.com:#####/our_amazing_project.git # replace this with your own link
 git remote -v
 git push origin master # Push your local repo to your new remote GitHub repo
``` 
 
### Clone someones repository

> Before cloning a new repo be sure you are not inside an existing git project. ```git clone``` will create a new folder.
```{bash,  echo = TRUE, eval = FALSE}
 cd ..
 git clone https://github.com/CexyNature/our_amazing_project.git # copy from 'clone' tab on repository
```
 
 