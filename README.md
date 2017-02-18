# Git Powertools

A set of powertools for git.

1. [Git rollup](#1-git-rollup) -- discards the history from the master branch.
2. [Git clone-all](#2-git-clone-all) -- clones all repositories of a given user.
3. [Links to additional awesome git tools](#3-links-to-additional-git-tools).

## 1. Git Rollup

Git rollup discards all the history from the `master` branch.

### Quick Start
Download git-rollup and make it executable by running:
~~~bash
	$  chmod u+x git-rollup
~~~

To rollup a repository, run from within the repository to rollup:
~~~bash
	$  Run git rollup COMMIT_MESSAGE
~~~

Git rollup commits the repository files to recreate the `master` branch with only the latest versions, as if it was a brand new repository. Git rollup does not delete or affect other branches (besides `latest_branch` which is used to recreate the `master` branch).

#### Important:
* **No Undo**: Git rollup cannot be undone!

* **Broken Forks**: All forks of the repository will stop working after!

### How It Works?
Git rollup creates a new temporary branch (latest_branch),
and commits the latest revision of all files from the master branch to latest_branch.

Then it deletes the master branch, makes latest-branch the master branch.
Finally, git rollup forces a push to origin.

## 2. Git Clone-All

Git clone-all creates a local copy of all public Github repositories of a given user.

### Quick Start
Download git-clone-all and make it executable by running:
~~~bash
	$  chmod u+x git-clone-all
~~~

To clone all public repositories of a given user:

1. Find the Github USERID of the user. The USERID appears immediately after github.com/. For my account, the USERID is macp3o.

2. Run:
~~~bash
	$  git clone-all USERID [DIRECTORY]
~~~
Or, move to the target directory and omit DIRECTORY in the command above.

### Dependencies
Requires bash, curl, sed, and obviously git.

## 3. Links to Additional Git Tools
Additional wonderful git tools are available from:
* [TJ's Git Extras](https://github.com/tj/git-extras), and
* [Steve Mao's Awesome Git Addons](https://github.com/stevemao/awesome-git-addons) curated list of git addons.

## MIT License
Git Powertools is open-source software released under the MIT license. See the LICENSE file for details. 


