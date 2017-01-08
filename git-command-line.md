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
 git remote add origin https://github.com/Yifan127/Py103.git
 ```
 5. Verify the remote URL
 ```
 git remote -v
 ```
 6. Push the changes in my local repository to Github.
 ```
 git push origin master
 ```
 7. I want to rename the remote name <origin> to a more meanningful one <Py103>.
```
git remote rename origin Py103
```


