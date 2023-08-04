## 1.准备一台香港或者国外的服务器



## 2.安装宝塔

```shell
wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && sudo bash install.sh ed8484bec
```

## 3.配置解析域名

`去自己的域名产商配置`

## 4.宝塔安装nginx并且创建站点

![](images\QQ截图20230423200929.png)

## 5.配置SSL证书

![](images\QQ截图20230423203941.png)

![](images\QQ截图20230423204112.png)

## 6.安装XUI 

git地址 https://github.com/vaxilu/x-ui

```shell
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```

![](images\QQ截图20230423204611.png)

## 7.nginx配置解析

![](images\QQ截图20230423204810.png)

```shell
 location ^~ / {         #XUI登录目录
        proxy_pass http://127.0.0.1:32458;    #XUI登录目录+端口
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
  location /proxy {      #   VPN路径
        proxy_redirect off;
        proxy_pass http://127.0.0.1:32459;     #VPN端口
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $http_host;
        proxy_read_timeout 300s;
        # Show realip in v2ray access.log
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
```



![](images\QQ截图20230423205357.png)

## 8.浏览器访问域名

![](images\QQ截图20230423205515.png)

![](images\QQ截图20230423205829.png)

## 9.电脑版本下载v2rayN  , 手机版本下载Shadowrocket

[https://github.com/2dust/v2rayN/releases](https://github.com/2dust/v2rayN/releases)



![](images\QQ截图20230423210150.png)



ctrl+v粘贴到v2rayN

![](images\QQ截图20230423210322.png)





![](images\QQ截图20230423210417.png)

![](images\QQ截图20230423210507.png)





![](images\QQ截图20230423210548.png)

## 10.访问YouTube

![](images\QQ截图20230423210757.png)

## 11.手机连接



![](images\QQ截图20230423210920.png)



![](images\QQ截图20230423211234.png)



![](images\QQ截图20230423211337.png)



## 12.推荐安装最新内测版本，就不需要这么麻烦了，

https://github.com/FranzKafkaYu/x-ui

```shell
bash <(curl -Ls https://raw.githubusercontent.com/FranzKafkaYu/x-ui/master/install.sh)
```

![](images\QQ截图20230605105042.png)

![](images\QQ图片20230605105309.png)

