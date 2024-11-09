2024年11月9日 14点35分

# VPS 的流媒体测试
```bash
bash <(curl -L -s check.unlock.media)
```
> [GitHub](https://github.com/lmc999/RegionRestrictionCheck.git)

# Ubuntu Server 设置中文
首先更新 apt 并安装中文语言包：
```bash
sudo apt update && sudo apt install language-pack-zh-hans -y
```
其次设置 locale：
```bash
sudo dpkg-reconfigure locales
```
需要重启服务器
```bash
sudo reboot
```

# 各大镜像
- [阿里巴巴开源镜像站](https://developer.aliyun.com/mirror/)
- [南京大学镜像站](https://mirror.nju.edu.cn/)
- [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/)