#### 安装完主题后，页面中间部分空白

* 依次检查主题文件夹名称是否为`handsome`
* 是否已经安装并且启用主题必要的插件

#### 点击首页头像，显示404页面

* 需要新建“时光机”独立页面，具体方法见[独立页面](/page)

#### links插件无法启用，显示500错误

* 更新主题包中最新版本的links插件`1.1.2`
* 一般是由于你的`usr/plugin`没有足够的权限导致的。

如果是Linux服务器尝试，在typecho的usr目录下输入此命令：

```bash
sudo chmod -R 777 plugin
```

如果仍有问题，请联系我

#### 友链设置后前台不输出内容（使用无效）

* links插件需要填写`链接分类`来判断输出的位置，请详细阅读[友链设置文档](./plugin)

#### 无法评论，提示输入内容不符合规则

请依次检查以下内容：

* cdn缓存静态缓存了HTML页面，导致评论功能失败（cdn缓存建议只缓存静态资源文件，如css js image）
* 使用了服务器缓存功能
* 使用了数据库缓存插件
* 使用了页面代码压缩的插件

如仍有问题，请联系我。

#### typecho1.1版本编辑器无法解析HTML代码


* typecho 1.0正式版本原生markdown解析器非常弱，可以解析HTML，但是无法解析表格。可以配合以下插件使用[typecho-plugin-Parsedown](https://github.com/kokororin/typecho-plugin-Parsedown) 或者 [typecho-markdown](https://github.com/mrgeneralgoo/typecho-markdown)(包含更多markdown语法)

!> 插件安装后请注意文件夹命名要求。安装插件后，无需任何设置，自动替换前台文章解析，支持解析表格和HTML代码。

* typecho 1.1正式版本原生markdown解析器不支持解析HTML代码，必须使用特权模式才可以解析HTML代码，示例如下：

```html
!!!
// 你的HTML代码
!!!
```
* 使用typecho开发版本（比1.1正式版本更高的版本）[下载开发版本](http://typecho.org/download)



#### 全局音乐播放器一直在加载无法播放

* PHP必须满足 PHP>=5.4
* 某些国外服务器无法云解析，请使用手动添加歌曲功能
* 服务器需要安装curl 扩展，请勿禁用`curl_exec`函数，并且curl扩展需要支持https
* 网易云会时常封禁cookie，导致解析失败，请打开主题目录下面的`libs/Get.php` 根据注释要求修改`$netease_cookie`变量。（一般有问题的话，我会在群内通知的）或者换用QQ音乐或者其他平台

如果仍有问题，请联系我。

#### 评论区不能斗图不能显示图片 | 说说不能显示图片/音乐播放器/视频播放器**

* 后台 `设置——评论——允许使用的HTML标签和属性` 里面添加html标签
```html
<img src="">
<audio class="" src="" preload>
<video src=""></video>
```

#### 评论区无法使用markdown语法

* 后台 `设置——评论——在评论中使用Markdown语法(选中)`
后台 `设置——评论——允许使用的HTML标签和属性` 里面添加markdown语法对应的html标签
```html
<blockquote><pre><code><strong><em><h5><h6><a href title><table><thead><tr><th><tbody><td>
```

#### 使用EditorMD前台文章首次不加载，刷新一次才能加载

* 主题pjax与EditorMD的前台解析js有冲突，在该插件的设置界面，将`接管前台Markdown解析并启用ToC、TeX科学公式、流程图 Flowchart、时序图 Sequence Diagram 等扩展`
选择否即可。


