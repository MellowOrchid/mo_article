这篇文章用来讲述如何下载安装 VS Code 并进行C/C++ 编程。

0. 系统要求：Windows 10/11 64位

1. 下载文件，单击下面的两项
   - [VS Code](https://code.visualstudio.com/sha/download?build=stable&os=win32-x64 "System Installer, x64")
   - [w64devkit](https://github.com/skeeto/w64devkit/releases "GitHub")
2. 安装 VS Code，其中，可以选择更改安装位置，记得将VS Code添加到桌面快捷方式。当然，这取决于阁下。

3. 创建工作区路径。在非系统盘中，创建名为 `vscode` 的文件夹，再在其中创建 `code` 文件夹，存放代码文件。
   - 如果想进一步区分不同语言的代码，可再在 `code` 文件夹中创建 `cpp` 文件夹等。

4. 解压 w64devkit。打开压缩包后，将其中的 `w64devkit` 直接拖入 `vscode` 文件夹中即可。

5. 配置 VS Code。打开 VS Code，在窗口左侧，会有一个叫 `Extensions` 的窗格，从上到下第五个，可以在其中搜索 `zh-cn` 与 `c` 这两个关键字，分别配置简体中文与 C/C++。就像这样两个： [![](/photo/cpp-on-vscode/extensions.png)](/photo/cpp-on-vscode/extensions.png) 它们旁边会有 `Install` 按钮。随后，VS Code 会提示重启。重启后，界面会显示简体中文。

6. 找到 `w64devkit` 里的 `bin` 文件夹，复制路径；打开开始菜单，直接输入 `path`，依次点击：编辑系统环境变量、环境变量(N)，在下面的系统变量中找到 `Path` 并双击，点击右侧 `新建`，按 `Ctrl`+`V` 将路径粘贴，形如 `D:\vscode\w64devkit\bin`。接下来，三次点击“确定”。

7. 回到VSCode中，在左下角的齿轮图标-设置中：
   - 设置字体大小，如20；
   - 由于每次编译会产生少量缓存，但日久天长，积少成多，最好别给C盘太大压力，偶尔清理一下；搜索 `cache`，找到 `C_Cpp: Intelli Sense Cache Path`，将值改为之前创建的 `cache` 文件夹路径：`cache` 即可；
   - 搜索 `format on type`，找到 `Editor: Format On Type` 打勾，这样就可以在输入完一行后自动格式化；
   - 界面左上角的 `文件(F)` 中，勾选 `自动保存`，毋庸置疑，这很有帮助。

8. 在 `文件(F)` 菜单中，`添加工作区文件夹`，将之前创建的 `code` 文件夹添加进去，选择 `信任`。可右键关闭下面的 `大纲` 与 `时间线`。

9. 点击上面的“新建文件”图标，起个名字，加上 `.cpp` 后缀，之后，可以在右下角找到叫 `Win32` 的 `C/C++配置`，点击后，选择 `编辑配置(UI)`，在 `编译器路径` 中，配置形如 `D:/vscode/w64devkit/bin/g++.exe`。

10. 写一段代码，或者复制以下代码：

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

在右上角找到▷，即“运行C/C++”文件，选择g++，随后，在下面的“终端”窗格可以看到输出结果。

至此，基础配置完成。

如果有需要，可以继续设置。（待更新）

如有问题，请联系 QQ：212637329