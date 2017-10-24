# Daily usage
* [Undoing a git rebase](http://stackoverflow.com/questions/134882/undoing-a-git-rebase)
```
git reflog
git reset --hard HEAD@{XXXX}
```

* [How to move certain commits to another branch in git?](https://stackoverflow.com/questions/2369426/how-to-move-certain-commits-to-another-branch-in-git) 

# Setup
* [Git file permissions on Windows](http://stackoverflow.com/questions/6476513/git-file-permissions-on-windows)
* [Git/Bash is extremely slow in Windows 7 x64](https://stackoverflow.com/questions/4485059/git-bash-is-extremely-slow-in-windows-7-x64)
* [What's the best CRLF (carriage return, line feed) handling strategy with Git?](http://stackoverflow.com/questions/170961/whats-the-best-crlf-carriage-return-line-feed-handling-strategy-with-git)
* [Dealing with line endings](https://help.github.com/articles/dealing-with-line-endings/)
* [Git: How configure KDiff3 as merge tool and diff tool](http://stackoverflow.com/questions/33308482/git-how-configure-kdiff3-as-merge-tool-and-diff-tool)
* [Pimp My Git – Manage Different Git Identities](https://dzone.com/articles/pimp-my-git-manage-different-git-identities)

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
git svn clone --no-metadata -A authors-transform.txt --stdlayout http://SVN_REPO tmp
# git svn init  --no-metadata --authors-file=authors-transform.txt --stdlayout --prefix=svn/ http://SVN_REPO
```

3) Change svn tag branches to git tags
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
git push 
git push --tags
```

# Git Hg
* [Converting a Mercurial repository to Git on Windows](https://www.appveyor.com/blog/2014/02/23/converting-mercurial-repository-to-git-on-windows/)
