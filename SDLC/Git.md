<details>
<summary>Basics of Git</summary>
# Basics

**What is origin and when would you use it?**
- `origin` is a reference to the remote repo + branch you push/pull to/from (ie. sync with). If you cloned the repo, initially/by default, origin would refence the remote repo you cloned the repo from. Can easily change w --set-upstream origin {other_branch}

** What is the difference between `git fetch` and `git pull`?
- `fetch` will download changes and update the .git folder but not apply any changes to your local working copy. `pull` is both a `fetch` followed by a `git merge` so it applies changes to your local repo

**Two branches, develop and master. Two developers both work on the same file. Developer A creates a new branch then changes first line of code. Developer B creates a new branch and changes last line of code. Developer A wants to push changes to develop - will there be a conflict?**
- No, because Develop B has not pushed 

**Devs A and B work on different teams in different codebases, however they do have a shared “common code” set of libraries that both teams maintain. What is the best strategy for these teams to follow to reduce conflicts?**
- Good communication, fetch and push early and often, write tests

**I want to contribute to an open source repository. How?
- Generally speaking, (1) look for the repos instructions on how they like contributions, or (2) fork, change, create PR
</details>

<details><summary>Intermediate </summary>
**I accidentally made substantial changes to master. I don’t want to discard those changes and I don’t want to merge them yet into master. What next?**
- Typically you would stash your changes, checkout a new feature Branch, then apply the changes to your feature branch

**I have two branches, develop and master. I create a local feature branch, do my development, and PR /merge to develop. How do I get the change into master?**
- Cherry-pick 

**When should a team consider squashing commits?**
- When there is no value to a “chatty” commit history

**When would `rebase` be appropriate?**
- rebase and merge do the same thing (integrate changes from one branch to another) but just in different ways
- How it works: `git rebase feature master` 
   - Moves feature commits to start at top of master (after last merge commit) so that it looks like Feature changes occurred after merge master
   - Rewrites the history of the repo 
- Only appropriate for private feature branches
- Golden rule of rebasing is never rebase a public (shared w others) branch
- Good uses:
   - Make PRs easier: Cleanup your local Feature branch commit history w an interactive rebase in which you squash commits into one
   - Move changes from one branch to another - Accidentally made changes to master, rebase to feature branch and it makes history look like feature branches changes occurred after last master merge commit
   - If you would prefer a clean, linear history free of unnecessary merge commits, you should reach for git rebase instead of git merge when integrating changes from another branch.
- Bad uses 
   - if you want to preserve the complete history of your project and avoid the risk of re-writing public commits, use git merge instead 
- https://link.medium.com/o6wGBDXZU6
- https://www.atlassian.com/git/tutorials/merging-vs-rebasing
- https://perl.plover.com/classes/git-rebase-wtf/

</details> 