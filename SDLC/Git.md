<details>
<summary>Basics of Git</summary>
# Basics

**What is origin and when would you use it?**
- `origin` is a reference to the remote repo + branch you push/pull to/from (ie. sync with). If you cloned the repo, initially/by default, origin would refence the remote repo you cloned the repo from. Can easily change w --set-upstream origin {other_branch}

** What is the difference between `git fetch` and `git pull`?
- `fetch` will download changes and update the .git folder but not apply any changes to your local working copy. `pull` is both a `fetch` followed by a `git merge` so it applies changes to your local repo

</details>