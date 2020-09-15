# mall-vue
> 高仿小米商城

## 1 vue cil脚手架

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





###  build之后index.html如何本地访问
新建文件`vue.config.js`
```
module.exports = {
    publicPath: './',
}
```

## 部署到GitHub Pages
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