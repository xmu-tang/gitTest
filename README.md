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

