# 海角社区(haijiao.com) - 解锁VIP,去广告脚本

该脚本完全免费并开源,遵守MIT协议.

开源代码托管在: [haijiao_vip](https://github.com/sex4096/haijiao_vip/)

TG讨论群:`@svip_hj`

## 功能

- 去广告
- 屏蔽全局置顶贴
- 解锁VIP板块帖子
- 手机版适配

![setting1](snapshot/settings3.jpg)

## 待开发功能

- 解锁钻石和金币帖子
- 下载视频
- ~~免登录 (目前看来免登录问题还很多,滞后吧)~~

## 说明

### 目前需要登录网站才可以使用!!!

### 目前需要登录网站才可以使用!!!

### 目前需要登录网站才可以使用!!!

### 暂时是测试版本,不支持解锁钻石和金币帖子!可以加群持续关注进度!

不同于别的脚本对页面元素进行操作,或者从三方解析网站解析视频的操作,

该脚本对`底层请求`添加了`拦截器`, 通过修改请求来达到解锁VIP,去广告等功能,不对页面元素做任何修改

这样做的好处有:

1. 不用针对各个浏览器版本做兼容.
2. 由于拦截器可以拿到请求并替换返回,后续对付费视频做处理应该很简单,不需要从第三方解析视频.(我要好好想下,欢迎各位大佬提想法~)
3. 网站进行改动不需要适配.

## 安装

#### PC端:

正常Tampermonkey安装`haijiao.js`即可,~~脚本无任何依赖~~.

#### iOS:

推荐使用Safari浏览器+Stay插件进行安装,在Stay通过链接新建脚本即可:
`https://raw.githubusercontent.com/sex4096/haijiao_vip/master/haijiao.js`

#### 安卓:

我没安卓机器不知道,哪位哥们告诉一下~

## 闲聊

由于我对前端代码不是很熟悉,而且是第一次写Tampermonkey脚本,并且所以写的有些磕磕碰碰潦草的不行,大佬不要笑话我啊...

由于拿到了`webpack_require`,基本上可以对网站所有功能进行原生调用或者修改,所以大家有什么好的想法可以和我交流~

建立了一个TG群:`@svip_hj`,大家可以来交流. PS:禁止讨论反动言论,禁止讨论幼女/人兽等.

## 贡献

欢迎大佬贡献代码,基本调用如下:

比如调用网站的确认信息框并且在点击确认后弹出登录窗口:

```typescript
VUE.prototype.$message.close();
VUE.prototype
  .$confirm("您暂时还未登录,海角VIP脚本无法生效,请登录", "提示", {
    confirmButtonText: "确定",
    cancelButtonText: "取消",
    type: "warning",
  })
  .then(() => {
    VUE.prototype.$loginWindow();
  });
```

## 截图

设置界面在这里:

PC端:
![settings1](snapshot/settings1.jpg)

移动端:

![settings2](snapshot/settings2.jpg)
