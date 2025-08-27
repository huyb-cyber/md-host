\#### 简介：

访问网址： [https://npm.chuanyinet.com](https://npm.chuanyinet.com/)，基于 [Verdaccio](https://verdaccio.org/) 搭建，用于上传内部的npm包

\#### 使用方式

\##### 1、创建账户（账户使用邮箱前缀来创建）

npm adduser --registry [https://npm.chuanyinet.com/](https://npm.chuanyinet.com/)

\#### 2、发包

npm publish --registry [https://npm.chuanyinet.com/](https://npm.chuanyinet.com/)

\#### 3、安装包，3中方式

\- 1、指定源

npm i @pp/ldap --registry https://npm.chuanyinet.com/ 

\- 2、项目中配置.npmrc

registry=https://registry.npmmirror.com/ @pp:registry=https://npm.chuanyinet.com/ 

\- 3、配置别名

alias ppnpm="npm --registry=https://npm.chuanyinet.com" ppnpm i @pp/ldap 

\#### 约定

\- 内部的包名都以 @pp开头，例如 @pp/ldap

\### 项目npm源设置

在项目根目录下 建 .npmrc文件，然后写入下面代码，@pp前缀自动会走公司私服

\```javascript

registry=https://registry.npmmirror.com

@pp:registry=https://npm.chuanyinet.com/

\```