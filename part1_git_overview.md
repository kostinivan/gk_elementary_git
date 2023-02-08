# git main features overview
ptaya:

![ptaya](git_image.png "Git")

git is a one of most popular version control systems. it allow you to develop huge projects with others and track all activity and changes. though, you can navigate not only through all text files (source codes), but all changes and it's authors (with blame to punish dumbs more percisely). check this out to get more information:
- [Github](github.com)
- [Gitlab](gitlab.com)
- [git branching trainer](https://learngitbranching.js.org/)

git has several pros in comparison with svn(subversion system). 
0) git stores only the difference(diff) - changes for every stage
## manage repositories
every repository on your host is a *local copy* of remote **original** repo<sitory>. so you can sync them in between to get updates from remote (with changes from your team) or - to update remote with changes you've made localy.
### create retository
`git init` - initialize git repository in current folder. Just create the *.git* folder with all neccesury staff inside.
### set remote copy
`git set remote <url>` - changest the remote URL of git repository to sync with. remote URL must exist 
### clone origin repository
`git clone <url>` - clones remote origin repo that exist. will create a folder with name of origin repo and sync all files with remote. so you do NOT need to `set remote` after clone

## manage branches
in every git repository there could be several branches that are easy to switch. the one **main**(or **master** or **trunk** or ) - the head of all other branches. it should be stable. other brunches should meet some requirements

0) no branch should live forever
1) one branch must serve to solve single task
2) after solving task branch should be merged
3) name of branch must tell about task that is solving there

### create
`git checkout -b <name>` - will create new branch from current HEAD localy and switch to it. *name* here - is the name of NEW branch being created - *-b* option stands for that
### switch
`git checkout <name>` - will switch to existing branch with name *name*. locally
### merge 
`git merge <name>` - will merge branch *name* into current branch. 
### delete 
`git branch --delete <name>` - will delete the branch *name*. you better not to delete any branch
### list
`git branch` - will show the list of all local branches. with option `-r` will show remote branches instead

## manage local copy
sometimes (everytime) it's better to save all changes you made. there is a little tricky thing. to save your changes on hard drive of your host there is enough to press `Ctrl+S` or something. but *git* will NO track your changes by defalut. you must clearly specify what files *git* should track and sync with remote origin. one file must be added to tracking after every changes you made

### add to track
`git add <path>` - will tell the *git* to add files specified to next commit. you can specify one file, or several files. or by pattern like `.` or `<subfolder>/*.cpp` - it will add all files in root repo folder (first case) or all files from *subfolder* with `.cpp`-extension. operation `add` will take into account content of file `.gitignore` where you can specify all files that should't be tracked (usually this is some specific thing of your host like *build* folder or some heavy files like input data -- git is mostly for source-files) 
### commit
`git commit -m "short capacious description of changes you've made since last commit"` - will save all changes = make a diff from previous commit with description you put after option `-m` which means `message`.
### add and track
`git commit -a -m "commit message"` - will add all files and make a commit. equivals to `git add .` followed by `git commit -m "commit message"`

## update&sync
be up to date. work with last version of code from remote. keep remote up to date with changes made localy.
### update from remote
* `git fetch` - asks remote to provide actual information about all changes in all branches that have been made in remote origin since last sync. do not affects your local files - just gets history
* `git pull` - updates your local copy of current branch from remote
### update remote
`git push` - will upload all changes that was added and commited localy to remote origin.
## berry
apply only specified commits and changes

`git cherry-pick <commit-hash>` - amazing thing

## navigate through versions
* `git rebase` - will move the HEAD to specified commit.
* `git reset`
* `git revert`
***coming soon...***




