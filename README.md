# myblog
刚学完了vue和node.js，所以就想简单做一个博客看看掌握了多少知识！！！

问题描述
使用build打包部署后在浏览器按F12，点击Sources后可以看到webpack://的目录，里面包含了项目的所有源码
问题产生原因
在vue-cli3之后原本的配置文件变为了可选的了，并且默认打包后可以通过map文件看到源码以方便调试。
解决方法
有两种解决方法：
在项目根目录下增加vue.config.js文件，在其中进行配置
module.exports = {
  productionSourceMap: true
}
1
2
3
在package.json中增加vue属性，在其值中进行配置
{
  "name": "test",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",
  "dependencies": {
  },
  "vue": {
    "productionSourceMap": false
  }
}
