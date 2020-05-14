---
title: 'Valine评论系统'
date: 2020-05-11 02:03:08
tags: [Gridea]
published: true
hideInList: false
feature: https://valine.js.org/images/valine.png
isTop: false
---
Gridea提供了两个评论系统，[Gitalk](https://github.com/gitalk/gitalk/blob/master/readme-cn.md)和[disqus](https://github.com/SukkaW/DisqusJS)。Gitalk需要使用Github账号登录，对于没有github账号的人来说不太方便，disqus目前在国内不可用。找了好久，发现了[valine](https://valine.js.org//)这个评论系统。

<!-- more -->



# 在Gridea中加入Valine

## Valine介绍

Valine - 一款快速、简洁且高效的无后端评论系统。

官网地址：https://valine.js.org/

## leancloud注册及配置

leancloud注册及配置见[快速开始文档](https://valine.js.org/quickstart.html)

## 修改主题模板

在Gridea theme模板的**head.ejs**中引入

```html
    <script src='//unpkg.com/valine/dist/Valine.min.js'></script>
```

在**post.ejs**文章详情页模板中文章末尾的位置添加下面的代码

```html
<div id="vcomments"></div>
    <script>
        new Valine({
            el: '#vcomments',
            appId: '<API_ID>',
            appKey: '<API_Key>'
        })
    </script>
```

appid和和appkey替换成leancloud中的应用key即可。修改完成后点击保存，然后同步，就可以了。记得在Gridea客户端中把配置中的评论关掉。

打开文章详情页，显示评论框就成功了。

![img](https://cdn.nlark.com/yuque/0/2019/png/302953/1563170592469-assets/web-upload/9209fe50-a1b7-47e2-bc51-5cbb67b0931d.png)





# Valine的配置

## el

- 类型:`String`
- 默认值:`null`
- 必要性:`true`

Valine 的初始化挂载器。可以是一个`CSS 选择器`，也可以是一个实际的`HTML元素`。

## appId

- 类型:`String`
- 默认值:`null`
- 必要性:`true`

从`LeanCloud`的应用中得到的`appId`.

> [获取appId 和 appKey](https://valine.js.org/quickstart.html)。

## appKey

- 类型:`String`
- 默认值:`null`
- 必要性:`true`

从`LeanCloud`的应用中得到的`appKey`.

> [获取appId 和 appKey](https://valine.js.org/quickstart.html)。

## ~~region~~

- 类型:`String`
- 默认值:`cn`
- 必要性:`false`

存储节点：在`Valine`中初始化时默认遵循`Leancloud SDK`的节点规则(`默认中国大陆节点`)。

> Leancloud js-sdk 从 `v3.8.0`版本开始删除了`region`选项:
> [leancloud/javascript-sdk/releases/tag/v3.8.0](https://github.com/leancloud/javascript-sdk/releases/tag/v3.8.0)

可选值:

- `cn` - 中国大陆节点
- `us` - 海外节点

## placeholder

- 类型:`String`
- 默认值:`Just go go`
- 必要性:`false`

评论框`占位提示符`。

## ~~notify~~

- 类型:`Boolean`
- 默认值:`false`
- 必要性:`false`

> `v1.4.0+` 已废弃

## ~~verify~~

- 类型:`Boolean`
- 默认值:`false`
- 必要性:`false`

验证码服务。

> `v1.4.0+` 已废弃

## path

- 类型:`String`
- 默认值:`window.location.pathname`
- 必要性:`false`

当前`文章页`路径，用于区分不同的`文章页`，以保证正确读取该`文章页`下的评论列表。
可选值：

- `window.location.pathname` (默认值，推荐)
- `window.location.href`
- `自定义`

> - I. 请保证每个`文章页`路径的唯一性，否则可能会出现不同`文章页`下加载相同评论列表的情况。
> - II. 如果值为`window.location.href`，可能会出现随便加`不同参数`进入该页面，而被判断成新页面的情况。

## avatar

- 类型:`String`
- 默认值:`mm`
- 必要性:`false`

`Gravatar` 头像展示方式。

可选值：

- `''`(空字符串)
- `mp`
- `identicon`
- `monsterid`
- `wavatar`
- `retro`
- `robohash`
- `hide`

更多信息，请查看[头像配置](https://valine.js.org/avatar.html)。

## meta

- 类型:`Array`
- 默认值:`['nick','mail','link']`
- 必要性:`false`

评论者相关属性。

## pageSize

- 类型:`Number`
- 默认值:`10`
- 必要性:`false`

评论列表分页，每页条数。

## lang

- 类型:`String`
- 默认值:`zh-CN`
- 必要性:`false`

多语言支持。

可选值：

- `zh-CN`
- `zh-TW`
- `en`
- `ja`

如需`自定义语言`，请参考[i18n](https://valine.js.org/i18n.html)。

## visitor

- 类型:`Boolean`
- 默认值:`false`
- 必要性:`false`

[文章访问量统计](https://valine.js.org/visitor.html)。

## highlight

- 类型：`Boolean`
- 默认值: `true`
- 必要性: `false`

`代码高亮`，默认开启，若不需要，请手动关闭

## avatarForce

- 类型: `Boolean`
- 默认值: `false`
- 必要性: `false`

每次访问`强制`拉取最新的`评论列表头像`

> 不推荐设置为`true`，目前的`评论列表头像`会自动带上`Valine`的版本号

## recordIP

- 类型: `Boolean`
- 默认值: `false`
- 必要性: `false`

是否记录评论者IP

> ```
> v1.3.5+
> ```

## serverURLs

- 类型: `String`
- 默认值: `http[s]://[tab/us].avoscloud.com`
- 必要性: `false`

> ⚠️ 该配置适用于国内`自定义域名`用户, `海外版本`会自动检测(无需手动填写) `v1.3.10+`

## emojiCDN

- 类型: `String`
- 默认值: ``
- 必要性: `false`

设置`表情包CDN`，参考[自定义表情](https://valine.js.org/emoji.html)

> ```
> v1.4.5+
> ```

## emojiMaps

- 类型: `Object`
- 默认值: `null`
- 必要性: `false`

设置`表情包映射`，参考[自定义表情](https://valine.js.org/emoji.html)

> ```
> v1.4.5+
> ```

## enableQQ

- 类型: `Boolean`
- 默认值: `false`
- 必要性: `false`

是否启用`昵称框`自动获取`QQ昵称`和`QQ头像`, 默认关闭，需`博/网站主`主动启用

> ```
> v1.4.6+
> ```

## requiredFields

- 类型: `Array`
- 默认值: `[]`
- 必要性: `false`

设置`必填项`，默认`匿名`，可选值：

- `['nick']`
- `['nick','mail']`

> ```
> v1.4.6+
> ```