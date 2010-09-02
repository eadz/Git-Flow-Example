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
