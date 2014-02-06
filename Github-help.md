###Updating a Forked Repo on Windows###
  
  1) Go to your folder containing the forked repo and run
  
  2) ```git fetch upstream```
  
  3) ```git merge upstream/master```
  
  If an error message occurs that 'upstream' doesn't exist then run: 
  ```git remote add upstream https://github.com/evitics/documentation.git```
  
###Updating a local Repo###
 
  1) git commit -m "short description of what changed" -m "Long detailed description of what changed"
 
  2) git push -u origin master

Once you want to push the commit upstream, go to github and navigate to your repo (not the evitics). 
Then Submit a pull request


### Create a shortcut to fetch upstream, origin, and merge ###

  1) navigate to the git repo
  
  2) open in the editor of your choice ```.git/config```
  
  3) add the following lines at the bottom of the file:
  
  ```
  [alias]
  pu = !"git fetch origin -v; git fetch upstream -v; git merge upstream/master"
  ```
  
  For example here is my config afterwords:
  
  ```
  [core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        ignorecase = true
        precomposeunicode = false
[remote "origin"]
        url = https://github.com/cobookman/frontend.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
        remote = origin
        merge = refs/heads/master
[remote "upstream"]
        url = https://github.com/evitics/frontend.git
        fetch = +refs/heads/*:refs/remotes/upstream/*
[alias]
  pu = !"git fetch origin -v; git fetch upstream -v; git merge upstream/master"
  ```
  
