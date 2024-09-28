# 即将更新！！！！

# Cloudflare-workers/pages代理脚本
### 本项目仅支持本地化部署，不使用订阅器、节点转换等第三方外链引用，无需担心节点订阅被外链作者查看
--------------------------------
## 脚本特色：
### 懒人小白专用！默认节点都为CF官方IP，无需频繁更新订阅获取客户端优选IP
#### Workers方式：支持vless+ws+tls、trojan+ws+tls、vless+ws、trojan+ws代理节点
#### Pages方式：支持vless+ws+tls、trojan+ws+tls代理节点
#### CF Vless/Trojan的单节点支持path路径自定义三类proxyip（IPV4形式、IPV6形式、域名形式）
#### 支持单节点链接、聚合通用节点订阅、sing-box节点订阅、clash节点订阅

--------------------------------

## 一：CF Vless节点可自定义内容

#### 方式一（推荐）：可修改Vless_workers_pages文件下的_worker.js文件

1、UUID必须自定义（第7行）

2、如果无法访问CF类网站或者ChatGPT网页版，说明ProxyIP失效，可更换ProxyIP，自定义（第9行）

3、订阅节点的优选IP（第13-27行）与端口（第30-44行），优选IP与端口两者变量编号须对应

4、伪装网页默认留空，显示为本地IP信息代码界面，可自定义（第10行），为避免风险建议默认留空

#### 方式二：也可在CF-workers/pages界面中使用变量设置
注：变量设置结果将覆盖本地修改结果
| 变量作用 | 变量名称| 变量值要求| 变量默认值|
| :--- | :--- | :--- | :--- |
| 1、必要的uuid | uuid |符合uuid规定格式 |万人骑uuid：77a571fb-4fd2-4b37-8596-1b7d9728bb5c|
| 2、能上CF类网站 | proxyip |ipv4地址、域名、[ipv6地址]|proxyip域名：代码第9行|
| 3、订阅节点优选IP | ip1到ip13 |CF官方IP、CF反代IP、CF优选域名| CF官方不同地区的visa域名|
| 4、优选IP对应端口 | pt1到pt13 |CF13个标准端口、反代IP对应任意端口| CF13个标准端口|

---------------------------------

## 二：CF Trojan节点可自定义内容

#### 方式一（推荐）：可修改Trojan_workers_pages文件下的_worker.js文件

1、密码必须自定义（第4行）

2、如果无法访问CF类网站或者ChatGPT网页版，说明ProxyIP失效，可更换ProxyIP，自定义（第5行）

3、订阅节点的优选IP（第9-23行）与端口（第26-40行），优选IP与端口两者变量编号须对应

4、伪装网页默认留空，显示为本地IP信息代码界面，可自定义（第6行），为避免风险建议默认留空

#### 方式二：也可在CF-workers/pages界面中使用变量设置
注：变量设置结果将覆盖本地修改结果，每更新变量需要重新上传一次原始pages文件
| 变量作用 | 变量名称| 变量值要求| 变量默认值|
| :--- | :--- | :--- | :--- |
| 1、必要的密码 | pswd |任意字符号 |万人骑密码：trojan|
| 2、能上CF类网站 | proxyip |ipv4地址、域名、[ipv6地址]|proxyip域名：代码第5行|
| 3、订阅节点优选IP | ip1到ip13 |CF官方IP、CF反代IP、CF优选域名| CF官方不同地区的visa域名|
| 4、优选IP对应端口 | pt1到pt13 |CF13个标准端口、反代IP对应任意端口| CF13个标准端口|

---------------------------------
## 三：CF Vless/trojan的单节点支持path路径自定义proxyip

支持IPV4、IPV6(需中括号)、域名三种方式

可在客户端上的path设置处直接修改：/pyip=IPV4地址  ；  /pyip=[IPV6地址]  ；  /pyip=域名

注意：仅影响当前客户端正在设置的单节点，并不影响其他单节点或者订阅节点的proxyip

---------------------------------

## 四：查看配置信息与分享链接

CF Vless：在网页地址栏输入 https:// workers域名 或者 pages域名 或者 自定义域名 /自定义uuid

CF Trojan：在网页地址栏输入 https:// workers域名 或者 pages域名 或者 自定义域名 /自定义密码

注意：使用自定域时，原先workers域名 或者 pages域名下的配置信息与分享链接依旧可用

---------------------------------

## 五：优选IP应用

如果你没有天天最高速度或者选择国家的需求，使用默认的CF官方不同地区的visa域名即可（IP落地地区都为美国）

推荐好记的懒人专属CF官方IP如下（IP落地地区都为美国，支持13个标准端口切换），称之为"冲在最前的不死IP"

104.16.0.0 

104.17.0.0 

104.18.0.0 

104.19.0.0 

104.20.0.0 

104.21.0.0 

104.22.0.0 

104.24.0.0 

104.25.0.0 

104.26.0.0 

104.27.0.0 

172.66.0.0

172.67.0.0

162.159.0.0

2606:4700:: 需IPV6环境

通过配置变量修改，可使用他人分享的IP或者域名，也可以自行本地优选，相关优选应用与脚本可参考视频教程

注意：多个CF节点在客户端使用负载均衡或者自动选择时，建议所有应用的节点都为同一个国家地区，以避免不同国家之间的IP乱跳现象

---------------------------------
## 六：无需socks5！小白利用reality协议一键自制proxyip、80系/443系的任意端口反代IP

### 推荐使用 离中国近、便宜、流量多的纯IPV6的vps进行搭建。近可能避免使用IPV4，因为IPV4大概率被大佬们偷扫反代IP，成为他们的公益或收费反代IP库。如果非要用IPV4，请时常关注下自己VPS的流量，使用proxyip与客户端优选IP都会消耗VPS流量

### 可现实以下四种情况：

可选择现实1：仅用于客户端优选IP，即CF节点访问非CF网站的落地IP地区与VPS地区一致，访问CF网站落地IP地区根据proxyip决定

可选择现实2：仅用于proxyip，即CF节点访问CF网站的落地IP地区与VPS地区一致，访问非CF网站落地IP地区根据客户端优选IP决定

可选择现实3：同时用于客户端优选IP与proxyip，即CF节点访问CF网站的落地IP地区、访问非CF网站落地IP地区，两者都与VPS地区一致（仅支持443端口的TLS节点）

可选择现实4：通过在VPS安装WARP全局双栈V4+V6功能，即访问非CF网站的客户端优选IP的落地IP（104.28……/2a09:……）现实固定，或访问CF网站的proxyip的落地IP（104.28……/2a09:……）现实WARP解锁功能效果

搭建proxyip与反代ip的脚本推荐：[x-ui-yg脚本](https://github.com/yonggekkk/x-ui-yg)、[sing-box-yg脚本](https://github.com/yonggekkk/sing-box_hysteria2_tuic_argo_reality)

相关操作请看[视频教程](https://youtu.be/QOnMVULADko)

---------------------------------
## 七：客户端推荐

#### 启用分片(Fragment)功能的好处：无视域名被墙TLS阻断，从而让workers等被墙的域名支持TLS节点
#### 提示：未被墙TLS阻断的自定义域名或pages域名无需开启分片就可使用TLS节点
 
目前支持该功能的平台客户端如下（点击名称即跳转到官方下载地址）

1、安卓Android：[v2rayNG](https://github.com/2dust/v2rayNG/tags)、[Nekobox](https://github.com/maskedeken/NekoBoxForAndroid/tags)、[Karing](https://github.com/KaringX/karing/tags)、v2box

2、电脑Windows：[v2rayN](https://github.com/2dust/v2rayN/tags)、[Hiddify](https://github.com/hiddify/hiddify-next/tags)、[Karing](https://github.com/KaringX/karing/tags)

3、苹果Ios：Karing、Shadowrocket(小火箭)、Streisand、v2box

4、软路由Openwrt：[homeproxy](https://github.com/kiddin9/openwrt-packages)

注意：其他平台客户端未开启分片功能情况下，workers域的6个443系TLS节点是不可用的

注意：Shadowrocket(小火箭)、v2box、v2rayn、v2rayng客户端对trojan+ws有强制开启TLS问题，造成trojan+ws不通。且clash订阅没有trojan+ws节点。特此说明

---------------------------------

### 相关说明及注意点请查看[甬哥博客](https://ygkkk.blogspot.com/2023/07/cfworkers-vless.html)

### 视频教程：

[CF workers永久免费vless节点搭建教程（一）：全网首发演示跳IP现象，解密两大节点使用技巧，优选IP、优选域名的优缺点说明](https://youtu.be/9V9CQxmfwoA)

[CF workers永久免费vless节点搭建教程（二）：优选反代IP一键脚本发布，pages部署教程，多平台客户端设置说明，独家探讨CF免费代理敏感安全问题](https://youtu.be/McdRoLZeTqg)

[CF workers永久免费Trojan节点搭建教程（三）：无需自定义域名，workers与pages两方案部署优选IP节点；CF Trojan与CF Vless对比总结；如何看待Trojan被识别](https://youtu.be/lmhhL8M1k0I)

强烈推荐：[CF vless/trojan永久免费节点教程（四）：解读优选官方IP、优选反代IP、优选域名三者的关系与特点；ProxyIP存在的意义](https://youtu.be/NaLd-orwFUE)

强烈推荐：[CF vless/trojan永久免费节点教程（五）：不用自定义域名？不用频繁优选IP？不用订阅器？总结CF节点与域名的结构关系图](https://youtu.be/8s-ELRuFaeE)

强烈推荐：[CF vless/trojan永久免费节点教程（六）：节点不能用，问题出在哪？多平台免费客户端设置指南及避坑说明](https://youtu.be/8E0l0nQWLxs)

最新推荐：[CF vless/trojan永久免费节点最终教程（七）：全网独家演示真正的"固定IP"，解决twitch、chatgpt客户端报错问题；一键自制反代IP与ProxyIP；揭秘你被他人偷扫IP的风险](https://youtu.be/QOnMVULADko)

[直播精选回顾：CF workers vless免费节点四大特点，节点被断流阻断问题](https://youtu.be/9OHGpWlfdJ0)

[ClouDNS永久免费域名最终教程：CF pages vless自定义域名直接部署](https://youtu.be/PN0BLANXh4I)

---------------------------------
---------------------------------
---------------------------------
---------------------------------
## 优选域名、优选官方IP+反代IP一键脚本（在本地网络环境下利用termux或者ish运行）：

### CF-CDN优选公共大厂域名脚本，苹果安卓手机平板专用：
```
curl -sSL https://gitlab.com/rwkgyg/CFwarp/raw/main/point/CFcdnym.sh -o CFcdnym.sh && chmod +x CFcdnym.sh && bash CFcdnym.sh
```
------------------------------------------------------------------------
### CF-优选官方IP+反代IP二合一脚本，苹果安卓手机平板专用：
```
curl -sSL https://gitlab.com/rwkgyg/CFwarp/raw/main/point/cfip.sh -o cfip.sh && chmod +x cfip.sh && bash cfip.sh
```

-------------------------------------------------------------

### 交流平台：[甬哥博客地址](https://ygkkk.blogspot.com)、[甬哥YouTube频道](https://www.youtube.com/@ygkkk)、[甬哥TG电报群组](https://t.me/+jZHc6-A-1QQ5ZGVl)、[甬哥TG电报频道](https://t.me/+DkC9ZZUgEFQzMTZl)

-------------------------------------------------------------
### 感谢你右上角的star🌟
[![Stargazers over time](https://starchart.cc/yonggekkk/Cloudflare-workers-pages-vless.svg)](https://starchart.cc/yonggekkk/Cloudflare-workers-pages-vless)
------------------------------------------------------------------------
### 代码来源：[ca110us](https://github.com/ca110us/epeius)、[emn178](https://github.com/emn178/js-sha256/blob/master/src/sha256.js)、[3Kmfi6HP](https://github.com/3Kmfi6HP/EDtunnel)、[badafans](https://github.com/badafans/Cloudflare-IP-SpeedTest)、[XIU2](https://github.com/XIU2/CloudflareSpeedTest)

### 声明：所有代码来源于Github社区，并通过ChatGPT进行整合
