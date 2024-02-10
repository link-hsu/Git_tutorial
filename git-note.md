[ninja - git tutorial](https://www.youtube.com/playlist?list=PL4cUxeGkcC9goXbgTDQ0n_4TBzOO0ocPR "web-link")

```git --version```

```
  git config --global user.name = inkHsu
  git config --global user.email = roccoisgood@gmail.com
  git config user.name // LinkHsu
```
---
```
  git init // create .git directory - respository
  git add . // push into staging area
  git remove --cashed index.html // remove outside from staging area
  git commit -m "description for commit" // file status of snapshot for specific time
  git log // check commit history
  git log --oneline // show condense coomit history
```
---
- checkout commit
~~~
  git log --oneline
  git checkout af6b84c // detached from branch
  // 使用 git checkout 命令會將您的工作目錄切換到指定的 branch 或 commit。
  // case 1. checkout to branch -> new commit -> head and branch move to new commit
  // case 2. checkout to commit_id(no branch) -> head move to new commit 實務上會先新增一個分支
~~~
- revert commit
~~~
  git log --oneline
  git revert af6b84c // screen move to vim editor, adding a new commit after reverting [以現在狀態修改該commit修正內容，所以該修改commit之後的commit調整內容都會保留]
~~~
- reset commit
~~~
  git reset af6b84c
  // go back inside of that commit with current branch, and we can't use git log to check info [working directory still don't change](commit file still exist, but hard to find out)
  // 使用 git reset commit_id 之後使用 git log --oneline 看不到這之間的 commit 內容，是因為 git reset 命令會重置 HEAD 指針，而 git log 命令只會顯示 HEAD 指針指向的 commit 之前的歷史記錄。
  // normal case: HEAD所在commit和working directory內容會一致，但git reset此處為例外(分離)
  // 使用情境：用於單純新增過去某個commit內容，且修改內容和其之後的commit內容沒有衝突，那麼snapshot就不會有detach情形
  git reset af6b84c --hard // working directory will change to previous snapshot 
~~~
---
~~~
  git branch -D branchName // 刪除branch
  git branch -a // 列出本地和遠程的所有 branch
~~~
---
~~~
 git merge feature-a // merge feature-a(被合併) into master 
~~~
- 當您在本地端執行 git push 命令時，只有當前所在的 branch 會被推送到遠端存儲庫。
---
~~~
 git remote add origin https://github.com/link-hsu/Financial-App.git
 git remote remove origin
~~~
~~~
 git push url master
~~~