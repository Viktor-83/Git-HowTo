# HowTo use GitHub - for Learning purpose

[Git-CheatSheet.pdf](./github-git-cheat-sheet.pdf)

## BEGIN

### General info

```bash
git status
git reflog      // see any action made by user!
git log         // see commits on branch
git branch      // see branches
git remote -v   // see remote url
```

### Create new repo

```bash
echo "# Git-test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:Peanuts-83/Git-test.git
git push -u origin main  // -u = --set-upstream
```

### Push an existing repo

```bash
git remote add origin git@github.com:Peanuts-83/Git-test.git
git branch -M main
git push -u origin main
```

### Import a repo (if submodules inside, only submodules ref, no submodule files imported)

```bash
git clone git@github.com:Peanuts-83/Git-test.git
```

## SUBMODULES

ref : https://git-scm.com/book/fr/v2/Utilitaires-Git-Sous-modules

### Add a repo (submodule) to another repo

```bash
git submodule add git@github.com:Peanuts-83/Git-test.git
git submodule add git@github.com:Peanuts-83/Git-test.git folderName     // optional
```

### Import a repo with submodules content files

```bash
git clone --recurse-submodules git@github.com:Peanuts-83/Git-test.git
```

### Import submodules content files AFTER basic git clone repo (forgot --recursive-submodules option)

```bash
git submodule update --init --recursive
```


### Remove a submodule

[Check HowTo here](https://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule/36593218#36593218)

### Commit all & push

```bash
git add .
git commit -m'Name of the commit'
git push
```

## FILES & DIR

### COPY file or dir from another branch

```bash
git checkout branchName fileOrDirName
```

### REMOVE file or dir only on remote

```bash
git rm --cached fileName
git commit -m'fileName removed'
git push
```

## BRANCHES

[https://learngitbranching.js.org](https://learngitbranching.js.org)
### CREATE branch & go on it

```bash
git branch branchName
git checkout branchName
// or short command
git checkout -b branchName
```

### COPY branch or commit under HEAD

Originals remain the same

```bash
git cherry-pick branch1 branch2 de9a6fb // branch or commit names
```

### MERGE branch

Merged branch ends to merge point. Original branches remain the same.

**CAUTION** : Deleted common files on any branch are deleted!

```bash
git checkout main
git merge branch2       //
```

### REBASE branch

Places HEAD branch ahead rebased branch. Original branches are changed, history rewritten...

**CAUTION** : Do not use on public branch used by others!

```bash
git checkout branch1
git rebase main         // branch1 comes ahead main
```

### UNDO changes if remote is still ok

```bash
git reset --hard origin/main        // rewrites history
git revert commit-hash       // creates a new commit to undo changes
```

git reset --soft A, will change the commit history and repository; staging and working directory will still be at state of C.

git reset --mixed A, will change the commit history, repository, and staging; working directory will still be at state of C.

git reset --hard A, will change the commit history, repository, staging and working directory; you will go back to the state of A completely.