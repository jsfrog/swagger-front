# framework-doc-front

## 简介
基于knife4j-vue 二次开发的项目，源项目地址https://gitee.com/xiaoym/knife4j/tree/master/knife4j-vue。。

## 改动点
|  文件   | 改动前  |  改动后 |说明
|  ----  | ----  |----| ----|
|   vue.config.js |  publicPath: ".." |  publicPath: "/framework/doc/" | 资源目录 |
|   vue.config.js |  target |  本地开发可以指定到服务的地址 build的时候注释掉就行 | 接口的域名 |
|   BasicLayout.vue |  create{ this.initSpringDocOpenApi();} |  create{ this.initKnife4jFront();} | 改为front模式 |
|   BasicLayout.vue | initKnife4jFront |  函数前面增加了var i18nParams=this.getI18nFromUrl();var tmpI18n=i18nParams.i18n; | 解决bug |
|   BasicLayout.vue |  selectDefaultMenu else{this.openKeys = [m.key];} |  selectDefaultMenu else (m != undefined && m != null){this.openKeys = [m.key];} | 解决bug |
|   BasicLayout.vue |  initKnife4jFront |  url的值为/framework/swagger-resources | 指定url |
|   Knife4jAsync.js |  analysisApi  |  注释掉了if(!that.springdoc)... | 请求接口会带上当前页面的地址 |
## 需要服务提供的