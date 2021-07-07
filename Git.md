Head is a reference to the current branch.

Shows all branches
```
git branch
```

Creates branch, doesnt switch yet
```
git branch <branch-name>
```

Swith branches
```
git switch <branch-name>
```
git checkout is the older command.
<br>
Delete branches
```
git branch -d <branch-name>
```
Rename branches
```
git branch -m <branch-name>
```

## Merge
1. First switch into master
2. git merge <branch>
This way we merge the <branch> into master

- Merging Strategies: Fast-forward, merge commit(non fast-forward, no conflicts), merge conflict
- Fast forward is just like anything doesnt change in master and we add new commits to the master
- Merge commit is like something changed, or added in master, but that doesn't added in feature branch
so, it also does is merge automatically without conflict
- Merge conflict is something changed in master and our branch so we need to solve it.

## Diff
Lists all changes in the working tree since your last commit
```
git diff HEAD
```

Lists all changes between the staging are and our last commit
```
git diff --staged or --cached
```

View spesific changes in a file
```
git diff --staged <file>
or
git diff HEAD <file>
```

Compare branches
```
git diff branch1..branch2
```

Compare commits
```
git diff commit1..commit2
```

## Git Stash
When you work on branch and then switch another branch, what happens the work you previously made in your previous branch?
1. They all come with the new branch
2. Git doesn't let you before you add your changes to the stash

Stashing: git provides a way of stashing these uncommitted changes so that we
can return to them later, without having to make unnecessary commits.

<p>

Remove the most recently stashed changes in your stash and re-apply them to your 
current working are
```
git stash pop
```

## Undo & Time Travel
We can go back old commit. This puts the branch into detached head state
```
git checkout <commit-hash>
```

You apply some changes to a file but don't want to keep them
```
git checkout HEAD <file>
```
Another way to do it using git restore. Its because git checkout is overloaded and do lots of stuff
it s replaced with new commands. 
```
git restore <file>
```
is equvailent.

## Git Reset
You want to get back to specified commit hash. Use
```
git reset <commit-hash>
```

## Git Revert
Same as reset but in reset we move pointer back, in reset we make commit that undo changes.
<br>
Which one to use?

> If u want to reverse some commits, that other people already have on their machihnes, use revert
> Otherwise use reset