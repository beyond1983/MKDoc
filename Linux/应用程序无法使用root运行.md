## 应用程序无法使用root用户运行

在linux kali下，很多应用程序安装后如果使用root帐号运行会提示无法使用，以linux下的markdown文档工具typora为例，有两种方案去解决这个问题。

1. 终端运行添加 --no-sandbox

   ![截图](/root/Git/Github/MKDoc/Files/应用程序无法使用root运行/2020-05-04 22-51-48 的屏幕截图.png)

这种方式运行只是临时的，且终端窗口不能关闭。

2. 修改程序，在usr/applications下找到对应的typora.desktop，在Exec行后添加--no-sandbox。

   ![截图](/root/Git/Github/MKDoc/Files/应用程序无法使用root运行/2020-05-04 22-57-18 的屏幕截图.png)