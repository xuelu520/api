# api [![Build Status](https://travis-ci.org/yobook/api.svg?branch=master)](https://travis-ci.org/yobook/api)
> api service, nodejs based

# code style
> indent 2 space

# API列表
> 打开[swagger.io编辑器](http://editor.swagger.io/#/edit), 上传项目内的swagger.yaml即可使用

# 数据库迁移
> 采用[sequelizejs自带migration](http://docs.sequelizejs.com/en/latest/docs/migrations//)进行数据库迁移， 并且已经加入到gulp豪华套餐中

# 持续集成服务
> 采用[Travis](travis-ci.org)进行部署和测试

# 构建工具
## 安装
采用gulp进行构建， 请本地安装gulp
```
npm install -g gulp
```
## tasks
### install
将会对src内的package.json进行安装
### db:migrate
将会对src/migrations内的脚本进行迁移
### db:create
将会产生一个src/migrations内的迁移脚本
这个脚本包含up和down脚本，在编写脚本的时候请明确正向迁移up和回滚down方法
### db:undo
将会回滚上一个操作


# IDE
## IntelliJ Idea
> 使用idea已经支持nodejs debug，请确认勾选上preference -> javascript -> lib内的nodejs相关lib

# 开发环境
开发环境使用gulp进行安装，在建立自己的开发环境时，请安装以下：
* node.js
* mysql

## clone代码到本地，安装gulp， 如果需要，请加上sudo
```
npm install -g gulp
```
## 依赖安装
```
npm install
gulp install
```
## 初始化数据库
```
mysql -uroot < ./scripts/create_database.sql
gulp db:migrate
```
## 启动开发环境
启动开发环境会自动watch ./src下所有的js\json文件，任何文件更新都触发重启
```
gulp dev
```
如果需要手动重启，直接在启动后的命令行stdin内输入rs
## 执行自动化测试
```
gulp test
```
## 本地访问测试
```
curl http://127.0.0.1:9527/healthcheck
```