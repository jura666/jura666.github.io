---
title: GITPRO之git常用命令
date: 2018-09-04 13:40:03
tags:
---

`git remote`	查看当前配置有哪些远程仓库
`git remote -v`	(verbose首字母)显示对应的克隆地址

#### 添加远程仓库
`git remote add [shortname] [url]`

#### 从远程仓库抓取数据到本地
`git fetch [remote-name]` 手工合并
#### git pull
如果设置了某个分支用于跟踪远端仓库的分支，可以使用	`git pull`自动抓取数据下来\\自动合并

`git push [remote-name][branch-name]`  将本地仓库中的数据推送到远端仓库

`git remote show [remote-name]` 查看某个远端仓库的详细信息

`git remote rename`修改某个远端仓库在本地的简称

`git remote rm`移除对应的远端仓库

----------

## 标签 tag
用`-a`(annotated首字母)指定标签名字
例如：`git tag -a v1.4 -m 'my version 1.4'`

`git show v1.4`查看相应标签的版本信息

##### 签署标签
如果有私钥，可以用GPG来签署标签，只要把之前的`-a`改为`-s`(signed的首字母)

#### 轻量级标签
不需要`-a` `-s` `-m`直接给出标签名字即可

#### 验证标签
`git tag -v [tag-name]`(verify首字母)

#### 后期加标签
在提交历史中 `$ git log --pretty = oneline`
在打标签的时候跟上对应提交对象的校验和(或前几位字符)即可
例：`$git tag -a v1.2 9fceb02`

#### 分享标签
`git push origin [tagname]`推送一个 例：`git push origin v1.5`
要一次推送所有本地新增的标签上去，使用`--tags`选项 例：`git push origin --tags`

`git log`查看提交历史

`git log -p -2``-p`展开显示每次提交内容的差异`-2`仅显示最近的两次更新

----------

## git分支

#### 何谓分支
`git branch testing`在当前commit对象上新建一个分支指针testing

`git checkout`切换到其他分支

`$git checkout testing`这样HEAD就指向了testing指针

`$git checkout -b iss53`相当于
> `git branch iss53`
> `git checkout iss53`

#### 修补
`$git checkout -b hotfix`
创建一个紧急修补分支
`git checkout master`
`git merge hotfix`fast forward 简单地把指针右移
`git branch -d hotfix`删除hotfix

#### 分支的管理
`git branch`给出分支清单
`git branch -v`查看各个分支最后一个提交对象的信息
`git branch --merged`查看哪些分支已被并入当前分支
`git branch --no-merged`查看尚未合并的工作
`git branch -d`删除未合并的分支会提示错误 `git branch -D`强制执行

#### 利用分支进行开发的工作流程
常用分支名称：
- `master`
- `develop`
- `topic`特性分支
- `proposed`建议
- `pu`proposed update，建议更新

`git fetch origin`同步远程服务器的数据到本地