#### BRANCH

```bash

# Displays remote branches
    #  origin/HEAD -> origin/main
    #  origin/main
git branch -r

# Displays all branches
git branch -a
    #   feature
    # * main
    #   remotes/origin/HEAD -> origin/main
    #   remotes/origin/main

# Push a new branch to remote
git push origin feature

# Displays newly added remote branches list
git ls-remote
    # From https://github.com/Ganzorig2022/git-lesson.git
    # 12225c47256bfc110b9086ba7a6d64c7abd5ad7a        HEAD
    # c51a25f837c3a60fbc6dfca736185dea132eea9f        refs/heads/feature
    # c4df6dc67886489debb3557c1223c74eb86f7cb1        refs/heads/feature-remote
    # 12225c47256bfc110b9086ba7a6d64c7abd5ad7a        refs/heads/main

# Fetch new branch from remote repository into local repository
git fetch origin

```
