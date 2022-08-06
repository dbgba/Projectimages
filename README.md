# 项目简介
* 这是基于稚晖君[ElectronBot
](https://github.com/peng-zhihui/ElectronBot)的SDK扩展应用的玩法示例项目，使用AutoHotkey来进行SDK调用与演示

* 因为[AutoHotkey
](https://www.autohotkey.com/)是脚本语言，用记事本即可编辑.ahk文件，和批处理.bat原理类似。对于想要修改自定义参数的可编辑.ahk文件，保存运行即可。无需前端界面

来实现，它能更方便的对电脑进行深度调用和流程自动化处理。

# 使用介绍
虽然AHK可以将解释器与.ahk脚本设为同名，免安装使用。但是为了方便调试使用，但是建议到[AutoHotkey
](https://www.autohotkey.com/download/ahk-install.exe)官网下载安装一下【建议使用默认选项安装】。毕竟安装包就3MB大小，能避免不必要的麻烦。

安装好AutoHotkey后，就可以对.ahk文件右键选**Edit Script**来编辑脚本了。项目所有示例中我只保留适配与ElectronBot相关的代码，而实际使用中我们可以使用AHK自身对电脑状态的判断和调用来实现很多的功能。例如：判断时间来设置电脑音量、当ElectronBot做姿势后，跟着播报自定义语音、判断进程状态决定开关某程序等等。需要根据自身情况查看[AHK中文帮助文档](https://www.autoahk.com/help/autohotkey/zh-cn/docs/commands/WinActive.htm)或使用对应函数类库做具体实现。


# 项目文件简要说明

每个文件夹的示例中都附带了详细截图与代码注释，以下仅做一些简单的介绍。

![](https://gcore.jsdelivr.net/gh/dbgba/HTTPRemoteConsole@master/Preview.jpg)
1.通过微信来控制ElectronBot

使用Accessible技术获取指定联系人的信息做为控制信号，即可实现比如：收到ElectronBot姿势参数后，调用SDK完成动作。
[演示截图.png]


2.智能家居控制

此示例选了一个简单易完成的方法硬改来实现电脑控制智能家居。示例用的继电器是CH340驱动，而AHK就能直接与CH340设备通信来进行控制。

[3.将引出的线接到继电器.jpg]


3.量子纠缠Demo半成品

之前想模仿稚晖君视频里的"量子纠缠"做的可行性测试Demo，目前只是用OpenCV识别获取人脸坐标并裁剪在电脑上显示。还没有研究怎么更好的传入ElectronBot上同步显示。


4.多个ElectronBot远程Tcp网络互动

此示例是简单的验证了一下AHK通过公网IP或者局域网远程同步两台ElectronBot的互动反应。


5.摄像头手势识别与ElectronBot同步

此示例需要与我另一个手势识别项目配合来实现，示例预设演示同步动作有：双手放下时、单手举起握拳时、单手举起做剪刀手时、双手举起握拳时。摄像头识别到上述手势后，ElectronBot也会同步反应。当双手举起握拳时，会执行一套预设的长动作。

[推荐手势设置.jpg]


6.语音唤醒并调用ElectronBot表情

此示例需要与我另一个手势识别项目中的语音识别来实现。因为调用的是Windows自带的API来实现的，不能保证所有系统都能复现。大致就是演示一种玩法，让ElectronBot可以变成你的语音助手。已经提供了SDK调用方法，用什么语音方案可自行选择。

7.连接ElectronBot时自动推送表情

ElectronBot在每次接入USB时都会以默认花屏显示，此辅助示例通过注册USB设备监控事件来让每次接入的是ElectronBot就立即同步指定表情或姿势。


8.热键快速调试ElectronBot

在日常调试ElectronBot时，需要打开上位机调整对应参数后，再同步到ElectronBot。而AutoHotkey就是为设置键盘快捷键而生的，示例简单演示了F1、F2、F3为头部上下和姿势归位，上下键为左手的抬起放下，左右键为右手的抬起放下。




:=:=:=:=:=:=:=:=:=:=:=:=:=:=

等待下载完成后，软件会**自动解压**并**适配手势识别**功能。

[下载中.png]

之后就可以对你的**摄像头**进行**手势识别**控制了。下图示例为：当**双手抬起**并**竖起大拇指**时，就**执行打开网页并放大网页**。

[添加手势代码.png]

软件还附带了**调用Windows自带API**来实现的**免费语音助手**。下图示例为：说出**电子电子**唤醒语音识别后，再说出关键字**启动游戏大厅**即可执行对应的**自定义流程**。

[添加语音识别代码.png]

更多**玩法**和用法，请详见**设置**与**帮助**的具体说明。例如：**当摄像头中有人时，自动切换到虚拟桌面。**
想创造更多自动化玩法组合，可使用软件附带的**生成快捷代码**和[AHK中文帮助文档](https://www.autoahk.com/help/autohotkey/zh-cn/docs/commands/WinActive.htm)来实现自己的**定制需求**。

# 注意事项

* 此exe文件为[AutoHotkey](https://github.com/Lexikos/AutoHotkey_L)开源项目，请将其加入杀毒-信任区。避免不必要的麻烦。

* 手势识别需要借助电脑的摄像头实现（任意摄像头都行），而语音识别需要接电脑麦克风实现。由于语音识别是调用Windows自带API来实现的，有些系统为了缩减体积会删掉此语音识别播报API导致无效。用原版镜像上安装的系统基本都不会出这问题。

* 我添加了4个手势依赖包的镜像源供高速下载，如果出现某个镜像源无法下载的情况。可根据弹出提示点击重新换源下载即可。如果镜像源和官方源自动下载都失效，只能自行想办法从官方GitHub下载"GoogleMediapipePackageDll-main.zip"压缩包后，将压缩包存放在"Lib"目录中，重启软件即可识别压缩包并解压适配手势识别功能。


# 感谢以下项目

>[peng-zhihui/ElectronBot: Open Source Desktop Robotics Project](https://github.com/peng-zhihui/ElectronBot)
>
>[Lexikos/AutoHotkey_L: AutoHotkey - macro-creation and automation-oriented scripting utility for Windows. (github.com)](https://github.com/Lexikos/AutoHotkey_L)
>
>[HW140701/GoogleMediapipePackageDll: package google mediapipe hand and holistic tracking into a dynamic link library](https://github.com/HW140701/GoogleMediapipePackageDll)