# DouYu Web

[![License](https://img.shields.io/badge/license-Apache%20License%202.0-blue)](./LICENSE)

## Notice

因为 `斗鱼礼物服务器` 限定了 `www.douyu.com` 域名。

只能使用 `nginx` 反代做一层代理屏蔽跨域问题。

**原域名为 `gift.douyucdn.cn`，现在为 `giftdouyucdn.starudream.cn`**

下面是相关 `nginx` 配置。

```conf
server {
  listen 80;
  listen [::]:80;
  server_name giftdouyucdn.starudream.cn;
  location / {
    proxy_pass https://gift.douyucdn.cn;
    proxy_hide_header Access-Control-Allow-Origin;
    add_header Access-Control-Allow-Origin *;
  }
}
```

## License

[Apache License 2.0](./LICENSE)