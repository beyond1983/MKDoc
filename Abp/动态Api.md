## Abp vnext自动API控制器

Application项目中的service服务默认会自动生成API控制器，但使用Tiered分层模式的项目，由于项目结构原因，不会自动生成API控制器，需要手动在HttpApi项目中添加Controller然后调用Service。[官方说明](https://github.com/abpframework/abp/issues/1469#issuecomment-517705968)

