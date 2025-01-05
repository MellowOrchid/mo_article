2025年1月5日 21点48分

# 该文章将简单描述如何将 TLS 证书部署到网站上

1. 首先确保 `certbot` 已经安装在系统上。

   使用 `sudo apt install certbot` 即可安装。

2. 修改如下语句，将其中的 `your.domain` 修改为需要申请证书的域名：
   ```bash
   sudo certbot certonly -d your.domain -d *.your.domain --manual --preferred-challenges dns
   ```
   这条命令将以**验证 DNS** 的方式，为 `your.domain` 和 `*.your.domain` 申请证书，该域名及其二级域名均可使用该证书。

3. 执行上述语句，向 Let's Encrypt 申请证书。此过程中，需要添加或修改 DNS 记录。

   将 `_acme-challenge` 这个二级域名添加 TXT 记录，值为程序所提供的字符串。

   等待几秒钟，按下回车，一共需要添加 2 个记录。

4. 申请到的证书将被保存，路径会在控制台输出。

5. 可以复制路径，粘贴到 Nginx 的配置文件中；

   或者使用 `cat` 命令截取其中的内容，粘贴到宝塔面板里。

   值得注意的是，**私钥*不能*分享给任何人**。
