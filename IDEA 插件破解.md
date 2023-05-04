# IDEA Eval Reset 使用方法

## 安装插件

### 离线安装方式

```json
1、下载插件
下载地址：https://plugins.zhile.io/files/ide-eval-resetter-2.1.6.zip

2、安装插件

直接下载插件 zip 包（macOS 可能会自动解压，然后把 zip 包丢进回收站）
通常可以直接把 zip 包拖进 IDE 的窗口来进行插件的安装。如果无法拖动安装，你可以在Settings/Preferences... -> Plugins 里手动安装插件（Install Plugin From Disk...）
插件会提示安装成功
```

### 在线安装方式

File -> Setting->plugins

![img](https://img-blog.csdnimg.cn/2021050814590156.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM3Njk5MzM2,size_16,color_FFFFFF,t_70)

点击后 跳出弹框点击+号添加图中的网址

![img](https://img-blog.csdnimg.cn/20210508145953255.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM3Njk5MzM2,size_16,color_FFFFFF,t_70)

然后搜索 IDE Eval Reset安装即可

![img](https://img-blog.csdnimg.cn/20210508150114377.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM3Njk5MzM2,size_16,color_FFFFFF,t_70)

## 使用插件

成功安装插件后，在 帮助 下会多一个 Eval Reset 按钮，如下图所示：

jetbrains 试用
一般来说，在 IDE 窗口切出去或切回来时（窗口失去/得到焦点）会触发事件，检测是否长时间（25 天）没有重置，给通知让你选择。（初次安装因为无法获取上次重置时间，会直接给予提示）

也可以手动唤出插件的主界面：

如果 IDE 没有打开项目，在Welcome界面点击菜单：Get Help -> Eval Reset
如果 IDE 打开了项目，点击菜单：Help -> Eval Reset
唤出的插件主界面中包含了一些显示信息，2 个按钮，1 个勾选项：

按钮：Reload 用来刷新界面上的显示信息。
按钮：Reset 点击会询问是否重置试用信息并重启 IDE。选择 Yes 则执行重置操作并重启 IDE 生效，选择 No 则什么也不做。（此为手动重置方式）
勾选项：Auto reset before per restart 如果勾选了，则自勾选后每次重启/退出 IDE 时会自动重置试用信息，你无需做额外的事情。（此为自动重置方式）