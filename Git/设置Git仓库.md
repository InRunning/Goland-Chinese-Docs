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

> ## 将整个项目与单个Git存储库相关联
>
> 1. 打开你想要放置在Git下的项目。
>
> 2. 从**VCS**主菜单或**VCS操作窗口**`Alt + \` `或选择**启用集成版本控制**（**Enable Version Control Integration**)。
>
> 3. 选择**Git**作为版本控制系统并单击**OK**。
>
> 4. 在VCS 集成启用后，GoLand 将询问你是否想要通过VCS分享项目设置。你可以选择**总是加上**（**Always Add**)去和其它使用GoLand工作的仓库使用者同步项目设置。
>
>    ![Notification prompting to select how to treat configuration files](https://resources.jetbrains.com/help/img/idea/2021.3/sharing-project-notification.png)

> ### 将项目中的不同目录与不同的Git存储库相关联
>
> 1. 打开你想要放置在Git下的项目。
>
> 2. 从主菜单中，选择**VCS|创建Git仓库**（**VCS|Create Git Repository**)。
>
> 3. 在打开的对话框中，指定将要在其中创建Git仓库的目录。
>
>    Git不支持外部路径，因此如果你想要选择项目根目录之外的路径，确保你创建仓库的文件夹也包含项目根目录
>
> 4. 如果你在项目结构中创建多个Git仓库，重复每个文件夹中的上述步骤

在你为你的项目初始化一个Git仓库后，你需要添加项目文件到仓库。

> ### 添加文件到本地仓库
>
> 1. 在**提交**（**Commit**）工具窗口`Alt+0`，展开**没有版本的文件**(**Unversioned Files**)节点。
>
> 2. 选择你想要添加到Git或整个更改列表的文件，然后按`Ctrl + Alt + A`或从上下文菜单选择**添加到VCS**（**Add to VCS**）
>
>    你也可以从项目工具窗口添加文件到本地Git仓库：选择你想要添加的文件，然后按`Ctrl + Alt + A`或从上下文菜单选择**Git | 添加**（**Git | Add**）。

当你的项目启用Git集成，GoLand推荐添加每个新建的文件到Git，及时它在GoLand外部被添加。你可以在IDE设置页`Ctrl + Alt + S`的**版本控制|确认**（**Version Control | Confirmation**)更改行为。如果你想要特定文件保持没有版本（unversioned），你可以忽略它们。

> 如果你想要添加一个在**.gitignore**上的文件，GoLand将建议强制添加它。在确认对话框单击**取消**（**Cancel**）只会取消强制添加忽略的文件 - 所有其它文件都将被添加到Git仓库。

## 从版本控制中排除文件（ignore)

有时你想要让特定文件unversioned。这些可能是VCS管理文件，使用程序文件，备份副本等。你可以通过GoLand忽略文件，IDE不会建议将它们添加到Git中，而是将它们高亮显示为已忽略。

你只能忽略*unversioned*文件，即你在**Unversioned Files**更改列表中看到的文件。如果文件已经被添加到Git但是还没有commit，你可以在**本地更改**视图右键并选择**回滚**（**Rollback**)。

Git允许你在两种配置文件中列出被忽略的文件模式：

- .git/info/exclude 文件。

  此文件中列出的模式仅仅适用于仓库的本地版本。

  当你初始化或check out 一个Git仓库时这个文件自动被创建。

- 一个或多个在VCS根目录及其子目录的 .gitignore 文件。

  这些文件被放入仓库，以便整个团队都可以使用其中的忽略模式。因此，它是存储被忽略的文件模式的最常见的地方。

  如果在VCS根目录中没有 .gitignore 文件，你可以右键项目窗口的任何地方，选择**New | File**(**新建|文件**)并在**新建文件**（**New File**）对话框中输入 .gitignore。

  > 要在Windows 文件管理器创建 **.gitignore**文件，创建文件名为 **.gitignore**。然后Windows 会自动将它重命名为 **.gitignore**。

> ### 添加文件到 .gitignore 或 .git/info/exclude
>
> 1. 决定要使用哪种Git配置文件来忽略文件。如果有疑虑，使用 **.gitignore**。
>
> 2. 在**本地更改**（**Local Changes**）视图或项目工具窗口找到要忽略的 unversioned 文件或文件夹。[这些视图的文件颜色](https://www.jetbrains.com/help/go/file-status-highlights.html)将帮助你辨识文件的状态。
>
> 3. 右键所选内容并选择**Git|Add to .gitignore**或**Git | Add to .git/info/exclude**。
>
>    这些视图的文件颜色帮助你辨别文件的状态。







