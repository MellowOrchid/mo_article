2024年11月14日 21点20分

# 安装 Maven

ℹ️ 建议动手操作前通读一遍文章。

## Windows

### 下载 Maven

- 发文时，maven 的最新稳定版为 3.9.9
- 若要检查最新的版本，可从[此地址](https://mirrors.tuna.tsinghua.edu.cn/apache/maven/ "清华 Apache maven 镜像")检查形如 `maven-3` 的文件夹是否有更新的

[Apache 官方](https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.zip)

[清华大学镜像站](https://mirrors.tuna.tsinghua.edu.cn/apache/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.zip)

> [Maven 官网](https://maven.apache.org/)

### 安装 Maven


1. 打开之前下载的压缩文件，如 `apache-maven-3.9.9-bin.zip`

2. 将压缩文件中的 `apache-maven-3.9.9` 文件夹拖拽到一个合适的目录下，如 `D:\code\maven`

    - **请勿**将其解压至类似于 `Program Files` 这样的文件夹中[^注1]

    - 建议在其他目录下新建文件夹，如 `D:\code` 作为专用的代码目录

### 配置 Maven

配置其下 `conf\settings.xml`：

1. 找到 `<mirrors>` 标签
   - 大致在 147 至 173 行
   - 该标签周围有多行注释，如果使用记事本编辑，请注意识别
2. 选中其中的 `<mirror>` 标签
   - **请勿多选 `</mirrors>`**
3. 删除或注释选中部分，替换为以下镜像源：
    ```xml
    <mirror>
        <id>aliyunmaven</id>
        <mirrorOf>*</mirrorOf>
        <name>阿里云公共仓库</name>
        <url>https://maven.aliyun.com/repository/public</url>
    </mirror>
    ```
   - 这段配置文件可以在这里找到：
   > [阿里巴巴 maven 镜像](https://developer.aliyun.com/mirror/maven)
4. 保存该文件
   - 如果保存时提示权限不足，请重做第一步，注意将其解压至权限足够的文件夹里

### 配置 PATH

1. 配置环境变量
   1. 打开开始菜单，搜索 `path`
   2. 点击 `编辑系统环境变量`
   3. 点击 `环境变量(N)…`
   4. 在下方的 `系统变量(S)` 中找到 `变量` 名为 `Path` 的行，双击或点击 `编辑(I)…`
   5. 依次点击 `新建(N)`、`浏览(B)…`，找到之前 `apache-maven-3.9.9` 文件夹下的 `bin`，点击 `确定`
      - 请勿漏选 `bin`
      - 最终路径形如 `D:\code\apache-maven-3.9.9\bin`
   6. 3 次点击 `确定` 保存修改

2. 按下 `Win`+`R` 输入 `cmd` 打开命令提示符

3. 键入 `mvn -v`，按下回车后，输出应形如：
   ```
    Apache Maven 3.9.9 (8e8579a9e76f7d015ee5ec7bfcdc97d260186937)
    Maven home: D:\code\apache-maven-3.9.9
    Java version: 21.0.2, vendor: Oracle Corporation, runtime: D:\Program Files\Java\jdk-21
    Default locale: zh_CN, platform encoding: UTF-8
    OS name: "windows 11", version: "10.0", arch: "amd64", family: "windows"
   ```

至此，Windows 平台的 maven 配置结束

[^注1]: 因为操作 `Program Files` 需要更高的权限，使得修改其目录下的文件同样需要更高的权限，不利于大多数用户使用，亦不利于接下来配置镜像