**预览地址：** http://www.jsnav.top
## 文件目录：    
```
├── index.js
├── package.json
├── .gitignore
├── models
|    |—— users.js
|    |—— posts.js
|    |—— comments.js
|—— pubilc
|    |—— css
|        |—— style.css
|    |—— img
|    |—— js
├── routes
|    ├── index.js
|    ├── posts.js
|    |—— comments.js
|    ├── signin.js
|    ├── signout.js
|    |—— signup.js
|—— config
|    |—— default.js
|—— lib
|    |—— mongo.js
|—— middlewares
|    |—— check.js
|—— logs
|    |—— error.log
|    |—— success.log
|—— views
|    |—— edit.ejs
|    |—— post.ejs
|    |—— signin.ejs
|    |—— create.ejs
|    |—— header.ejs
|    |—— footer.ejs
|    |—— signup.ejs
|    |—— posts.ejs
|    |—— 404.ejs
|    |—— component
|        |—— nav.ejs
|        |—— nav-setting.ejs
|        |—— notification.ejs
|        |—— post-content.ejs 
|        |—— comments.ejs
```

> 我们遵循了 MVC（模型(model)－视图(view)－控制器(controller/route)） 的开发模式。


## 功能：
- [x] 登陆
- [x] 注册
- [x] 登出
- [x] 上传头像
- [x] 发表文章
- [x] 修改文章
- [x] 留言
- [x] 评论
- [ ] 分页
- [ ] 标签
- [ ] 二级评论
- [ ] Nginx反向代理
- [ ] MongoDB加上用户和密码
## 部分截图

![注册](https://upload-images.jianshu.io/upload_images/7072486-7787bcb581462345.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



![博客首页](https://upload-images.jianshu.io/upload_images/7072486-f9f4772401d2478e.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![博客文章页](https://upload-images.jianshu.io/upload_images/7072486-27ca74745716ea65.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![博客发表页](https://upload-images.jianshu.io/upload_images/7072486-5288494cec50122a.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



## Error log
- 出了Bug，仔细看Error log.
- 注册是图片必须上传(要放在public/img下)，否则会报错 `Callback must be a function`。
- 仔细阅读教程，可以减少很多低级错误。
- 删除功能有bug，待解决。


## 使用 pm2 
> pm2 是 Node.js 下的生产环境进程管理工具，就是我们常说的进程守护工具。

下载pm2 
```
npm install pm2 -g
```
修改 package.json，添加 start 的命令：
```
package.json

"scripts": {
  "test": "istanbul cover _mocha",
  "start": "cross-env NODE_ENV=production pm2 start index.js --name 'myblog'"
}
```
然后运行 npm start 通过 pm2 启动程序，如下图所示 ：
![](https://github.com/nswbmw/N-blog/raw/master/book/img/4.15.1.png)

也可直接运行：
```
NODE_ENV=production pm2 start index.js --name 'myblog'
```
pm2 常用命令:
```
pm2 start/stop: 启动/停止程序
pm2 reload/restart [id|name]: 重启程序
pm2 logs [id|name]: 查看日志
pm2 l/list: 列出程序列表
```


启动项目：
```
npm install

npm install pm2 -g

npm start
```

---
目标是做成一个模板网站：http://www.zhenshigushi.net    

在此鸣谢作者提供的教程：[nswbmw/N-blog](https://github.com/nswbmw)    
服务器部署参考：https://biaochenxuying.cn/articleDetail?article_id=5bfa728bb54f044b4f9da240
