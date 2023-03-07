## NodeJs配置

(配置16.x的版本，别下载后面的，会有各种问题)

可以参考： [(38条消息) NodeJs 的安装及配置环境变量_nodejs安装及环境配置_Alisone_li的博客-CSDN博客](https://blog.csdn.net/zimeng303/article/details/112167688)

1.下载安装包，下载**msi的**

[Node.js (nodejs.org)](https://nodejs.org/zh-cn/)

2.选择好路径开始安装即可

3.配置环境变量

> 3.1找到安装的路径，配置进去
> 
> 3.2配置 “node_global” 和 “node_cache”
> 
> 在nodejs的安装目录下，创建两个文件，然后将这两个文件的路径配置到环境变量中去
> 
> ```
> npm config set prefix "E:\develop_tool\Other_envs\nodejs\node_global"
> 
> npm config set cache "E:\develop_tool\Other_envs\nodejs\node_cache"
> 
> 修改 原来的配置（可能在用户那边）
> 
> 将 C:\Users\king\AppData\Roaming\npm 改成 node_global的路径
> ```
> 
> ```
> # 这个可以全局安装
> npm install express -g
> ```
> 
> “-g”等同于“–global”，“-g” 是全局安装，不加“-g”就是默认下载到当前目录。“-g” 表示安装到之前设置的【node_global】目录下，同时nodejs会自动地在node_global文件夹下创建【node_modules】子文件夹， 即自动下载到配置的路径

npm 下载东西的时候有时候会出问题，一般最好选择使用管理员身份打开，或者授予nodejs安装路径管理员权限。

4.配置淘宝镜像

```
# 查看当前镜像
npm config get registry
# 配置镜像
npm config set registry https://registry.npm.taobao.org/
```

 全局安装基于淘宝源的cnpm

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
# 查看
cnpm -v
```

全局安装yarn

```
npm install --global yarn
//yarn卸载
npm uninstall yarn -g  
// 查看是否成功
yarn --version
```

现在 Yarn 已经 [安装完毕](https://yarn.bootcss.com/docs/install)，可以开始使用了。 以下是一些你需要的最常用的命令：

**初始化一个新项目**

```
yarn init
```

##### 常用命令

```
yarn -v  // 查看yarn 版本
yarn config list  // 查看yarn配置
yarn config get registry   // 查看当前yarn源

// 修改yarn源（此处为淘宝的源）
yarn config set registry https://registry.npm.taobao.org  

// yarn安装依赖
yarn add 包名          // 局部安装
yarn global add 包名   // 全局安装

// yarn 卸载依赖
yarn remove 包名         // 局部卸载
yarn global remove 包名  // 全局卸载（如果安装时安到了全局，那么卸载就要对应卸载全局的）

// yarn 查看全局安装过的包
yarn

npm install -g yarn  // 安装yarn 
yarn --version       // 安装成功后，查看版本号
md yarn   // 创建文件夹 yarn  
cd yarn   // 进入yarn文件夹 

初始化项目 
yarn init // 同npm init，执行输入信息后，会生成package.json文件

yarn的配置项： 
yarn config list // 显示所有配置项
yarn config get <key> //显示某配置项
yarn config delete <key> //删除某配置项
yarn config set <key> <value> [-g|--global] //设置配置项

安装包： 
yarn install         //安装package.json里所有包，并将包及它的所有依赖项保存进yarn.lock
yarn install --flat  //安装一个包的单一版本
yarn install --force         //强制重新下载所有包
yarn install --production    //只安装dependencies里的包
yarn install --no-lockfile   //不读取或生成yarn.lock
yarn install --pure-lockfile //不生成yarn.lock
添加包（会更新package.json和yarn.lock）：

yarn add [package] // 在当前的项目中添加一个依赖包，会自动更新到package.json和yarn.lock文件中
yarn add [package]@[version] // 安装指定版本，这里指的是主要版本，如果需要精确到小版本，使用-E参数
yarn add [package]@[tag] // 安装某个tag（比如beta,next或者latest）

//不指定依赖类型默认安装到dependencies里，你也可以指定依赖类型：
yarn add --dev/-D // 加到 devDependencies
yarn add --peer/-P // 加到 peerDependencies
yarn add --optional/-O // 加到 optionalDependencies

//默认安装包的主要版本里的最新版本，下面两个命令可以指定版本：
yarn add --exact/-E // 安装包的精确版本。例如yarn add foo@1.2.3会接受1.9.1版，但是yarn add foo@1.2.3 --exact只会接受1.2.3版
yarn add --tilde/-T // 安装包的次要版本里的最新版。例如yarn add foo@1.2.3 --tilde会接受1.2.9，但不接受1.3.0

yarn publish // 发布包
yarn remove <packageName>  // 移除一个包，会自动更新package.json和yarn.lock
yarn upgrade // 更新一个依赖: 用于更新包到基于规范范围的最新版本
yarn run   // 运行脚本: 用来执行在 package.json 中 scripts 属性下定义的脚本
yarn info <packageName> 可以用来查看某个模块的最新版本信息

缓存 
yarn cache 
yarn cache list # 列出已缓存的每个包 
yarn cache dir # 返回 全局缓存位置 
yarn cache clean # 清除缓存

 global list  
```
