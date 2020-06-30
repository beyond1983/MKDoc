## 配置vscode调试netcore项目

> vscode调试应用需要***launch.json***与***tasks.json***两个配置文件，如果是在vscode新建的项目会自动添加这两个文件，从vs或其他IDE创建的项目则需要新建这两个文件。

**launch.json配置**

```json
{
    // 使用 IntelliSense 了解相关属性。 
    // 悬停以查看现有属性的描述。
    // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": ".NET Core Launch (web)",//启动名称，可自定义
            "type": "coreclr",//dotnet core固定类型
            "request": "launch",//固定值
            "preLaunchTask": "build",//对应tasks.json文件中task的name
            "program": "${workspaceRoot}/src/Zeor.CMS.Web/bin/Debug/netcoreapp3.1/Zeor.CMS.Web.dll",//启动文件路径
            "args": [],//一般留空
            "cwd": "${workspaceRoot}/src/Zeor.CMS.Web",//启动项目路径
            "stopAtEntry": false,//默认
            "serverReadyAction": {
                "action": "openExternally",//默认
                "pattern": "\\bNow listening on:\\s+(https?://\\S+)"//默认
            },
            "env": {
                "ASPNETCORE_ENVIRONMENT": "Development"//默认开发环境
            },
            "sourceFileMap": {
                "/Views": "${workspaceRoot}/Views"//默认
            }
        }
        
    ]
}
```

**tasks.json配置**

```json
{
	"version": "2.0.0",
	"command": "dotnet",//全局命令，类似在命令行中执行dotnent 命令
	"args": [],//默认
	"tasks": [
		{
			"problemMatcher": ["$msCompile"],//默认
			"args":[
				"build",//默认，拼凑为 dotnet build xxx
				"${workspaceRoot}\\src\\Zeor.CMS.Web\\Zeor.CMS.Web.csproj" //编译项目路径
			],
			"label": "build",//任务名称
			"isBuildCommand":true,
			"detail": "build web"//任务说明
		}
	]
}
```

