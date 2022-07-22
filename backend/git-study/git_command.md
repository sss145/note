### 初始化git仓库

```
git init
```

### 提交到本地仓库的基本流程

```git
#将文件提交到暂存区中
git add [文件名] 
#将暂存区中的内容上传到本地仓库
git commit -m "一段描述性质的内容"
```

### 查看仓库文件

```
git ls-files
```

### 查看版本信息

```
#查看之前的版本信息
git log 
git log -5 --pretty=oneline
#查看记录在本地的HEAD和分支引用在过去指向的位置
git reflog
```

### 回退到其他版本

```
git reset --hard [版本标识]
```

### 文件删除

```
#从本地仓库中恢复刚才删除的文件
git checkout -- [文件名]
#完全删除文件,本地仓库和工作区的文件都将被删除
git rm [文件名]
```

### 本地推送到远程

```
#ssh方式
#使用本地Git客户端生成SSH公钥与私钥 
ssh-keygen -t rsa -C "GitHub账户邮箱"
#将.ssh文件夹下的公钥复制下来,在github上新建公钥
#检查测试链接 执行命令 ssh -T git@github.com 过程中要输入yes
#根据新建的仓库页面上的提示代码进行推送操作
```

### 分支操作

|                  命令                  |                             描述                             |
| :------------------------------------: | :----------------------------------------------------------: |
|          git checkout branch           |                        切换到指定分支                        |
|       git checkout -b new_branch       |                   新建分支并切换到新建分支                   |
|          git branch -d branch          |                         删除指定分支                         |
|               git branch               |             查看所有分支,并且*号标记当前所在分支             |
|            git merge branch            |                           合并分支                           |
| git branch -m\| -M oldbranch newbranch | 重命名分支,如果newbranch名字分支已经存在,则需要使用-M强制重命名<br />,否则,使用-m进行重命名. |

### 分支Push与Pull操作

|                        命令                        |               描述               |
| :------------------------------------------------: | :------------------------------: |
|                   git  branch -a                   |        查看本地与远程分支        |
|            git push origin branch_name             |        推送本地分支到远程        |
|           git push origin :remote_branch           |    删除远程分支(本地分支保留)    |
| git checkout -b  local_branch origin/remote_branch | 拉取远程指定分支并在本地创建分支 |

### 冲突解决

1.本地分支合并冲突

2.多人协同远程冲突

解决方法:每次推送之前先拉取远程仓库的代码,可以避免80%的冲突

### 标签管理

|                命令                 |                  描述                   |
| :---------------------------------: | :-------------------------------------: |
|          git tag tag_name           | 新建标签 默认为最后一次commit的描述信息 |
|     git tag -a tag_name-m 'xxx'     |       添加标签并制定标签描述信息        |
|               git tag               |              查看所有标签               |
|         git tag -d tag_name         |            删除一个本地标签             |
|      git push origin tag_name       |           推送本地标签到远程            |
|       git push origin --tags        |    推送全部未推送过的本地标签到远程     |
| git push origin :refs/tags/tag_name |            删除一个远程标签             |

