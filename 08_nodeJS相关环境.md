##### 1. node.js环境及其依赖项

直接下载安装：[Node.js](https://github.com/nodejs/node)

版本查看：

```js
node -v
```

###### （1）nvm

说明： 通过`nvm`安装`node.js`环境，可安装多个版本，并根据需要切换`node`版本

下载地址:  [Releases · coreybutler/nvm-windows · GitHub](https://github.com/coreybutler/nvm-windows/releases)

```js
nvm -v // 版本查看

nvm -h // 查看帮助命令

nvm list available // 列出所有可用的node版本

nvm list // 列出已安装并且被nvm管理的node版本

nvm install 版本号 // 安装某个版本的node   

nvm uninstall 版本号 // 删除指定版本

nvm use 版本号 // 切换node版本

nvm current // 查看当前使用的node版本
```

常见问题：

(a)

- 切换版本时提示：`exit status 1: ��û���㹻��Ȩ`

解决方法：

- 安装路径不能包含中文、空格

- 搜索`Windows PowerShell`，并以管理员方式打开终端进行操作

- `nvm`的安装目录下，`setting.txt`的`root`路径(nvm安装路径)和`path`路径(node的各个版本的存放路径)要与实际安装路径一致

(b)

- 如果之前使用 npm 安装过扩展包，现在想使用 NVM 进行管理。则首先需要从全局中删除 node_modules 目录

解决方法：

```js
npm root -g // 查看全局 node_modules 目录
```

###### （2）npm

说明：它是`node`内置的，自带的

常用命令：

```js
npm -v // 版本查看

// 全局安装依赖包
npm install -g [package]  // 安装在node版本的环境里

npm uninstall -g [package] // 删除全局安装的包

// 项目局部安装依赖包
npm install [package] // 一般不使用，因为不修改项目中的package.json 文件，以后使用npm install初始化时不会自动安装依赖包

npm install --save-dev [package] // 开发环境，初始化时自动安装依赖，简写：npm install -D

npm install --save [package] // 生产环境，初始化时自动安装依赖，简写：npm install -S

npm uninstall [package] // 删除项目中安装的包
```

###### （3）yarn

说明：缓存了每个下载过的包，所以再次使用时无需重复下载。

常用命令：

```js
npm install -g yarn // 全局安装

yarn -v // 版本查看

// 全局安装依赖包
yarn global add [package] // 安装在node版本的环境里

yarn remove -g [package] // 删除全局安装的包

// 项目局部安装依赖包
yarn add [package]@[version] –dev // 开发环境，初始化时自动安装依赖，简写：yarn -D add [package]

yarn add [package] // 生产环境，初始化时自动安装依赖

yarn remove  [package] // 删除项目中软件包

// 缓存控制
yarn cache list // 列出已缓存的每个包

yarn cache dir // 全局缓存位置

yarn cache clean // 清除缓存
```

###### （4）cnpm

说明：淘宝源，用法与`npm`一样

常用命令：

```js
npm install -g cnpm --registry=https://registry.npm.taobao.org // 安装并设置源为淘宝镜像

cnpm -v // 版本查看
```

###### （5）pnpm

说明：含义为 `performant npm` 意指『高性能的 npm』，与`npm`一样的都是软件包管理工具。`pnpm `比其他包管理器快 2 倍。

常用命令：

```js
npm install -g pnpm // 全局安装

pnpm -v // 版本查看

// 全局安装依赖包
pnpm add -g [package] // 安装在node版本的环境里

pnpm uninstall -g [package] // 删除全局安装的包

// 项目局部安装依赖包
pnpm add -D [package] // 开发环境，初始化时自动安装依赖

pnpm add [package] // 生产环境，初始化时自动安装依赖

pnpm un [package] // 删除项目中软件包
```

###### 镜像管理

###### （1）nrm

说明：管理npm镜像的工具，可以列出可以使用的镜像，非常方便。

```js
npm install -g nrm // 全局安装

nrm ls // 查看镜像列表

nrm use tencent // 使用腾讯镜像

nrm current // 查看当前使用的镜像

nrm test // 测试速度

npm config set registry https://registry.npmmirror.com // 设置镜像为阿里云镜像
```

###### （2）yrm

说明：管理yarn镜像的工具，可以列出可以使用的镜像，非常方便。

```js
npm install -g yrm // 全局安装

yrm ls // 列出可以使用的镜像

yrm use taobao // 使用淘宝镜像

yrm test taobao // 测试镜像速度

yarn config get registry // 查看yarn当前使用的镜像

yarn config set registry https://registry.npm.taobao.org/ // 手动设置为淘宝镜像
```

##### 2. mock.js与json-server服务

###### （1）json-server

说明：为前端提供简单易操作的 RestFul 接口的服务。

官方地址：[https://github.com/typicode/json-server/](https://github.com/typicode/json-server/)

使用：

```js
// 1.安装JSON服务器
npm install -g json-server 

// 2.创建json文件
例如有一个db.json文件，里面的数据如下：
{
  "posts": [
    { "id": 1, "title": "json-server", "author": "typicode" },
    { "id": 2, "title": "哈哈哈哈", "author": "画师" }
  ],
  "comments": [
    { "id": 1, "body": "some comment", "postId": 1 }
  ],
  "profile": { "name": "typicode" }
}

// 3.启动JSON服务器
// 启动的文件可以是json文件，也可以是js文件，js文件需要导出json形式的数据
json-server --watch db.json
或
json-server --watch --port 8080 --host 127.0.0.1 db.json

// 4.调用接口
// （1）浏览器直接访问
http://localhost:8080/posts // 获取列表

http://127.0.0.1:8080/posts/1 // 获取id为1的单个资源

// （2）通过axios访问
// 服务
const server = 'http://127.0.0.1:8080';
// 查
$http.get(`${server}/posts`).then(function (res: any) {
  console.log(res.data);
});

$http.get(`${server}/posts`, {
      params: {
        id: 1,
      },
    })
    .then(function (res: any) {
      console.log(res.data);
  });

// 增
$http.post(`${server}/posts`, { // id自动生成
      title: "333",
      author: "3333",
    })
    .then(function (res: any) {
      console.log(res.data);
    });

// 更新
$http.put(`${server}/posts/3`, { // 更新id为3的数据
      title: "计划35",
      author: "34页6",
    })
    .then(function (res: any) {
      console.log(res.data);
    });

// 删除
$http.delete(`${server}/posts/2`) // 删除id为2的数据
    .then(function (res: any) {
      console.log(res.data);
    });
```

###### （2）mock.js

说明：生成各种测试数据

地址：[http://mockjs.com/](http://mockjs.com/)

```js
npm install --save-dev mockjs // 安装

// 语法1
let obj = Mock.mock({
    'id':'@id()',//得到随机id
    title:"@cword(1, 2)",//随机生成中文名字
    date:"@date()",//随机生成日期
    avatar:"@image('200x200','red','#fff','avatar')",//生成图片(宽高，背景色，字体色，文本)
    description:"@paragraph()",//描述
    ip:"@ip()",//ip地址
    email:"@email()"//email
})
console.log(obj);

// 语法2
const Mock = require('mockjs')
//Mock.Random 是一个工具类，用于生成各种随机数据
const Random = Mock.Random
module.exports = () => {
    //定义json-server需要的数据结构
    let data = { 
        news: [] 
    }
    //添加20条包含中文的内容
    for (let i = 1; i <= 20; i++) {
        data.news.push({
            id: i,
            title: Random.cword(10, 20),
            content: Random.cparagraph(10),
        })
    }
    return data
}
// 控制台启动服务
json-server --watch --port 3002 --host 127.0.0.1 db.js
// 浏览器访问
http://127.0.0.1:3002/news
```

常见问题：

- es6模块导入报错

解决方法：

- 初始化：`npm init`，直到出现`package.json`

- 在`package.json`里面添加`"type": "module"`

##### 3. axios请求

安装：

```js
npm install -S axios 
```

##### 5 .webpack

全局安装：

```
npm install webpack webpack-cli –g

一般指定版本
npm install webpack@3.6.0 -g
```

项目中的局部安装：

```
npm install webpack webpack-cli --save-dev

一般指定版本，除非报错
npm install webpack@3.6.0 --save-dev
```

版本查看：

```
webpack -v
```

项目中自动生成package.json文件

```
npm init -y
npm init
```

安装loader:

直接看官网

1.通过clean-webpack-plugin插件删除输出目中之前旧的文件。

```
npm install --save-dev clean-webpack-plugin
```

2.css相关

```
npm install --save-dev css-loader
```

3.样式相关

```
npm install --save-dev style-loader

npm install stylus stylus-loader --save-dev
```

4.less相关

```
npm install less less-loader --save-dev
```

5.图片相关

```
npm install --save-dev url-loader
```

6.手动配置vue

```
npm install -D vue-loader vue-template-compiler
```

安装插件plugin

1.HtmlWebpackPlugin  用来打包html

```
npm install --save-dev html-webpack-plugin
```

2.js压缩

```
npm install --save-dev uglifyjs-webpack-plugin@1.1.1
```

实时重新加载

```
npm install --save-dev webpack-dev-server
```

##### 6 .vue-cli

全局安装：3.0版

```
npm install -g @vue/cli
```

版本查看：

```
vue --version
```

项目创建：

vue2.0:

```
桥接工具，可拉取2.0版本，全局安装
npm install -g @vue/cli-init
# `vue init` 的运行效果将会跟 `vue-cli@2.x` 相同
vue init webpack my-project
```

vue3.0:

```
设计原则是"0配置",移除了vue2.0中的build和config等目录。
移除了static文件夹，新增了public文件夹，并将index.html移动到public中。

vue create 项目名称

vue ui
```

vue路由:

```
vue add router
```

导入：

```
import Axios from 'axios'
```

##### 8 .Git

克隆：

```
git clone 地址
```

增加：

```
git add .
```

挂载：

```
git commit -m " "
```

推送：

```
git push
```

##### 9 .Mint UI

安装：

```
// 安装 
# Vue 1.x 
npm install mint-ui@1 -S 

# Vue 2.0 
npm install mint-ui -S
```

引入：

```
// 引入全部组件 
import Mint from 'mint-ui'; 
import 'mint-ui/lib/style.css';
Vue.use(Mint);

// 按需引入部分组件 
import { Cell, Checklist } from 'mint-ui'; Vue.component(Cell.name, Cell); Vue.component(Checklist.name, Checklist);
```

##### 10 .Element-UI

安装：

```
npm i element-ui -S
```

引入：

```html
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';
Vue.use(ElementUI);
```

##### 11 .sass

webpack

```
第一种方法：
npm install node-sass --save-dev
npm install sass-loader --save-dev

第二种方法：
修改sass安装的源
npm config set sass_binary_site=https://npm.taobao.org/mirrors/node-sass
npm install

降低版本：
npm install node-sass@4.14.1 --save-dev
npm install sass-loader@7.3.0 --save-dev
```

vite

```
npm install --save-dev sass
```

##### 10.Stylus

安装

```
npm install stylus stylus-loader --save-dev
```

编写样式

```
<style lang="stylus" rel="stylesheet/stylus">

<style>
```

##### 12.json5

解决json文件，无法添加注释问题

```
npm install json5 --save-dev
```

##### 13.内网配置

1.设置代理

目的：内网是不能联网的，使用代理，是为了能下载相关的依赖，例如脚手架

```
npm config set registry http://172.29.0.245:8081/repository/group-npm/
```

2.sass本地下载

目的：内网不能联网，所以需要本地下载。你需要在外网下载好相关版本的依赖，然后外网通过ftp上传，内网通过sftp下载。

```
npm config set sass_binary_path="D:\yilaibao\win32-x64-83_binding.node"
```

以上两个配置  在C:\User\你自己电脑的用户名\.npmrc  文件上找

##### 14.内外网连通

```
先上传--使用ftp连接，上传文件到云桌面环境(这里通过一个软件FlashFXP)
ip：47.98.187.24，端口：21，用户名：ftpuser，密码：ftp_16888

在下载--在云桌面环境下载文件(这里通过一个软件Xftp7)
ip：172.29.0.246，协议sftp、连接端口：22、账号：sftp、密码：sftp_16888
```

##### 15. vsCode离线插件安装

```
https://marketplace.visualstudio.com/vscode
```

##### 16. nginx代理

```js
打开cmd命令窗口，切换到nginx目录下

start nginx // 启动

nginx -s stop // 强制停止

nginx -s quit // 处理完所有请求后再停止

nginx -s reload // 重启

killall nginx // 杀死所有进程
```
