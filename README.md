仅供本人工作学习使用,他人请勿使用和传播.



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





部署方式三
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

使用 Cloudflare平台 Worker 快捷部署订阅节点
在 Cloudflare Workers 和 Pages 控制台中 创建Worker。
并起一个短点的英文名 后点部署
右上 点 编辑代码
进入后删除里面原有的代码 一共16行全删除
接着 打开 worker.js 文件 复制里面的全部 内容  [ _worker.js 文件 打开方式 选 记事本 或 其它 文本编辑 即可]  粘贴到  Worker 编辑器中。
ctrl+c 复制  ctrl+v粘贴
将第 7 行 userID 修改成你生成的 UUID   并复制保存 UUID留用

然后点 页面中上部分的  { 活动 最新}  应用 保存   在点一下右上角的 部署 即可

然后点 页面中上部分的  { 活动 最新}右边有个预览  在里面的链接尾部后面 加上你的 uuid 即可获取  部署信息


 https://你的项目名.pages.dev 加上 /你的uuid     获取 你的部署信息





 
