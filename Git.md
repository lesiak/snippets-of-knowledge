# Daily usage
* [Undoing a git rebase](http://stackoverflow.com/questions/134882/undoing-a-git-rebase)
```
git reflog
git reset --hard HEAD@{XXXX}
```
 
# Setup
* [Git file permissions on Windows](http://stackoverflow.com/questions/6476513/git-file-permissions-on-windows)
* [What's the best CRLF (carriage return, line feed) handling strategy with Git?](http://stackoverflow.com/questions/170961/whats-the-best-crlf-carriage-return-line-feed-handling-strategy-with-git)
* [Git: How configure KDiff3 as merge tool and diff tool](http://stackoverflow.com/questions/33308482/git-how-configure-kdiff3-as-merge-tool-and-diff-tool)

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

# Git Hg
* [Converting a Mercurial repository to Git on Windows](https://www.appveyor.com/blog/2014/02/23/converting-mercurial-repository-to-git-on-windows/)
