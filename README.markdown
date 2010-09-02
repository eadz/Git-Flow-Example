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

So far, we have been working on the development version. 
Even though this post isn't production ready, I'm going to make a release branch using git flow. 

  git flow release start v0.1



