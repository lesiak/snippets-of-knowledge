# Daily usage
* [Undoing a git rebase](http://stackoverflow.com/questions/134882/undoing-a-git-rebase)
```
git reflog
git reset --hard HEAD@{XXXX}
```

# Search

### git log -S
- Searches the commit history for changes that added or removed a specific string.
- It is used to find commits where the string was introduced or removed.
- Focuses on historical changes rather than the current state of the repository.
- Example: `git log -S"myString"`

* In a git repo, I know that myString occured in some version of application.conf file. How can I look for versions that added or removed this string?

You can use the git log command with the -S option to find commits that added or removed a specific string in a file. Here's how you can do it:
```
git log -S"myString" -- application.conf
```
**Explanation:**
```
-S"myString": Searches for commits where the string myString was added or removed.
-- application.conf: Limits the search to the application.conf file.
```
This will show a list of commits where the string myString was introduced or removed. You can inspect each commit using git show <commit-hash> to see the exact changes.

### git grep
- Searches for a string or pattern in the content of files in the current working directory or a specific branch.
- It is used to find occurrences of a string in the current state of the repository (or a specific branch).
- Does not provide historical information about when the string was added or removed.
- Example: `git grep "myString"`

# Cleanup tracking branches
* [Remove tracking branches no longer on remote](https://stackoverflow.com/questions/7726949/remove-tracking-branches-no-longer-on-remote)
```
git remote prune origin
```
* [What are the differences between git remote prune, git prune, git fetch --prune, etc](https://stackoverflow.com/questions/20106712/what-are-the-differences-between-git-remote-prune-git-prune-git-fetch-prune)
> There are potentially three versions of every remote branch:
> 
> 1. The actual branch on the remote repository
> (e.g., remote repo at https://example.com/repo.git, `refs/heads/master`)
> 2. Your snapshot of that branch locally (stored under `refs/remotes/...`)
> (e.g., local repo, refs/remotes/origin/master)
> 3. And a local branch that might be tracking the remote branch
> (e.g., local repo, `refs/heads/master`)
>
> Let's start with `git prune`. This removes *objects* that are no longer being referenced, it does not remove references. In your case, you have a local branch. That means there's a ref named `random_branch_I_want_deleted` that refers to some objects that represent the history of that branch. So, by definition, `git prune` will not remove `random_branch_I_want_deleted`. Really, `git prune` is a way to delete data that has accumulated in Git but is not being referenced by anything. In general, it doesn't affect your view of any branches.
> 
> `git remote prune origin` and `git fetch --prune` both operate on references under `refs/remotes/...` (I'll refer to these as remote references). It doesn't affect local branches. The git remote version is useful if you only want to remove remote references under a particular remote. Otherwise, the two do exactly the same thing. So, in short, `git remote prune` and `git fetch --prune` operate on number 2 above. For example, if you deleted a branch using the git web GUI and don't want it to show up in your local branch list anymore (`git branch -r`), then this is the command you should use.
> 
> To remove a local branch, you should use git `branch -d` (or `-D` if it's not merged anywhere). FWIW, there is no git command to automatically remove the local tracking branches if a remote branch disappears.
 
* [How to move certain commits to another branch in git?](https://stackoverflow.com/questions/2369426/how-to-move-certain-commits-to-another-branch-in-git) 

# Setup
* [Git file permissions on Windows](http://stackoverflow.com/questions/6476513/git-file-permissions-on-windows)
* [Git/Bash is extremely slow in Windows 7 x64](https://stackoverflow.com/questions/4485059/git-bash-is-extremely-slow-in-windows-7-x64)
* [What's the best CRLF (carriage return, line feed) handling strategy with Git?](http://stackoverflow.com/questions/170961/whats-the-best-crlf-carriage-return-line-feed-handling-strategy-with-git)
* [Dealing with line endings](https://help.github.com/articles/dealing-with-line-endings/)
* [Git: How configure KDiff3 as merge tool and diff tool](http://stackoverflow.com/questions/33308482/git-how-configure-kdiff3-as-merge-tool-and-diff-tool)
* [Pimp My Git – Manage Different Git Identities](https://dzone.com/articles/pimp-my-git-manage-different-git-identities)

# SourceTree
* [SourceTree 2.0 is horribly slow and not scaling well on Windows 10](https://community.atlassian.com/t5/Sourcetree-discussions/SourceTree-2-0-is-horribly-slow-and-not-scaling-well-on-Windows/td-p/582066)
   - Update to latest version
   - Use embedded Git - Latest version (Tools > Options > Use Embedded Git) 
   - Disable LibGit2 integration (Tools > Options > Disable LibGit2 integration)
   - Set the Log rows to fetch per load to "0" (Tools > Options > General > Repo Settings)

# Repo rewrite
* [List all authors of a particular git project](http://www.commandlinefu.com/commands/view/4519/list-all-authors-of-a-particular-git-project)
git log --all --format='%aN <%cE>' | sort -u
* [Change the author and committer name and e-mail of multiple commits in Git](http://stackoverflow.com/questions/750172/change-the-author-and-committer-name-and-e-mail-of-multiple-commits-in-git)
* [Remove folder and its contents from git/GitHub's history](https://stackoverflow.com/questions/10067848/remove-folder-and-its-contents-from-git-githubs-history)
* [BFG Repo-Cleaner](https://rtyley.github.io/bfg-repo-cleaner/)

# Aliases
```
git config --global alias.lg "log --pretty='%Cred%h%Creset |%C(yellow)%d%Creset %s %Cgreen(%cr)%Creset %C(cyan)[%an]%Creset' --graph"
```

# Git Svn
* [Migrating from SVN to Git, preserving branches and tags](http://www.sailmaker.co.uk/blog/2013/05/05/migrating-from-svn-to-git-preserving-branches-and-tags-3/)
* [convert git-svn tag branches to real tags](http://gitready.com/advanced/2009/02/16/convert-git-svn-tag-branches-to-real-tags.html)
* [How to migrate code from SVN to GIT without losing commits history?](http://stackoverflow.com/questions/9211405/how-to-migrate-code-from-svn-to-git-without-losing-commits-history)
* [How to import svn branches and tags into git-svn?](http://stackoverflow.com/questions/2244252/how-to-import-svn-branches-and-tags-into-git-svn)

1) Create authors-transform.txt
```sh
svn log -q | awk -F '|' '/^r/ {sub("^ ", "", $2); sub(" $", "", $2); print $2" = "$2" <"$2">"}' | sort -u > authors-transform.txt
```

2) Git Svn Clone Svn repo
```sh
git svn clone --no-metadata -A authors-transform.txt --stdlayout http://SVN_REPO_NO_BRANCH_SUFFIX tmp
# git svn init  --no-metadata --authors-file=authors-transform.txt --stdlayout --prefix=svn/ http://SVN_REPO_NO_BRANCH_SUFFIX
```

3) Change svn tag branches to git tags and remove svn tag branches
```sh
git for-each-ref --format="%(refname:short) %(objectname)" refs/remotes/origin/tags \
| while read BRANCH REF
  do
        TAG_NAME=`echo ${BRANCH#*/} | sed 's/tags\///'`
        BODY="$(git log -1 --format=format:%B $REF)"
        #TAG_NAME1=`echo $TAG_NAME | sed 's/tags\///'`
        
        echo "ref=$REF parent=$(git rev-parse $REF^) tagname=$TAG_NAME body=$BODY" >&2

        git tag -a -m "$BODY" $TAG_NAME $REF^  &&\
        git branch -r -d $BRANCH
done
```
4) Change other svn branches to git branches
```sh
for branch in `git branch -r` ; do  
  BRA=`echo $branch | sed 's/origin\///'`  
  git branch $BRA refs/remotes/$branch
done
```
Remove svn branches
```sh
for branch in `git branch -r` ; do    
  git branch -r -d $branch
done
```

5) [Ignore] Already done Change origin/branch to branch
```sh
git branch -r | sed -e 's/origin\///g' | xargs -I0 git branch -m origin/0 0
git branch -m trunk master
```

6) Pusg to a remote repo
```sh
cd tmp
git remote add origin GIT_REPO
git push --set-upstream origin master 
git push --tags
```

# Git Hg
* [Converting a Mercurial repository to Git on Windows](https://www.appveyor.com/blog/2014/02/23/converting-mercurial-repository-to-git-on-windows/)
