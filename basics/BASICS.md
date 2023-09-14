```bash
# Display all commits of current branch
git log

git init

# Check working directory & staging area status
git status

# Create a new branch
git branch second-branch
git checkout second-branch

# Create a new branch, then switch to it
git checkout -b third-branch

# Merge other branch with main branch
git checkout main
git merge third-branch

# Go to specific branch
git switch second-branch

# Create a new branch
git switch -c fourth-branch
```

```bash
# List data in staging area. Тухайн branch-ын staging area доторх file-уудыг харуулна.
git ls-files

# Remove deleted file
git rm working-with-branches.txt
```

#### RESTORE or UNDO **_UNSTAGED_** changes

```bash
# Initial-commit.txt файл дээр өөрчлөлт хийсний дараа, commit хийгээгүй үедээ (unstaged changes) REVERT буюу буцаагаад хуучин хэвэнд нь аваачиж болдог.
git checkout initial-commit.txt

# Ignore all unstaged commits
git checkout .

# Restore specific file that has not been committed
git restore initial-commit.txt


# Шинээр үүсгэсэн файлыг (untracked file)-ыг бүр мөсөн устгах
git clean -df
```

#### RESTORE or REVERT **_STAGED_** changes

`1.` Эхний арга

```bash
git add .

# Хэрвээ git add . хийсэн бол хуучин хэвэнд нь оруулахын тулд "git reset"...
git reset intitial-commit.txt
git checkout initial-commit.txt

```

`2.` Хоёр дох арга

```bash
git add .

# Хэрвээ git add . хийсэн бол хуучин хэвэнд нь оруулахын тулд "git restore --staged"...
git restore --staged intitial-commit.txt
git checkout initial-commit.txt
```

#### DELETE the **_STAGED_** changes (latest commit)

```bash
touch unrequired.txt
git add unrequired.txt
git commit -m "unrequired file added"

# Шинээр үүсгэсэн 'unrequired.txt' файлын commit-ыг ~1-ээр ухраана.
git reset --soft HEAD~1
```

#### DELETE the **_STAGED_** changes (latest commit)

```bash
touch unrequired.txt
git add unrequired.txt
git commit -m "unrequired file added"

# Шинээр үүсгэсэн 'unrequired.txt' файлыг устгана. Бусад файлуудын commit-уудыг reset (~1-ээр) хийнэ.
git reset --hard HEAD~1
```

#### DELETE BRANCH

```bash
git branch -D second-branch # one branch
git branch -D second-branch third-branch # more than one branch
```
