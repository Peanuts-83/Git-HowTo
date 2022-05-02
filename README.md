# Test Repo - for training purpose only

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

### Import code from another repo

```bash
git clone git@github.com:Peanuts-83/Git-test.git
// or add repo in another repo
git submodule add git@github.com:Peanuts-83/Git-test.git
```

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

## BRANCHES

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

Merged branch ends to merge point. It comes to HEAD and overwrites it. Original branches remain the same.

**CAUTION** : Non existing files on merged branch are deleted on HEAD branch!

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