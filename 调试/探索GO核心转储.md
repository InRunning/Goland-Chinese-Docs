# 探索Go核心转储

有时当你调试程序时，你需要检查代码执行流和理解程序当前状态。Go核心转储是包含运行进程的内存转储及其在程序生命周期中的状态的文件。你可以在程序完成执行或仍在运行时调试内核转储。

> 只能在Linux机器上创建Go核心转储文件。但是你可以在任何支持GoLand的操作系统上查看转储文件。

>  ### 在Linux上创建Go核心转储
>
> 1. 在包含该文件的目录中打开终端。
>
> 2. 设置`文件描述符`参数为`无限的`：`ulimit -c unlimited`。
>
> 3. 在终端运行`go build .`来构建程序。在终端中，`build`命令在当前项目目录创建一个二进制文件（例如，**awesomeProject**)。
>
> 4. 要创建核心转储，运行`GOTRACEBACK=crash ./<binary_file_name>`（例如，`GOTRACEBACK=crash ./awesomeProject`）。这个命令在当前项目目录创建**核心**（**core**）文件。
>
>    ![https://resources.jetbrains.com/help/img/idea/2021.3/go_create_go_core_dump.png](https://resources.jetbrains.com/help/img/idea/2021.3/go_create_go_core_dump.animated.gif)

> ### 查看转储日志
>
> 1. 导航到**运行|打开核心转储**(**Run | Open Core Dump**)。
>
> 2. 在**可执行**（**Executable**）字段中，指定二进制文件的路径（例如，**awesomeProject**)。
>
> 3. 在**核心转储**（**Core Dump**）字段中，指定核心文件（例如，**core**)。
>
> 4. 点击**确定**（**OK**），在调试工具窗口中，选择你想要检查的帧.
>
>    ![https://resources.jetbrains.com/help/img/idea/2021.3/go_open_go_core_dump.png](https://resources.jetbrains.com/help/img/idea/2021.3/go_open_go_core_dump.animated.gif)

> ### 查看Goland中的Go core转储
>
> 1. 打开或创建Go文件的Go Build配置。
>
> 2. 在**环境**（**Environment**）字段中，点击文件夹（![The folder icon](https://resources.jetbrains.com/help/img/idea/2021.3/icons.nodes.folder.svg))。
>
> 3. 在环境变量对话框中，点击**添加**（**Add**）图标(![The Add icon](https://resources.jetbrains.com/help/img/idea/2021.3/icons.general.add.svg))
>
> 4. 点击**名字**（**Name**）字段并输入`GOTRACEBACK`。
>
> 5. 点击**值**（**Value**）字段并输入`crash`。
>
> 6. 保存所有更改并点击**确定**（**OK**）。
>
> 7. 运行程序`Shift + F10`。程序的输出将会在调试窗口展示。
>
>    ![https://resources.jetbrains.com/help/img/idea/2021.3/go_gotraceback_crash.png](https://resources.jetbrains.com/help/img/idea/2021.3/go_gotraceback_crash.animated.gif)



