https://www.liaoxuefeng.com/wiki/896043488029600

创建仓库

```shell
git init
```

添加文件到仓库

```shell
git add test.txt
```

提交文件到仓库

```shell
git commit -m "a new commit"
```

查看仓库状态

```shell
git status
```

查看文件修改情况

```shell
git diff test.txt
```

查看提交日志

```shell
git log
git log --pretty=oneline
```

回退到上个版本

```shell
git reset --hard HEAD^
上上个版本：git reset --hard HEAD^
上100个版本：git reset --hard HEAD~100
指定版本号：git reset --hard 1094a
```

查看命令历史

```shell
git reflog
```

工作区，暂存区，版本库概念

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220729135510265.png" alt="image-20220729135510265" style="zoom:50%;" />

撤销工作区修改（本质是将暂存区内容回退到工作区）

```shell
git checkout -- test.txt
```

撤销暂存区修改（本质是将仓库HEAD内容回退到暂存区）

```shell
git reset HEAD test.txt
```

删除文件

```shell
rm test.txt
git rm test.txt / git add test.txt
```

恢复误删的文件

```shell
git checkout -- test.txt
```

连接远程仓库

```shell
git remote add origin git@github.com:xmu-tang/gitTest.git
```

推送代码到远程仓库

```shell
第一次：git push -u origin master
之后：git push origin master
```

添加SSH密钥

```shell
git bash 输入 ssh-keygen -t rsa 
按三下回车
C:\Users\Administrator.ssh目录下生成到id_rsa和id_rsa.pub两个文件，id_rsa是密钥，id_rsa.pub是公钥，将id_rsa.pub的内容添加到GitHub
```

<img src="https://img-blog.csdnimg.cn/e37928089f45478fa5f865e93de3c844.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQ29udHJvbEhvcGVsZXNz,size_20,color_FFFFFF,t_70,g_se,x_16" alt="在这里插入图片描述" style="zoom:50%;" />

从远程库克隆（首先创建远程库）

```shell
git clone git@github.com:xmu-tang/SpringBoot.git
```

创建分支

```shell
git branch dev
```

切换分支

```shell
git checkout dev
```

查看当前分支

```shell
git branch
```

合并指定分支到当前分支

```shell
git merge dev
```

删除分支

```shell
git branch -d dev
```

分支冲突后，进行手动调整，然后提交分支

查看分支合并图

```shell
git log --graph --pretty=oneline --abbrev-commit
```

强制禁用`Fast forward`模式进行合并提交

```shell
git merge --no-ff -m "merge with no-ff" dev
```

暂存工作区

```shell
git stash
```

查看暂存区内容

```shell
git stash list
```

恢复暂存区（不删除）

```shell
git stash apply
多次stash,指定恢复内容:git stash apply stash@{0}
删除：git stash drop
```

恢复暂存区（删除）

```shell
git stash pop
```

