ownCloud is open source and you can contribute.
You can find the source repositories on github here: https://github.com/owncloud

How to work with git and github
-------------------------------

Here we use the documentation repository https://github.com/owncloud/documentation

You can make a local copy to work 

* git clone git@github.com:owncloud/documentation.git

There are lots of branches and different versions. Have look

* git branch -a

We want to change somthing in the stable5 branch, switch to this branch with 

* git checkout stable5

Attention now, don't change files in the stable5 branch. We need a new branch. Later we can make a pull request and merge our branch with the stable5 branch, to bring all together again.

* git branch my_new_feature_stable5

This new branch is based on the branch we are right now - stable5. Now switch into our new branch

* git checkout my_new_feature_stable5

Now it is time for hard work and all your changes. See your changes

* git status

Finished? Please dont't forget to test. And then lets commit the changes

* git add .
* git commit -m "Short explanation on the changes" 

Add "adds" your changes to a commit, which collects all changes like a package.
The commit is only on your local system, but this is teamwork. Let's publish

* git push origin my_new_feature_stable5

Now everyone can see and work with the commited changes. Fine, now keep on working!
After all the day's work, one last step - the pull request.
Go to the github https://github.com/owncloud/documentation and click on pull requests. 
Here click on the button "New pull request" and select the base branch "stable5" and compare to the "my_new_feature_stable5" branch.
You can see the changes of your work and every single commit. 

