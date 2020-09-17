# mall-vue
> 高仿小米商城

## 1 vue cil4脚手架

如已安装低版本，需要先卸载

```
vue --version
npm uninstall -g vue-cli
npm install -g @vue/cli
```

初始化项目：
```
vue create name
```

## 知识点
### 使用代理解决跨域问题
```
   devServer: {
        host: 'localhost',
        port: 8080,
        proxy: {
            '/api': {
                target: 'http://mall-pre.springboot.cn',
                changeOrigin: true,
                pathRewrite: {
                    '/api': ''
                }
            }
        }
    }
```
### 需求梳理
- 熟悉文档、查看原型、读懂需求
- 了解前端设计稿-设置前端业务架构
- 了解后端接口文档-定制相关对接规范
- 协调资源
- 搭建前端架构


### npm install

```
npm i vue-lazyload element-ui node-saas sass-loader vue-awesome-swiper vue-axios vue-cookie --save-dev 
```
```
npm set sass_binary_site=https://npm.taobao.org/mirrors/node-sass/
npm set registry=https://registry.npm.taobao.org
```

### 接口错误拦截



## 静态部署
###  build之后index.html如何本地访问
新建文件`vue.config.js`
```
module.exports = {
    publicPath: './',
}
```

### 部署到GitHub Pages
> 原理就是建个分支，把build出的dist下的静态文件放到分支上，然后设置到xxxx.github.io/ 下

1.安装gh-pages
```
sudo npm install gh-pages --save-dev
```

2.修改package.json

```
      "predeploy": "npm run build",
      "deploy": "gh-pages -d dist"
```

3.执行
```
npm run deploy
```
