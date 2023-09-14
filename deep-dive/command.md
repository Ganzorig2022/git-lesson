#### STASHING - temporary storage for unstaged and uncommitted changes

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

#### RESTORE the specific commit

```bash

# Shows all reference logs including deleted commits
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

#### REBASE - change the base of commits in another branch

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

#### CHERRY PICKING - merge only specific commit

```bash
git switch -c feature2

# file2.txt дээр өөрчлөлт оруулав.
git add .
git commit -m "type fixed on file2.txt"

# git log-оор тухайн commit-ын ID-г (f9f1de4f6a38e9038e33060f9ffa1e98d0b66177) олж авна.
git log

# Main рүүгээ буцаж очоод, зөвхөн тухайн ганцхан commit-ыг merge хийнэ.
git switch main

git cherry pick f9f1de4f6a38e9038e33060f9ffa1e98d0b66177
```
