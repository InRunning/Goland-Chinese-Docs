# 设置Git仓库

 当你clone一个存在的Git仓库，或将现有项目置于Git版本控制之下，GoLand自动检测Git是否安装在计算机上。如果IDE不能定位Git的可执行程序，它将建议下载它。

GoLand支持WSL2的Git，WSL2在Windows 10 version 2004 可用。

如果Git没有安装在Windows上，GoLand会在WSL中搜索Git并从哪里使用它。此外，对于使用\\\wsl$路径打开的项目，GoLand会自动从WSL切换到Git。

如果你需要手动配置GoLand使用WSL中的Git，转到**版本控制|Git**（**Version Control|Git**）的IDE设置`Ctrl+Alt+S`页，单击指向Git可执行文件的路径字段中的浏览图标，并通股\\wsl$路径选择来则WSL的Git，例如，\\\wsl$\debian\usr\bin\gin。

## 从远程主机 Check Out 项目

GoLand 允许你 check out（在 Git 术语是 *clone*)一个存在的项目并基于你下载的数据创建一个新的项目。

> 1. 从主菜单中，选择**Git | Clone**，或者，如果当前没有项目打开，请单击**欢迎**（**Welcome**)**从VCS获取**（**Get from VCS**）。
>
> 2. 在**从版本控制获取**（**Get from Version Control**)对话框中，指定要从远程仓库clone的URL，或选择左侧的一个VCS托管服务。
>
>    如果你已经登录进选择的托管服务，则“完成”将提示你可以clone的仓库列表。
>
> 3. 单击**Clone**（**Clone**）。如果你要基于你clone的源创建项目，单击在确认对话框中的**Yes**。Git root 映射将自动设置为项目根目录。
>
>    如果你的项目包含子模块，它们也会被clone并且自动注册为项目根。

## 将现有项目置于Git版本控制之下

你可以根据现有的项目源创建一个本地的Git仓库。



