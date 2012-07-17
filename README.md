### Basic Node.js Post-Receive Hook ##

This is a template script for use in a git post-recieve hook. It will checkout the code 
into a commit specific build folder, then run npm install and eventually npm test. This 
script is inspired by the heroku deployment process. 

## Setup & Usage ##

* Setup a bare git on the remote (deployment server), `git init --bare`
* Create a file called `hooks/post-receive` in the new remote repo. 
* Remember to the the file executable, `sudo chmod +x hooks/post-receive`
* Add a remote to your local git folder `git remote add myServer git@myserver.com:myrepo.git
* Once its all set, use the new remote, `git push myServer branchName`

## To Do ##
This script is evolving. 

* Add settings to define the branch for testing, deployment etc.
* Add a check for the npm test to make certain all test pass before moving on.
* Add the deployment and restart code. (Currently missing)
* Add a commit/build specific URL.

## References ## 
The following links provides the code needed to string this together. 

* http://sterlinghamilton.com/2010/12/23/unix-shell-adding-color-to-your-bash-script/
* http://npmjs.org/doc/
* https://devcenter.heroku.com/articles/nodejs
* http://stackoverflow.com/questions/3170337/how-can-i-get-rid-of-the-remote-messages-that-appear-on-every-line-returned
* http://blog.ekynoxe.com/2011/10/22/git-post-receive-for-multiple-remote-branches-and-work-trees/

