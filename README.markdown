# Git Flow by example using GitHub #

## Initial Setup ##

We start with this

![network-1](http://github.com/eadz/Git-Flow-Example/raw/develop/images/network-1.png "Initial Commit Network Image")

	➜  Git-Flow-Example git:(master) git flow init

	Which branch should be used for bringing forth production releases?
	   - master
	Branch name for production releases: [master] 
	Branch name for "next release" development: [develop] 

	How to name your supporting branch prefixes?
	Feature branches? [feature/] 
	Release branches? [release/] 
	Hotfix branches? [hotfix/] 
	Support branches? [support/] 
	Version tag prefix? []
	
Then after pushing the develop branch to github, we get this:

![network-2](http://github.com/eadz/Git-Flow-Example/raw/develop/images/network-2.png "After git flow init")

## Releasing The Development Version ##

### Release branches ###
**May branch off from:** develop
**Must merge back into:** develop and master
**Branch naming convention:** release-*

So far, we have been working on the development version. 
Even though this post isn't production ready, I'm going to make a release branch using git flow. 

	➜  Git-Flow-Example git:(develop) git flow release start v0.1                      
	Switched to a new branch 'release/v0.1'

	Summary of actions:
	- A new branch 'release/v0.1' was created, based on 'develop'
	- You are now on branch 'release/v0.1'

	Follow-up actions:
	- Bump the version number now!
	- Start committing last-minute fixes in preparing your release
	- When done, run:

	     git flow release finish 'v0.1'

When creating a release branch, it uses the current state of 'develop' branch as its base. You can make any further small commits to make it production ready, then you can run `git flow release finish 'v0.1'` to finish the release. 

When the release is finished, the release branch will be merged to master. 


## Git flow feature example ##

### Release branches ###
**May branch off from:** develop
**Must merge back into:** develop and master
**Branch naming convention:** release-*

### Feature branches ###
**May branch off from:** develop
**Must merge back into:** develop
**Branch naming convention:** feature/feature_name

Feature branches are where you'll do most of your work. This chapter is a feature branch. You make your changes, and commit to the branch, and when the branch is ready, it will be merged back into develop. 

	➜  Git-Flow-Example git:(feature/feature_example) ✗ git flow feature help
	Branches 'develop' and 'origin/develop' have diverged.
	And local branch 'develop' is ahead of 'origin/develop'.
	Switched to a new branch 'feature/feature_example'

	Summary of actions:
	- A new branch 'feature/feature_example' was created, based on 'develop'
	- You are now on branch 'feature/feature_example'

	Now, start committing on your feature. When done, use:

	     git flow feature finish feature_example

There are quite a few options for git flow feature. You can find them buy running `git flow feature help`:

		git flow feature help
		usage: git flow feature [list] [-v]
		       git flow feature start [-F] <name> [<base>]
		       git flow feature finish [-rF] <name|nameprefix>
		       git flow feature publish <name>
		       git flow feature track <name>
		       git flow feature diff [<name|nameprefix>]
		       git flow feature rebase [-i] [<name|nameprefix>]
		       git flow feature checkout [<name|nameprefix>]
		       git flow feature pull <remote> [<name>]

If we push a feature branch to GitHub without releasing it(`git push origin feature/feature_example`), the network graph looks like this:

![network-newfeature](http://github.com/eadz/Git-Flow-Example/raw/develop/images/network-newfeature.png "After pushing feature branch")

Once we release the feature by running `git flow feature finish feature_example`, the changes on the feature branch are merged back into the **develop** branch, but not the master branch.




Once that happens, the network looks like this:


You can see the green dots are the individual commits on this branch. 

