# Test Repo - for training purpose only

## BEGIN

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

### Import code from another repo

```bash
git clone git@github.com:Peanuts-83/Git-test.git
// or add repo in another repo
git submodule add git@github.com:Peanuts-83/Git-test.git
```

### Commit all & push

```bash
git status
git add .
git commit -m'Name of the commit'
git push
```

## BRANCHES

### Create branch & go on it

```bash
git branch branchName
git checkout branchName
// or short command
git checkout -b branchName
```
