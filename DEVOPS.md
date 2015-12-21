## Node.js & Devops related notes
This is an attempt to collect all devops and security issues rising arround ES6/Node/React/Redux ecosystem

### Node
* [10 Habits of a Happy Node Hacker (2016)](http://blog.heroku.com/archives/2015/11/10/node-habits-2016#6-be-environmentally-aware)
* [Node.js Interview Questions and Answers](https://blog.risingstack.com/node-js-interview-questions/)
* [Debugging Memory Leaks in Node.js Applications](http://www.toptal.com/nodejs/debugging-memory-leaks-node-js-applications)
* Optional
  * [MAKEFILE RECIPES FOR NODE.JS PACKAGES by Andrey Popp 2013/05/16](https://andreypopp.com/posts/2013-05-16-makefile-recipes-for-node-js.html)
  * [Making the case for make](http://shapeshed.com/making-the-case-for-make/)

### Docker
* https://www.datadoghq.com/docker-adoption/
* [Docker Swarm](https://docs.docker.com/swarm/) Docker Swarm is native clustering for Docker, it allows you create and access to a pool of Docker hosts using the full suite of Docker tools. Because Docker Swarm serves the standard Docker API, any tool that already communicates with a Docker daemon can use Swarm to transparently scale to multiple hosts. 
* [97-things-every-programmer-should-know](https://github.com/xmalinov/97-things-every-programmer-should-know/blob/master/en/SUMMARY.md)
* [What PostgreSQL has over other open source SQL databases: Part II](https://www.compose.io/articles/what-postgresql-has-over-other-open-source-sql-databases-part-ii/)
* [Grafana](http://grafana.org/) - the leading graph and dashboard builder for visualizing time series metrics. 
* [tj/mon](https://github.com/tj/mon) tj's replacement of monit
* [AWS in plain English](https://www.expeditedssl.com/aws-in-plain-english)
* :fire:[Visualizing Docker Containers and Images](http://merrigrove.blogspot.ru/2015/10/visualizing-docker-containers-and-images.html)

### Security
* [OAuth Has Ruined Everything](http://developer.telerik.com/featured/oauth-has-ruined-everything/)
* [Installing fail2ban on CentOS 7](http://unix.stackexchange.com/questions/171567/installing-fail2ban-on-centos-7) 
* [Top Overlooked Security Threats to Node Apps: ](https://speakerdeck.com/player/c5d895008c77013162b85e7a2e8ee0d7?#)
* [OAuth 2 VS JSON Web Tokens: How to secure an API](http://kidtronnix.com/2015/03/05/Oauth-2-VS-Json-Web-Tokens/)


### GIT
* :clapper: egghead.io [How to Write an Open Source JavaScript Library](https://egghead.io/lessons/javascript-how-to-write-a-javascript-library-setting-up-github?series=how-to-write-an-open-source-javascript-library)
* git-scm.com [Git Basics](http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)
* [How to Write a Git Commit Message](http://chris.beams.io/posts/git-commit/)
* :bomb: [Changing Git history or what to do when you have a mess on your hands](http://justinhileman.info/article/git-pretty/)
* :fire:[Getting Started – Git-Flow](http://yakiloo.com/getting-started-git-flow/)
* [Visualizing Git Concepts with D3](https://onlywei.github.io/explain-git-with-d3/#rebase)
* [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/)

#### Creating a feature branch 
```
git checkout -b myfeature develop
``` 
#### Incorporating a finished feature on develop ¶ 
```
git checkout develop
git merge --no-ff myfeature
git branch -d myfeature
git push origin develop
```
#### Creating a release branch ¶
```
git checkout -b release-1.2 develop
./bump-version.sh 1.2
git commit -a -m "Bumped version number to 1.2"
```
#### Finishing a release branch ¶
```
git checkout master
git merge --no-ff release-1.2
git tag -a 1.2
```
 * To keep the changes made in the release branch, we need to merge those back into develop, though. In Git:
```
git checkout develop
git merge --no-ff release-1.2
Merge made by recursive.
```
 * This step may well lead to a merge conflict (probably even, since we have changed the version number). If so, fix it and commit.
```
git branch -d release-1.2
```
#### Creating the hotfix branch 
```
git checkout -b hotfix-1.2.1 master
./bump-version.sh 1.2.1
git commit -a -m "Bumped version number to 1.2.1"
```
  * Then, fix the bug and commit the fix in one or more separate commits.
```
git commit -m "Fixed severe production problem"
```
#### Finishing a hotfix branch
```
git checkout master
git merge --no-ff hotfix-1.2.1
git tag -a 1.2.1
```
 * Next, include the bugfix in develop, too:
```
git checkout develop
git merge --no-ff hotfix-1.2.1
```
The one exception to the rule here is that, when a release branch currently exists, the hotfix changes need to be merged into that release branch, instead of develop. Back-merging the bugfix into the release branch will eventually result in the bugfix being merged into develop too, when the release branch is finished. (If work in develop immediately requires this bugfix and cannot wait for the release branch to be finished, you may safely merge the bugfix into develop now already as well.)

 * Finally, remove the temporary branch:
```
git branch -d hotfix-1.2.1
```

![go](http://nvie.com/img/git-model@2x.png)



## Git Cheat Sheet
#### Configure
 * git config –global user.name "[name]"
   * Sets the name you want attached to your commit transactions
 * git config –global user.email "[email address]"
   * Sets the email you want attached to your commit transactions
 * git config –global color.ui auto
   * Enables helpful colorization of command line output
 * git config –global push.default current
   * Update a branch with the same name as current branch if no refspec is given
 * git config –global core.editor [editor]
   * Which editor to use when commit and tag that lets you edit messages
 * git config –global diff.tool [tool]
   * Specify which command to invoke as the specified tool for git difftool

#### Create repositories
 * git init [project-name]
   * Creates a new local repository with the specified name
 * git clone [url]
   * Downloads a project nd its entire version history

#### Make changes
 * git status
   * Lists all new or modified files to be committed
 * git status -s
   * Short view of status
 * git diff
   * Shows file differences not yet staged
 * git add [file]
   * Snapshots the file in preparation for versioning
 * git add .
   * Add all modified files to be commited
 * git add '*.txt'
   * Add only certain files
 * git add –patch filename.x (or -p for short)
   * Snapshot only chunks of a file
 * git rm [file]
   * Tell git not to track the file anymore
 * git diff –staged
   * Show what has been added to the index via git add but not yet committed
 * git diff HEAD
   * Shows what has changed since the last commit.
 * git diff HEAD^
   * Shows what has changed since the commit before the latest commit
 * git diff [branch]
   * Compare current branch to some other branch
 * git difftool -d
   * Same as diff, but opens changes via difftool that you have configured
 * git difftool -d master..
   * See only changes made in the current branch
 * git diff –no-commit-id –name-only –no-merges origin/master…
   * See only the file names that has changed in current branch
 * git diff –stat
   * See statistics on what files have changed and how
 * git reset [file]
   * Unstages the file, but preserves its contents
 * git commit
   * Record changes to git. Default editor will open for a commit message
 * git commit -m "[descriptive message]"
   * Records file snapshots permanently in version history
 * git commit –amend
   * Changing the history, of the HEAD commit

#### Group changes
 * git branch
   * Lists all local branches in the current directory
 * git branch [branch-name]
   * Create a new branch
 * git checkout [branch-name]
   * Switches to the specified branch and updates the working directory
 * git checkout -b <name> <remote>/<branch>
   * Switches to a remote branch
 * git checkout [filename]
   * Return file to it's previous version, if it hasn’t been staged yet
 * git merge [branch]
   * Combines the specified branch's history into the current branch
 * git merge –no–ff [branch]
   * Merge branch without fast forwarding
 * git branch -a
   * See the full list of local and remote branches
 * git branch -d [branch]
   * Deletes the specified branch
 * git branch -D [branch]
   * Hard branch delete, will not complain
 * git branch -m <old<sub>name</sub>> <new<sub>name</sub>>
   * Rename a branch

#### Refactor filenames
 * git rm [file]
   * Deletes the file from the working directory and stages the deletion
 * git rm –cached [file]
   * Removes the file from version control but preserves the file locally
 * git mv [file-original] [file-renamed]
   * Changes the file name and prepares it for commit

#### Suppress tracking
 * .gitignore
   * *.log
   * build/
   * temp-*
   * A text file named .gitignore suppresses accidental versioning of files and paths matching the specified patterns
 * git ls-files –other –ignored –exclude-standard
   * Lists all ignored files in this project
        
#### Save fragments
 * git stash
   * Temporarily stores all modified tracked files
 * git stash pop
   * Restores the most recently stashed files
 * git stash list
   * Lists all stashed changesets
 * git stash drop
   * Discards the most recently stashed changeset
        
#### Review history
 * git log
   * Lists version history for the current branch
 * git log –follow [file]
   * Lists version history for a file, including renames
 * git log –pretty=format:"%h %s" –graph
   * Pretty commit view, you can customize it as much as you want
 * git log –author='Name' –after={1.week.ago} –pretty=oneline –abbrev-commit
   * See what the author has worked on in the last week
 * git log –no-merges master..
   * See only changes in this branch
 * git diff [file-branch]…[second-branch]
   * Shows content differences between two branches
 * git show [commit]
   * Outputs metadata and content changes of the specified commit

#### Redo commits
 * git reset
   * Unstage pending changes, the changes will still remain on file system
 * git reset [commit/tag]
   * Undoes all commits after [commit], preserving changes locally
 * git reset –hard [commit]
   * Discards all history and changes back to the specified commit
        
#### Synchronize changes
 * git fetch [bookmark]
   * Downloads all history from the repository bookmark
 * git fetch -p
   * Update history of remote branches, you can fetch and purge
 * git merge [bookmark]/[branch]
   * Combines bookmark's branch into current local branch
 * git push
   * Push current branch to remote branch
 * git push [remote] [branch]
   * Manually specify remote and branch to use every time
 * git push -u origin master
   * If a remote branch is not set up as an upstream, you can make it so
 * git pull
   * Downloads bookmark history and incorporates changes
 * git pull [remote] [branch]
   * Specify to pull a specific branch
 * git remote
   * See list of remote repos available
 * git remote -v
   * Detailed view of remote repos available
 * git remote add [remote] [url]
   * Add a new remote


