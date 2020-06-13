## window环境下编译net core项目提示“无法找到回退包文件夹NuGetFallbackFolder”

系统卸载Jetbrains Rider2020后又安装了Jetbrians Rider2019，然后编译原来的net core项目时就无法成功，错误信息如下截图：

![img](F:\GitHub\MKDoc\Files\5R[`C$P@BJ00P[0N1U$_RW.png)

从提示信息可以看到，找不到“NuGetFallbackFolder”文件夹，此时，只需要在对应的sdk文件夹下新建一个“NuGetFallbackFolder”的文件夹即可解决这个问题。如本机安装路径为  C:\Program Files\dotnet\sdk，只需要在此文件夹下新建一个NuGetFallbackFolder文件夹，然后执行dotnet build，可以看到项目编译成功。

![image-20200605221908560](F:\GitHub\MKDoc\Files\image-20200605221908560.png)

