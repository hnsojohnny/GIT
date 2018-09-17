## <center>git分支学习</center>
***

### 查看分支
> git branch

### 创建分支
> git branch `branchname`

_创建一个名为`branchname`的分支。_

### 切换分支
> git checkout `branchname`

_切换`branchname`分支_

> git checkout -b `branchname`

_创建并切换分支_

### 分支合并
> git merge `branchname`

_把当前分支和`branchname`合并,如果合并的两个分支都对同一文件进行了修改，那么合并的时候，要先解决掉冲突，然后重新提交。_

### 查看分支的最后一次提交
> git branch -v

### 查看分支合并
> git branch --merged

_查看有那些分支合并到了当前分支。如果已经合并了，但是列表中还能看见的分支，可以删除已经合并的分支。_

### 查看未合并分支
> git branch --no-merged

### 删除分支
> git branch -d `branchname`

### 强制删除分支
> git branch -D `branchname`

### 推送
> git push `remotename` `branchname`

### 拉取
> git pull `remotename` `branchname`

### 删除远程分支
> git push `remotename` -d `branchname`
  * > git fetch

    _从服务器上抓取本地没有的数据_
