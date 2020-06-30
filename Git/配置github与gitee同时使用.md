#### 1. 清理全局信息（新装Git可以跳过该步骤）

查看全局设置命令

```powershell
git config --global --list
```

清理用户名、邮箱

```powershell
git config --global --unset user.name
git config --global --unset user.email
```

#### 2.生成加密钥匙文件

生成Github加密钥匙文件

```powershell
ssh-keygen -t rsa  -C "xx@qq.com"
```

根据提示输入文件存放路径，其它留空回车

```powershell
C:\Users\Administrator/.ssh/id_rsa_github
```

同理生成操作生成Gitee加密钥匙文件

```powershell
ssh-keygen -t rsa  -C "xx@qq.com"
```

根据提示输入文件存放路径，其它留空回车

```powershell
C:\Users\Administrator/.ssh/id_rsa_gitee
```

#### 3.多账号必须配置 config 文件(重点)

若无 config 文件，则需在C:\Users\Administrator/.ssh创建 config 文件。 config文件内容

```powershell
#Default gitHub user Self
Host github.com
HostName github.com
User git #默认就是git，可以不写
IdentityFile ~/.ssh/id_rsa.github

# gitee
Host gitee.com
Port 22
HostName gitee.com
User git
IdentityFile ~/.ssh/id_rsa.gitee
```