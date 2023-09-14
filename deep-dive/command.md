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

git switch -c feature
git add .
git commit -m "feature branch added"
git branch -D feature

git reflog

# reflog-ын жагсаалтаас тухайн log-ны id (3ab90d3)-aaр нь cүүлийн commit-ыг авчирж болно.
git checkout 3ab90d3
git switch -c feature
```
