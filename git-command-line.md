### Git Command Line

I am so used to using Github Desktop, but it's a little 'weird' if you don't know how to use git command line. So play with it right now!

 1. I already have a project in my local, and I want to add it to Github.
 
 ```
 cd <project directory>
 git init
 ```
 This creates a subdirectory named **.git** that contains all of the repository files.
 2. Add the files to my new local repository.
 ```
 git add .
 ```
 3. Commit the files in my local repository.
 ```
 git commit -m 'initial version'
 ```
 4. Add the URL for the remote repository.
 ```
 git remote add origin https://github.com/Yifan127/LearnPythonTheHardWay.git
 ```
 5. Verify the remote URL
 ```
 git remote -v
 ```
 6. Push the changes in my local repository to Github.
 ```
 git push origin master
 ```
 7. I want to rename the remote name <origin> to a more meanningful one <LPTHW>.
 ```
 git remote rename origin LPTHW
 ```
 8. I forked a repository in Github, and I find there are some updates in the upstream repository, then I want to sync my forked repository with the upstream repository.
 ```
 git remote add Py103 https://github.com/Yifan127/Py103.git
 git remote add AIMinder https://github.com/AIMinder/Py103.git
 git remote -v
 ```
 ![](/assets/ch0/git remote -v.PNG)
 9. Fetch the update from upstream repository to local master branch.
 ```
 git fetch AIMinder
 ```
 10. Swith to master branch.
 ```
 git checkout master
 ```
 11. Merge the changes from upstream with local master branch.
 ```
 git merge AIMinder/master
 ```
 12. All the operations above are in my local repository, so at last I need to push the update to my remote Github repository.
 ```
 git push Py103 master
 ```
 
 




