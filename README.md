
# Git Basics #


####  Git Ignore  ####
## ##

This snippet will help you to take action of git ignore file.
If you pushed project and than creates .gitignore file and want to ignore folders/files in your git repo follow this steps.

This will clean all cached and delete files that are in .gitignore list
```bash
$ git rm -r --cached .
```

This will push code to git
```bash
$ git add .
```

```bash
$ git commit -m "Removing all files in .gitignore"
```
```bash
$ git push origin master
```


####  Untracked Files  ####
## ##

This snippet will help you to take action of deleted files.
If you pushed project and than delete some files and want to delete folders/files in your git repo follow this steps.


This will list all deleted files
```bash
$ git ls-files --deleted -z | xargs -0 git rm
```

---
This for perticluar files _node_modules_, _bower_components_ and _public/bower_components_.

Note: Seprated by _space_
```bash
$ git rm -r --cached node_modules bower_components/ public/bower_components/
```
>> <b>or</b>

This for all files.

```bash
$ git rm -r --cached .
```
---

This will push code to git
```bash
$ git add .
```
```bash
$ git commit -m “deleted untracked files”
```
```bash
$ git push origin master
```

  
####  Remove Commit  ####
## ##
This snippet will help you to take current commit head to perticular commit.

Careful: <code>git reset --hard</code> WILL DELETE YOUR WORKING DIRECTORY CHANGES. Be sure to stash any local changes you want to keep before running this command.
Assuming you are sitting on that commit, then this command will wack it...

if you want to look at the output of  Git log open in new tab of terminal
```bash
$ git log
```

The HEAD~1 means the commit before head.
```bash
$ git reset --hard HEAD~1
```

find the commit id of the commit you want to back up to from <code>git log</code>, copy _sha1-commit-id_ and then do this

```bash
$ git reset --hard <copied-sha1-commit-id>
```

If you already pushed it, you will need to do a force push to get rid of it...

```bash
$ git push origin HEAD --force
```



####  Remove All Commits  ####
## ##
This snippet will help you to remove all old commits from repo and make one single commit

This will create one branch named: <code>latest_branch</code>
```bash
$ git checkout --orphan latest_branch
```

Add all the files
```bash
$ git add -A
```

Commit the changes
```bash
$ git commit -am "commit message"
```

Delete the branch <code>master</code>
```bash
$ git branch -D master
```

Rename the current branch to master
```bash
$ git branch -m master
```

Finally, force update your repository
```bash
$ git push -f origin master
```




## Thank You ##

This is simple tutorial by [Bhavan Patel](https://github.com/bhavanpatel) so let me know if I've mistaked somewhere. :)

* [facebook](https://www.facebook.com/bhavan.patel.98) for socials!!
* [email](mailto:bhavan7@yahoo.com?Subject=Issue_On_Git_Tutorials) Mail me   !!
 
