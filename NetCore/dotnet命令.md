## dotnet命令

#### dotnet build

项目编译生成，在项目的根目录下执行

#### dotnet restore

还原项目，自动还原项目依赖，下载依赖库等，项目根目录下执行

#### dotnet run

在可执行应用根目录下执行，默认应用如果只有一个.csharp文件时，可不指定项目文件。如果存在多个项目文件时，加-p（--project）指定执行项目，否则无法运行，提示存在多个项目文件。

命令范例如下：

```shell
>dotnet run -p MyCompanyName.AbpZeroTemplate.Web.Admin.csproj
```

