# Git Powertools

A set of powertools for git.

1. [Git setup](#1-git-setup) -- initialize a repository with remote.
2. [Git collapse](#2-git-collapse) -- collapses all the history from the master branch.
3. [Git clone-all](#3-git-clone-all) -- clones all repositories of a given user.
4. [Links to additional awesome git tools](#4-links-to-additional-git-tools).


## 1. Git Setup

Git setup initializes a local git repository and pushes it to a remote git.

### Quick Start
Download git-setup and make it executable by running:
~~~bash
	$  chmod u+x git-setup
~~~

To setup a repository, run from within the repository to setup:
~~~bash
	$  Run git setup REMOTE_REPOSITORY
~~~

Example of REMOTE_REPOSITORY: `git@github.com:user/repository-name.git`

Git setup configures and commits the repository with message `initial commit`.
Subsequent commits to the remote repository can be pushed with `git push`.


## 2. Git Collapse

Git collapse discards all the history from the `master` branch.

### Quick Start
Download git-collapse and make it executable by running:
~~~bash
	$  chmod u+x git-collapse
~~~

To rollup a repository, run from within the repository to rollup:
~~~bash
	$  Run git collapse COMMIT_MESSAGE
~~~

Git collapse commits the repository files to recreate the `master` branch with only the latest versions, as if it was a brand new repository. Git collapse does not delete or affect other branches (besides `latest_branch` which is used to recreate the `master` branch).

#### Important:
* **No Undo**: Git collapse cannot be undone!

* **Broken Forks**: All forks of the repository will stop working after git collapse!

### How It Works?
Git collapse creates a new temporary branch (latest_branch),
and commits the latest revision of all files from the master branch to latest_branch.

Then it deletes the master branch, makes latest-branch the master branch.
Finally, git collapse forces a push to origin.

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

## 4. Links to Additional Git Tools
Additional wonderful git tools are available from:
* [TJ's Git Extras](https://github.com/tj/git-extras), and
* [Steve Mao's Awesome Git Addons](https://github.com/stevemao/awesome-git-addons) curated list of git addons.

## MIT License
Git Powertools is open-source software released under the MIT license. See the LICENSE file for details. 


