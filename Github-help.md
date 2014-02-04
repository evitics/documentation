===Updating a Forked Repo on Windows===
  1) Go to your folder containing the forked repo and run
  2) ```git fetch upstream```
  3) ```git merge upstream/master```
  If an error message occurs that 'upstream' doesn't exist then run: 
  ```git remote add upstream https://github.com/evitics/documentation.git```
  
===Updating a local Repo===
  1) git commit -m "short description of what changed" -m "Long detailed description of what changed"
  2) git push -u origin master

Once you want to push the commit upstream, go to github and navigate to your repo (not the evitics). 
Then Submit a pull request
