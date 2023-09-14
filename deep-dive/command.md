```bash

# Анхны clean working directory лүү очно.
git stash

# Өөрчлөлтүүдийг нь харуулна.
git stash apply

#
git stash push -m "third feature added"

git stash pop 0

# Тухайн stash-ыг index-ээр нь устгана.
git stash drop 0

# Бүх stash-уудыг устгана.
git stash clear

git stash list
```

#### RESTORE the current commit

```bash

# Shows all reference logs
git reflog


git reset --hard HEAD~1

# reflog-ын жагсаалтаас тухайн log-ны id (3ab90d3)-aaр нь cүүлийн commit-ыг авчирж болно.
git reset --hard 3ab90d3

```

#### RESTORE the current commit with new branch

```bash

git switch -c feature # create a branch
git add .
git commit -m "feature branch added"
git branch -D feature # delete branch

git reflog # list commits

# reflog-ын жагсаалтаас тухайн log-ны id (3ab90d3)-aaр нь cүүлийн commit-ыг авчирж болно.
git checkout 3ab90d3 #bring back or restore the commit with DETACHED HEAD

# DETACHED HEAD-ыг branch-тэй болгох
git switch -c feature
```

#### MERGE

```bash

# Feature branch-ын [commit-уудтай] нь хамт main рүү merge хийнэ.
git merge feature

# Feature branch-ын [commit-уудгүйгээр] нь main рүү merge хийнэ.
git merge --squash feature

# Non fast-forward merging
git merge --no-ff feature

```

#### REBASE

- Rewrites code history

```bash
# Main-ыг feature branch рүү авчирж ирнэ.
git rebase main
```

#### FIX CONFLICTS

- Ижил файланд ижил мөрөнд 2 branch-ыг merge хийх үед CONFLICT үүснэ.

```bash

git merge feature

# Accept current change or incoming change

# Abort merging
git merge --abort

```

#### CHERRY PICKING

```bash

```
