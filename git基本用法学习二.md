## <center>git远程仓库用法学习二</center>
***

### 远程仓库
* > git remote

    _可以看到每个远程服务器简写，`git`会默认给克隆的仓库服务器名称为`origin`。_
* > git remote -v

    _可以看到项目远程仓库读写地址。_

* > git remote add `<remote-name>` `<url>`

    _添加一个新的远程`git`仓库_
* > git fetch `<remote-name>`

    _拉取信息到远程仓库_
* > git remote show `<remote-name>`

    _查看远程仓库信息。_
* > git remote rename `old-remote-name` `new-remote-rename`

    _重命名远程仓库名称_
* > git remote rm `remote-name`

    _移除远程仓库_

### 标签
  * > git tag

      _查看标签列表_
  * > git tag -l '`标签名称`'

      _查看输入的含有标签名称的所有标签_
  * 创建标签

    `git`标签主要有两种：轻量标签(不会保存各种常见信息，所以推荐只是想用一个临时的标签)；附注标签(包含很多信息，通常建议创建附注标签)。
      * 附注标签
        > git tag -a `标签名称` -m `提交信息`

        _创建附注标签_
        > git show `标签名称`

        _查看标签信息_
    * 轻量标签
      > git tag `标签名称`

      _创建轻量标签_

    * 在某次提交打标签
      > git tag -a `标签名称` `生成提交字符串的前六位`

  * 提交标签到远程服务器
      > git push origin `tagname`

      _提交到tag到远程服务器_
      > git push origin --tags

      _把所有不在远程服务器的tag都上传_
  * 检出标签
    > git checkout -b `分支名字` `tagname`
