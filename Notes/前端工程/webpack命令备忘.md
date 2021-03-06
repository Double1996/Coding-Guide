<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [安装webpack](#%E5%AE%89%E8%A3%85webpack)
- [在项目中使用webpack](#%E5%9C%A8%E9%A1%B9%E7%9B%AE%E4%B8%AD%E4%BD%BF%E7%94%A8webpack)
- [利于分析 webpack 打包的命令](#%E5%88%A9%E4%BA%8E%E5%88%86%E6%9E%90-webpack-%E6%89%93%E5%8C%85%E7%9A%84%E5%91%BD%E4%BB%A4)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---
title: webpack命令备忘
date: 2016-03-03 09:29:15
tags: webpack
---

## 安装webpack

```sass
npm install webpack -g //webpack全局安装到了本地环境中，就可以使用webpack命令了。
```


## 在项目中使用webpack

```sass
npm init //实例化package.json文件。
npm install webpack --save-dev //安装webpack到package.json文件中。
//或者通过npm install webpack@1.2.x --save-dev 安装指定版本的webpack到package.json文件中。
npm install webpack-dev-server --save-dev //安装dev tools到package.json文件中，本地运行webpack服务
```

在包含 `webpack.config.js` 的目录运行命令：

```sass
webpack //执行一次开发时的编译
webpack -p //执行一次生成环境的编译（压缩）
webpack --watch //在开发时持续监控增量编译（很快）
webpack -d //让他生成SourceMaps
webpack --progress //显示编译进度
webpack --colors //显示静态资源的颜色
webpack --sort-modules-by, --sort-chunks-by, --sort-assets-by //将modules/chunks/assets进行列表排序
webpack --display-chunks //展示编译后的分块
webpack --display-reasons //显示更多引用模块原因
webapck --display-error-details //显示更多报错信息
```

或者如果你改变了 `webpack.config.js` 的文件名或文件路径，比如改为 `./config/dev.config.js`:

```sass
$ webpack --config congig/dev.config.js
```

[webpack入门级教程](http://www.cnblogs.com/shinggang/p/5034404.html)

## 利于分析 webpack 打包的命令

```scss
// 带有色彩的输出每一步所耗费的时间和各个资源的引用情况
$ webpack --colors --profile --display-modules

// 编译完成之后输出一个json文件
$ webpack --json > [文件名].json
```

使用 `--json` 之后，在命令运行目录下生成一个之前指定名称的 json 文件。通过 [Webpack Analyze](http://webpack.github.io/analyse/) 或 [WEBPACK VISUALIZER](http://chrisbateman.github.io/webpack-visualizer/) 上传 json 文件可以进行详细的分析

[Webpack your bags](http://blog.madewithlove.be/post/webpack-your-bags/)（业界良心的绝世好文，从webpack的初步到深入都有）