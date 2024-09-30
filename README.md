仅供本人工作学习使用,他人请勿使用和传播.

1
1
1

部署方法一
使用 Cloudflare平台pages的Git功能导入GitHub仓库快捷部署订阅节点
项目本地化部署不使用订阅器、节点转换等第三方外链引用 无需担心节点订阅被白嫖
准备材料:
注册GitHub
https://github.com/

下载GitHub app  可下可不下 可做验证用 省去验证码环节
 https://play.google.com/store/apps/details?id=com.github.android

注册cloudflare
https://www.cloudflare.com/zh-cn/

获取uuid 
https://www.uuidgenerator.net/

1 Github   [复制/Fork/分支/分叉]  仓库名 CF-  

2 Cloudflare workers和pages 里 点创建 Pages 选连接到Git，添加帐户GitHub 帐户 登录  

选中[复制/Fork/分支/分叉]仓库名CF-  点击 开始设置.

设置构建和部署页面下方，选择 环境变量（高级）后并 添加变量 变量名称填写UUID，值则为你的UUID，后点击 保存并部署即可。

2
2
2

部署方式二
使用 Cloudflare平台pages 导入Github 仓库中的 _worker.zip 压缩包或 _worker.zip 文件夹 快捷部署订阅节点


准备材料:
注册GitHub
https://github.com/

下载GitHub app  可下可不下 可做验证用 省去验证码环节
 https://play.google.com/store/apps/details?id=com.github.android

注册cloudflare
https://www.cloudflare.com/zh-cn/

获取uuid 
https://www.uuidgenerator.net/

Github  直接下载 仓库名 CF-
_worker.zip 压缩包
或
 _worker.zip 文件夹


1 Github  直接下载仓库中的 _worker.zip 压缩包 或_worker.zip 文件夹 或 [复制/Fork/分支/分叉]  仓库名 CF- 后 下载 

2 Cloudflare workers和pages 里 点创建 Pages 

在 Cloudflare Pages 控制台中选择 

点上传资产，

为你的项目取名，

点击 创建项目，

然后上传你下载好的 _worker.zip 压缩包 或_worker.zip 文件夹

点击 部署站点。

部署完成后点击 继续处理站点，

选择  设置 ，点变量和机密，制作，下方 变量和机密 {为项目定义文本、机密或构建变量，定义变量 }  后面点 添加环境变量。

变量名称 填写 UUID ，

值 填写 你生成的 UUID，并复制保存 UUID留用

点击 保存。

然后 点设置那行 最左边的 部署，

在页面 右边中部  点击 创建新部署 ，

重新上传  _worker.zip 压缩包 或_worker.zip 文件夹

点击 保存并部署 即可。

成功！

您的站点已构建并部署到：复制 https://你的项目名.pages.dev 加上 /你的uuid     获取 你的部署信息

3
3
3

部署方式三   

  使用 Cloudflare平台 Worker 快捷部署订阅节点   
准备材料:

注册GitHub
https://github.com/

下载GitHub app  可下可不下 可做验证用 省去验证码环节
 https://play.google.com/store/apps/details?id=com.github.android

注册cloudflare
https://www.cloudflare.com/zh-cn/

获取uuid 
https://www.uuidgenerator.net/


Github  仓库名 CF-  里 直接下载  _worker.js 文件



在 Cloudflare Workers 和 Pages 控制台中 创建Worker。

并起一个短点的英文名 后点部署

右上 点 编辑代码

进入后删除里面原有的代码 一共16行全删除

接着 打开 worker.js 文件 复制里面的全部 内容  [ _worker.js 文件 打开方式 选 记事本 或 其它 文本编辑 即可]  粘贴到  Worker 编辑器中。

ctrl+c 复制  ctrl+v粘贴

然后点 页面中上部分的  { 活动 最新}  应用 保存   在点一下右上角的 部署 即可

将第 7 行 userID 修改成你生成的 UUID   并复制保存 UUID留用

然后点 页面中上部分的  { 活动 最新}右边有个预览  在里面的链接尾部后面 加上你的 uuid 即可获取  部署信息



https://你的项目名.pages.dev 加上 /你的uuid     获取 你的部署信息

4
4
4
4444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444
相关设置四
cloudflare部署Workers和部署Pages的相关设置
部署Workers和部署Pages的相关设置 ~~~~~~~
部署Workers：支持vless+ws+tls  vless+ws  代理节点 ~~~~~
部署Pages：支持vless+ws+tls  ~~~~~
cloudflare Vless  的单节点支持 path路径 自定义三类  proxy ip（IPV4形式、IPV6形式、域名形式） ~~~~~~~~~~~
支持单节点、聚合通用节点订阅、sing-box节点订阅、clash 节点订阅.~~~~~~~~~~
0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
Cloudflare节点可自定义内容
方式一：
可修改Vless_workers_pages文件下的_worker.js文件

1、自定义  UUID 在（第7行）

2、如果无法访问cloudflare类网站或者ChatGPT网页版，说明 代理ip Proxy IP 失效，可更换 Proxy IP，自定义 在（第9行）

3、订阅节点的优选IP（第13-27行）与端口（第30-44行），优选IP与端口两者变量编号须对应

4、伪装网页默认留空，显示为本地IP信息代码界面，可自定义（第10行），为避免风险建议默认留空

111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
方式二：可在cloudflare-workers或pages 部署页面 中的设置里 使用 环境变量
注：变量设置结果将覆盖本地修改结果

变量作用  变量名称  变量值要求  变量默认值
1、uuid  uuid  符合 uuid规定格式  uuid：A08A6646-98B0-44AF-A75C-8C1F7F68D2D1
2、能上cloudflare类网站 proxy ip  ipv4地址、域名、[ipv6地址]  proxy ip域名：代码第9行 自建白嫖
3、订阅节点 优选IP  ip1到ip13  CF官方IP、CF反代IP、CF优选域名  cloudflare 官方不同地区的 visa 域名
4、优选IP对应端口  pt1到pt13  CF13个 标准端口、反代IP对应任意端口 cloudflare 13个标准端口

2222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222222
cloudflare Vless 的单节点支持 path 路径自定义代理ip  proxy ip
支持IPV4、[ipv6地址]、域名  三种方式
可在客户端app上的path设置处直接修改：/pyip=IPV4地址 ;/pyip=[IPV6地址] ;/pyip=域名
注意：仅影响当前客户端正在设置的单节点，并不影响其他单节点或者订阅节点的 proxy ip

333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333333
获取部署好的订阅节点信息~~~
cloudflare Vless：在网页地址栏输入 https:// workers域名 或者 pages域名 或者 自定义域名 /自定义uuid
例如
https://youzai.56789.workers.dev/ 你的uuid123456789
https://youzai.56789.pages.dev/ 你的uuid123456789
注意：使用自定域时，原先workers域名 或者 pages域名下的配置信息与分享链接依旧可用
444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444444

优选IP应用
默认CF官方不同地区的visa域名（IP落地地区美国）
推荐好记的懒人专属CF官方IP如下（IP落地地区都为美国，支持13个标准端口切换）

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

2606：4700：： 需IPV6环境~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
通过配置变量修改，可使用他人分享的IP或者域名，也可以自行本地优选
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

启用分片(Fragment)功能的好处：无视域名被墙TLS阻断，从而让workers等被墙的域名支持TLS节点
提示：未被墙TLS阻断的自定义域名或pages域名无需开启分片就可使用TLS节点
注意：其他平台客户端未开启分片功能情况下，workers域的6个443系TLS节点是不可用的

目前支持该功能的平台客户端如下

1、安卓Android：v2rayNG、Nekobox、Karing

2、电脑Windows：v2rayN、Hiddify、Karing

3、苹果ios：Karing、Shadowrocket

4、订阅 建议使用  手机 猫M 和 电脑猫V 


1：CF-workers-vless+ws节点
节点特色：关闭了TLS加密，无视域名阻断
客户端参数如下：
客户端地址(address)：自定义的域名 或者 优选域名 或者 优选IP 或者 反代IP
端口(port)：7个http端口可任意选择(80、8080、8880、2052、2082、2086、2095)，或反代IP对应端口
用户ID(uuid)：A08A6646-98B0-44AF-A75C-8C1F7F68D2D1
传输协议(network)：ws 或者 websocket
伪装域名(host)：lingering-unit-a148.youzai56789.workers.dev
路径(path)：/?ed=2560
传输安全(TLS)：关闭


2：CF-workers-vless+ws+tls节点
节点特色：
客户端参数如下：
客户端地址(address)：自定义的域名 或者 优选域名 或者 优选IP 或者 反代IP
端口(port)：6个https端口可任意选择(443、8443、2053、2083、2087、2096)，或反代IP对应端口
用户ID(uuid)：A08A6646-98B0-44AF-A75C-8C1F7F68D2D1
传输协议(network)：ws 或者 websocket
伪装域名(host)：lingering-unit-a148.youzai56789.workers.dev
路径(path)：/?ed=2560
传输安全(TLS)：开启
跳过证书验证(allowlnsecure)：false

3：聚合通用、Clash-meta、Sing-box
注意：
1、默认每个订阅链接包含TLS+非TLS共13个端口节点
2、当前workers域名作为订阅链接，需通过代理进行订阅更新
3、如使用的客户端不支持分片功能，则TLS节点不可用
