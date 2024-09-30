仅供本人工作学习使用,他人请勿使用和传播.
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
2 Cloudflare workers和pages 里 创建 Pages 选连接到Git，添加帐户GitHub 帐户 登录  
选中[复制/Fork/分支/分叉]仓库名CF-  点击 开始设置.
设置构建和部署页面下方，选择 环境变量（高级）后并 添加变量 变量名称填写UUID，值则为你的UUID，后点击 保存并部署即可。
