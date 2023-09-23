Useful Git snippets
#### Switch to new branch while preserving untracked files 
```bash
git switch -c <new branch>
# or git switch <existing branch>
```
or alternatively:
```bash
git add -A
git stash
git checkout <other branch>
git stash pop
```

#### WIP commit workflow
```bash
git switch -c dev
## Or git checkout -b dev

## Make your commits to the branch:
git add .
git commit -m "WIP: some work done on a new feature"
git push origin head

# Rebase to squash WIP commits into fewer atomic commits
git rebase -i <branching commit>

git switch master
# Pull before merging to update the master branch
git pull origin master
# no-ff flag keeps the branch commits marked seperately in history
git merge --no-ff dev
# git merge --rebase dev alternatively to rebase on top of updated master to avoid conflicts

git push origin master

#delete branch local and remote
git push -d origin dev
git branch -d dev
```
