# nuxt学习项目 nuxt-vue-mastery

## 项目介绍
这个项目是我学习nuxt时候练习的一个小项目，跟着视频做的一个项目。通过这个项目我初步认识了nuxt的使用方法，这个教程视频也非常适合入门nuxt。后台接口当前使用的是y-json-server.typicode.com上的在线地址,如果这个在线地址不能用了可以使用json-server开启本地服务，根目录中的`db.json`是接口的数据。
## 学习收获
 - 创建nuxt项目
 - Nuxt中的router的使用方法
 - 如何配置SEO
 - 在nuxt中使用axios
 - 在nuxt中使用vuex
 - 本地服务json-server的使用
## 学习资料
* 学习视频：https://www.bilibili.com/video/BV1NX4y1N7tJ?p=1
## 项目启动
* yarn install 安装依赖
* yarn dev 启动本地开发环境
* >  如果在线的api地址不可用可以下载json-server启用本地服务
  *  npm install -g json-server
  *  在根目录运行json-server --watch db.json

## 目录介绍
介绍几个重点文件，nuxt模板中自带的一些文件就不介绍了
* layouts/default.vue 默认布局
* layouts/error.vue 错误页面（404）
* components/NavBar.vue   头部导航组件
* components/EventCard.vue 首页列表里面的每一个item组件
* pages/events/_id.vue 详情页面
* services/EventService.js Api接口配置
* store/events.js 修改state状态的vuex模块
