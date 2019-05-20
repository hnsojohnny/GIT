# git用法学习

---

[TOC]

---

### 用rebase代替merge

假如我有一个分支：`branch1`，我想把`branch1`的内容合并到`master`中，可以这样操作：
    > * 切换到`branch1`分支:`git checkout branch1`
    > * 改变`branch1`的基点，并将master合并到branch1中:`git rebase master`
    > * 切换到`master`分支:`git checkout master`
    > * 合并`branch1`分支:`git merge branch1`

可以使用场景，比如从主分支的一个`commit`中展开了一个分支：`branch1`，然后主分支又修改了一个bug，说明`branch1`中也存在这个bug，就可以使用`git rebase master`，讲`branch1`的代码和`master`新修改的bug的代码一致，这样`branch1`也和`master`一样了。

### 修改提交

如果刚刚提交的代码中有错误，但是又不想增加新的提交：
    > * 首先把错误的信息改正然后添加到缓存：`git add`
    > * 然后加上--amend提交:`git commit --amend`
    
`--amend`并不会直接修改原来的`commit`，而是生成一条新的`commit`。

### 修复以前的commit

如果以前的提交有错误，可以用`rebase -i`的方式来修改原来的`commit`
    > * `git rebase -i 目标commit`
    > * 进入编辑状态，讲`pick`改成`edit`状态
    > * 修改文件后，加入缓存:`git add`
    > * 然后加上`--amend`提交:`git commit --amend`
    > * 在修复完成之后，就可以用`rebase --continue`来继续`rebase`过程，把后面的`commit`直接应用上去。

### 丢弃刚刚的提交

需求改了，刚刚的`commit`不需要了：
    > * `git reset --hard HEAD^`
表示往回数一个位置的`commit`。

### 丢弃很早以前的提交

需求变动，之前的`commit`不需要了，按照修复以前的`commit`的方法，进入编辑页，然后删掉提交的那行就可以了。

### 修改push的提交

代码提交好了，发现写错了，要重新写：
    > * `git revert 目标commit`
    
`revert`之后把新的`commit`再`push`上去。
    
### 删了的branch再弄回来

删了的branch想还原回来:
    > * 首先查看HEAD的移动历史:`git reglog`
    > * 切换到提交的目标`commit`:`git checkout 目标commit`
    > * 创建`branch`:`git checkout -b branch名称`
    
[git介绍](https://git-scm.com/about)
