2026年1月5日 20点53分

## 安装 Typecho 后阅读文章或登录出现 404 的解决方案

正常安装好 Nginx 与 PHP，配置完 Tyepcho 后首次查看文章或是登录、管理后台出现 404，是因为 Nginx 配置文件中 location 块的问题。

常见解决方法是添加 if 语句：
```nginx
location / {
    if (-f $request_filename/index.html) {
        rewrite (.*) $1/index.html break;
    }
    if (-f $request_filename/index.php) {
        rewrite (.*) $1/index.php;
    }
    if (!-f $request_filename) {
        rewrite (.*) /index.php;
    }
    try_files $uri $uri/ =404;
}
```

可行，但是使用 if 可能引发性能问题。

另一种方法是：
```nginx
location / {
    try_files $uri $uri/ /index.php$is_args$args;
}
```
只需要将原有的 `=404` 换掉就可以了。

各个版本：
>nginx version: nginx/1.24.0 (Ubuntu)
>
>PHP 8.3.6 (cli) (built: Dec  2 2024 12:36:18) (NTS)
>
>Typecho 1.2.1