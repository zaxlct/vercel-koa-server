# vercel-koa-server
免费部署到 vercel 教程

## 在 vercel 上创建项目
1. 注册 vercel 账号，最好用使用 GitHub 账号注册，可以直接导入 GitHub 上仓库
2. 在首页点击 add new project
3. Import Git Repository ，导入项目，你可以 Fork 此项目到你的 GitHub 下，就能直接导入了

## 设置部署步骤和环境变量
如图：
![部署步骤](http://vote-img.sutot.cn/vercel-koa-server-config2.png)
部署步骤就两步： `npm install` 和 `npm run build`
环境变量有三个：
1. PORT 端口
2. OPENAI_URL，请求 open api 的地址，正常是 https://api.openai.com，但是最好别填这个，GitHub 上找个代理，比如 https://github.com/x-dr/chatgptProxyAPI
3. OPENAI_API_KEY

设置完就自动部署了，代码如果更新到 GitHub master 分支也会自动部署

## 关闭接口限制
![部署步骤](http://vote-img.sutot.cn/vercel-koa-server-config.jpg)
如果不关闭此选项，koa 实现的 api 是不对外暴露的，只能是项目里的前端能访问，如果你不需要对外暴露，未来在此项目中继续添加前端代码，可打开

## 测试
部署成功后，会随机给你分配几个 Domains，我们复制第一个，假设为 https://vercel-xxx-xxx.vercel.app/
那么直接在浏览器上请求 `https://vercel-xxx-xxx.vercel.app/hello?what=test`，会返回`{"message":"Hello test"}`

别忘了用 postman 试一下，postman 走通了才是真的通了
