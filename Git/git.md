# Git

> Git 设置：**设置/首选项|版本控制|Git**（**Settings/Preferences|Version Control|Git**）

## 为远程Git设置密码

每次你和远程Git仓库交互的时候（例如，在pull, update 或 push 操作期间），它需要授权。你可以[配置GoLand记住你的密码](https://www.jetbrains.com/help/go/using-git-integration.html#password-policy)，这样你就不需要在每次登录时指定你的证书。

> ### 配置密码策略
>
> 1. 在**设置/首选项**对话框`Ctrl+Alt+S`，选择左侧**外观和行为|系统设置|密码**。
>
> 2. 选择Goland处理Git远程仓库密码的方式：
>
>    - 在本机密钥链中：选择此选项可使用本机密钥链存储密码。
>
>    - 在**KeePass**中：选择此选项可使用[KeePass password manager](http://keepass.info/)去存储你的密码。当你使用**KeePass 密码管理器**，一个主密码将会被用于访问存储单个密码的文件。一旦GoLand记住你的密码，它不会要求你输入密码，除非你需要访问数据库。在**主密码**（**MasterPassword**)字段输入用于访问c.kdbx文件的密码。
>
>      可以在数据库字段中更改c.kdbx文件的默认位置。
>
>      要导入一个c.kdbx文件，点击![the Settings icon](https://resources.jetbrains.com/help/img/idea/2021.3/icon_viewMode.png)并选择从下拉菜单中导入，或单击，并指定包含密码文件的路径。
>
>      如果你想要从数据库清除已经存在的密码，选择**清除**（**Clear**）。
>
>    - **重启后不要保存，忘记密码**：如果你想在关闭GoLand后重置密码，请选择此选项。

