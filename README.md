# resumer

一个改进后的基于vue.js框架的在线简历编辑器
改进部分包括：
 * 数据的双向绑定改为单向绑定
 * 原设计[预览地址](https://wangjit.github.io/vue-resumer-1/dist/)（[代码地址](https://github.com/wangjit/vue-resumer-1)）中，简历预览区的数据直接从简历编辑区获取，改进后改为用vuex管理数据
 * 完善了注册和登陆功能，用户的账户及密码使用LeanCloud存储 
 * 利用localStorage对用户未及时保存的简历编辑信息进行本地缓存

**体验地址**
[点我预览](https://wangjit.github.io/vue-resumer/dist/#/)

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run all tests
npm test
```


