# Github-how-to
Personal memo for github operations

## Create a new Git branch from origin
1. Pull changes from upstream to have an up-to-date master:
 ```
 $ git pull
 ```

2. Create a local branch:
```
$ git checkout -b <my-new-branch-name>
```


3. Push new branch to origin:
```
git push origin <my-new-branch-name>
```

4. Add remote for the new branch:
```
$ git remote add <name_of_remote> <my-new-branch-name>
```
or
```
git branch --set-upstream-to=<remote>/<branch> <my-new-branch-name>
```


## Merge fix branch to main via a temporary branch
1. Change to master branch and pull any update:
```
$ git checkout main
$ git pull
```

2. Create a new temporary branch from main, `tmpMerge`. No need to connect to remote/upstream, only local branch:
```
$ git checkout -b tmpMerge
```

3. Merge fix-branch with `tmpMerge`-branch:
```
$ git merge <fix-branch name>
```

 Fix any conflict.


4. Merge the main branch with updated `tmpMerge`-branch and push
```
$ git checkout main
$ git merge ´tmpMerge´ -m "<message>"
$ git push
```

## Delete branch
https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-locally-and-remotely

### Local branch
```
$ git branch -d <branch_name>
```

### Branch on github
```
$ git push main --delete <branch_name>
```
