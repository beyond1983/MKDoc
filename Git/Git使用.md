### Github 安装

要使用Github，首先我们要在系统上安装Git，下载系统对应Git并安装。

- [下载 git OSX 版](http://code.google.com/p/git-osx-installer/downloads/list?can=3)
- [下载 git Windows 版](http://msysgit.github.io/)
- [下载 git Linux 版](http://book.git-scm.com/2_installing_git.html)

### Git配置

首先在本地创建`ssh key`,WIndows下可以使用PowerShell

```powershell
$ ssh-keygen -t rsa -C "your_email@youremail.com"
```

后面的`your_email@youremail.com`改为你在github上注册的邮箱，之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。成功的话会在`~/`下生成`.ssh`文件夹，进去，打开`id_rsa.pub`，复制里面的`key`。

回到github上，进入 Account Settings（账户配置），左边选择SSH and GPG Keys，New SSH Key

![image-20200307095705239](../Files/Git%E4%BD%BF%E7%94%A8/image-20200307095705239.png)

title随便填，粘贴在你电脑上生成的key。

![image-20200307095816580](../Files/Git%E4%BD%BF%E7%94%A8/image-20200307095816580.png)

为了验证是否成功，在git bash下输入：

```
$ ssh -T git@github.com
```

如果是第一次的会提示是否continue，输入yes就会看到：You've successfully authenticated, but GitHub does not provide shell access 。这就表示已成功连上github。

接下来我们要做的就是把本地仓库传到github上去，在此之前还需要设置username和email，因为github每次commit都会记录他们。

```
$ git config --global user.name "your name"
$ git config --global user.email "your_email@youremail.com"
```



### 创建本地仓储

创建新文件夹，打开，然后执行` git init` 以创建新的 git 仓库。

### Github远程仓储

使用Github,要求的是先在Github上创建对应的repository,当我们在Github上创建好仓储后，配置本地设置

命令行下切换到对应的文件夹，添加远程地址：

```
$ git remote add origin git@github.com:yourName/yourRepo.git
```

后面的yourName和yourRepo表示你再github的用户名和刚才新建的仓库，加完之后进入.git，打开config，这里会多出一个remote "origin"内容，这就是刚才添加的远程地址，也可以直接修改config来配置远程地址，配置好后就可以使用了。

1.拉取远程仓库文件

> git pull origin master

origin是我为远程仓库取得名次，以便区分仓库

2.提交本地文件到缓存

添加所有文件

> git add *

添加制定文件

> git add 文件名称

添加提交说明

> git commit -m "提交说明"

3.提交文件到仓库

> git push