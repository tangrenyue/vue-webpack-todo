# vue-webpack-todo
![展示](https://github.com/tangrenyue/vue-webpack-todo/blob/master/mytodo.png)

学习自imooc的Jokcy老师的课程 [Vue+Webpack打造todo应用](https://www.imooc.com/learn/935)

前端的价值
1、搭建前端工程
2、网络优化（HTTP）
3、API定制
4、node.js层

初始化一个项目
npm init

安装
npm i webpack vue vue-loader
npm i css-loader vue-template-compiler

静态资源的加载
webpack对其他类型的文件处理,可在配置文件中配置rules规则，同样根据配置中的处理的loader都要安装.
npm i style-loader url-loader file-loader
stylus的css预处理器 npm i stylus-loader stylus

webpack-dev-server的配置
npm i webpack-dev-server
配置："dev": "webpack-dev-server --config webpack.config.js"
配置后，使用命令npm run dev也能够实现打包项目，并且是开发环境模式

由于一个配置文件,需要一个环境变量NODE_ENV判断,来判断是开发环境还是生产环境,在linux下直接NODE_ENV=production,在windows环境下 需要set NODE_ENV=production,解决这种跨平台设置的差异性,我们可以安装cross-env
npm i cross-env
    "build": "cross-env NODE_ENV=production webpack --config webpack.config.js",
    "dev": "cross-env NODE_ENV=development webpack-dev-server --config webpack.config.js"

引入html-webpack-plugin,用于让打包好的js文件自动包含到HTML文件中
npm i html-webpack-plugin

新建postcss和babel的配置文件 并配置这两个文件
PostCss会对CSS代码进行优化,主要是解决不同浏览器识别码的问题
npm i post i postcss-loader autoprefixer babel-loader babel-core
babel转换vue中的jsx代码
npm i babel-preset-env babel-plugin-transform-vue-jsx
npm i babel-helper-vue-jsx-merge-props babel-plugin-syntax-jsx
