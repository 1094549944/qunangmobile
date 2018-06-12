# qunangmobile
移动端项目
# qunang

> A Vue.js project

## Build Setup

```bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

# 多页面和单页面应用

多页面：页面跳转：服务器返回 html
每次请求一个页面，服务器都会返回一个新的 html 文件。

优点： 首屏时间快，seo 效果好。缺点：页面切换慢

单页应用：页面跳转：js 渲染优点：页面切换快缺点：首屏时间稍慢，seo 差通过服务器渲染，来解决单页面缺点。

## 解决移动端 300ms 延时的问题，使用 fastclick 这个库

npm install fastclick --save

## 使用 iconfont 字体

## 使用 stylus

npm install stylus --save
npm install stylus-loader --save
或者写成：npm install stylus stylus-loader --save

## 轮播图使用 vue-awesome-swiper

npm install vue-awesome-swiper@2.6.7 --save

## 使用 axios

npm install axios --save


## 使用better-scroll

是iscroll的封装

npm install better-scroll --save


## 使用vuex来管理状态级

## 解决部分机型打开白屏的问题，一个原因是，无法识别promise,另一个原因是webpack-dev-server 的问题。解决：打包，然后到测试或者正式服务器上
npm install babel-polyfill --save

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

