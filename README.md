Multiple-Heroku-Environments
============================

Shell script that sets up easy deployment to multiple environments on Heroku  

##Installation:

1) Navigate to your project base directory
<pre> git clone git@github.com:CEWendel/Multiple-Heroku-Environments.git</pre>
2) Set execute permissions 
<pre> chmod +x Multiple-Heroku-Environments/mult_environ </pre>
3) Run script
<pre> Multiple-Heroku-Environments/mult_environ </pre>

##Usage:

Let's set up the staging app, make some changes, and merge them over to the prod app
###Staging app

1) Switch to staging branch and make a change
<pre> git checkout staging </pre>
2) Commit the change you made on the staging branch
<pre> git commit -am "Stage file change" </pre>
3) Push the change to the staging branch of your remote repo (ie. Github)
<pre> git push origin staging </pre>
4) Push the change to the master branch of the staging heorku app(heroku-staging)
<pre> git push heroku-staging staging:master </pre>
5) Open the staging heroku app and make sure you change is displayed
###Merging to the master
* So let's say you are satisfied how the change looks on your staging app, and you want to merge it to your prod app
1) Checkout the master branch
<pre> git checkout master </pre>
2) Merge the changes from the staging branch
<pre> git merge staging </pre>
3) Push the changes to the master branch of your remote repo (ie. Github)
<pre> git push origin master </pre>
4) Push the changes to your prod app 
<pre> git push heroku-prod master </pre>
