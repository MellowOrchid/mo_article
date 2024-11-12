2024年11月12日 09点13分

# VPS 的流媒体测试

```bash
bash <(curl -L -s check.unlock.media)
```
> [GitHub \| lmc999](https://github.com/lmc999/RegionRestrictionCheck.git)

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

# Trojan-GFW

安装
```bash
sudo bash -c "$(curl -fsSL https://raw.githubusercontent.com/trojan-gfw/trojan-quickstart/master/trojan-quickstart.sh)"
```
> [GitHub \| trojan-gfw](https://github.com/trojan-gfw/trojan)

SQL配置
```sql
CREATE TABLE users (
    id INT UNSIGNED NOT NULL AUTO_INCREMENT,
    username VARCHAR(64) NOT NULL,
    password CHAR(56) NOT NULL,
    quota BIGINT NOT NULL DEFAULT 0,
    download BIGINT UNSIGNED NOT NULL DEFAULT 0,
    upload BIGINT UNSIGNED NOT NULL DEFAULT 0,
    PRIMARY KEY (id),
    INDEX (password)
);
```
> [Authenticator \| trojan](https://trojan-gfw.github.io/trojan/authenticator)

# 各大镜像

- [阿里巴巴开源镜像站](https://developer.aliyun.com/mirror/)
- [南京大学 Mirror](https://mirror.nju.edu.cn/)
- [清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/)
