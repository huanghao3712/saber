layout: doc
comments: false
date: 2015-5-18 4:11:59
repo: saber-router
ref: 0.2.0
---

# saber-router [![Build Status](https://travis-ci.org/ecomfe/saber-router.svg)](https://travis-ci.org/ecomfe/saber-router)

适用于移动端的`hash`路由控制

* 支持相对路径 `location.hash = '../somewhere/action'`
* 支持正则表达式控制路径
* 支持`RESTful`
* 使用`~`添加查询条件 `#/action~uid=100&name=saber`

## Usage

```javascript
var router = require('saber-router');

// 添加路由规则
router.add(
    '/custom/:id', // RESTful风格
    function (url, query) {
        console.log(query.id);
    }
);

// 开始路由监听
router.start();
```

## API

### .index

根路径，默认为`/`

### .add( path, fn, thisArg )

添加路由规则

* `path` `{string|RegExp}` 路由路径
* `fn` `{function(string, Object)}` 路由处理函数
* `thisArg` `{Object}` 路径处理函数的`this`指针

### .remove( path )

删除路由规则

### .clear()

清除所有路由规则

### .redirect( url, query, force )

URL跳转

* `url` `{string}` url
* `query` `{Object=}` 查询条件
* `force` `{boolean=}` 是否强制跳转

删除路由规则

### .start()

启动路由监听

### .stop()

停止路由监听

===

[![Saber](https://f.cloud.github.com/assets/157338/1485433/aeb5c72a-4714-11e3-87ae-7ef8ae66e605.png)](http://ecomfe.github.io/saber/)
