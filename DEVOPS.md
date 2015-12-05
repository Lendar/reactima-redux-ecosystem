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
* :fire:[Getting Started – Git-Flow](http://yakiloo.com/getting-started-git-flow/)
* [Visualizing Git Concepts with D3](https://onlywei.github.io/explain-git-with-d3/#rebase)
* [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/)

#### Creating a feature branch 
```
git checkout -b myfeature develop //Switched to a new branch "myfeature"
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

http://nvie.com/img/git-model@2x.png



