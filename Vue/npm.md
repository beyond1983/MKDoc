## npm使用

yarn或者npm还原项目的时候如果因为gulp与npm版本不兼容报错，可通过安装nvm切换本机nodejs版本解决。

### nvm

nvm是npm版本管理工具，安装后可以在本机使用不同的nodejs版本，下载地址[nvm下载地址](https://github.com/coreybutler/nvm-windows/releases)

使用范例：

安装nodejs 11.15.0版本

```powershell
nvm install 11.15.0
```

切换本机nodejs为11.15.0版本

```powershell
nvm use 11.15.0
```

* nvm的安装路径不能包含有空格或者中文，否则使用的时候会异常，中文乱码，可以通过拷贝nvm安装文件夹到盘符根据了下，然后更改环境变量路径，最后更改nvm安装路径下的setting文件对应的nvm安装路径，解决问题。

### Gulp打包

使用Gulp打包提示"ReferenceError: internalBinding is not defined",版本不兼容问题，直接执行 npm install natives@1.1.6 解决