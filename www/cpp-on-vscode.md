这篇文章用来讲述如何配置VSCode。

0.  系统要求：Windows 10/11 64位
    
1.  下载文件，单击下面的两项
    
    *   [VScode](https://code.visualstudio.com/sha/download?build=stable&os=win32-x64 "System Installer, x64")
    *   [w64devkit](https://github.com/skeeto/w64devkit/releases "GitHub")
    *   对于VSCode，如果下载速度慢，请转到下载，复制下载链接，粘贴到地址栏，将前面的`az…….net`替换为`vscode.cdn.azure.cn`，其它内容不变。最终，链接形如`https://vscode.cdn.azure.cn/stable/xxxxxx/VSCodeSetup-x64-x.xx.x.exe`。
    *   对于w64devkit，如果顺利访问GitHub，请点击最新版中的`w64devkit-x.xx.x.zip`，将自动下载；或者，请点击[这里](https://wp.morchid.top/cloud/#s/9V2FP8_Q "w64devkit 1.19.0")，从本站下载。
2.  安装VSCode，其中，可以选择更改安装位置，记得将VSCode添加到桌面快捷方式。当然，这取决于阁下。
    
3.  创建工作区路径。鄙人的建议是，在非系统盘中，创建名为`vscode`的文件夹，再在其中创建`cache`与`code`这两个文件夹，分别存放编译缓存与代码文件。
    
4.  解压w64devkit。打开压缩包后，将其中的`w64devkit`直接拖入`vscode`文件夹中即可。
    
5.  配置VSCode。打开VScode，在窗口左侧，会有一个叫`Extensions`的窗格，从上到下第五个，可以在其中搜索`zh-cn`与`c`这两个关键字，分别配置简体中文与C/C++。就像这样两个： [![](https://wp.morchid.top/wp-content/uploads/2023/06/vsc1-300x106.png)](https://wp.morchid.top/wp-content/uploads/2023/06/vsc1.png) 它们旁边会有“Install”字样。随后，VSCode会在提示重启。重启后，界面会显示简体中文。
    
6.  找到`w64devkit`里`bin`文件夹，复制路径；打开开始菜单，直接输入“path”，依次点击：编辑系统环境变量、环境变量(N)，在下面的系统变量中找到“Path”并双击，点击右侧“新建”，按`Ctrl+V`将路径粘贴，此时，形如`D:\vscode\w64devkit\bin`。接下来，三次点击“确定”。 回到VSCode中，在左下角的齿轮图标-设置中：
    
    *   设置字体大小，可以是20；
    *   由于每次编译会产生少量缓存，但日久天长，积少成多，最好别给C盘太大压力，偶尔清理一下；搜索`cache`，找到`C_Cpp: Intelli Sense Cache Path`，将值改为之前创建的`cache`文件夹路径，例如`D:\vscode\cache`；
    *   搜索`format on type`，找到`Editor: Default Formatter`，修改为`C/C++`，并将`Editor: Format On Type`打勾，这样就可以在输入完一行后自动格式化；
    *   界面左上角的“文件”中，打开“自动保存”，毋庸置疑，这很有帮助。
7.  在左侧第一个“文件”窗格中，“添加工作区文件夹”，将之前创建的`code`文件夹添加进去，选择信任即可。关闭下面的“大纲”与“时间线”，会更方便今后code。
    
8.  点击上面的“新建文件”，写个名字，加上`.cpp`后缀，之后，可以在右下角找到叫`Win32`的`C/C++配置`，点击后，选择`编辑配置(UI)`，在`编译器路径`中，配置为`D:/vscode/w64devkit/bin/g++.exe`。
    
9.  写一段代码，或者复制以下代码：
    

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << "Hello World.";
    // system("pause");
    return 0;
}
```

在右上角找到▷，即“运行C/C++”文件，选择g++，随后，在下面的“终端”窗格，阁下可以看到输出结果。

至此，基础的配置完成。如果有需要，可以继续设置。 （等待更新） [![](https://wp.morchid.top/wp-content/uploads/2023/06/vs-300x200.png)](https://wp.morchid.top/wp-content/uploads/2023/06/vs.png) 如有问题，请联系： QQ：212637329