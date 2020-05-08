**前端知识**

   * [Web基础](#Web基础)
      * [1.常用的网络传输协议](#1.常用的网络传输协议)
      * [2.常见的状态码](#2-常见的状态码)
   * [Django](#Django)
   * [Flask](#Flask)
   * [Vue](#Vue)
   * [AngularJS](#AngularJS)
   * [React](#React)
   * [jQuery](#jQuery)


# Web基础

## 1.常用的网络传输协议
* TCP：传输控制协议，可靠传输，面向连接
* UDP：用户数据包协议，不可靠传输，面向无连接
* FTP：文件传输协议,用于上传和下载文件
* HTTP：超文本传输协议，基于TCP/IP通信协议，面向对象
* SMTP：邮件传输协议
* TELNET：Internet远程登录服务的标准协议和主要方式
* DNS：域名系统，将域名解析为ip地址

## 2.常见的状态码
| 状态码 | 状态 | 描述 |
| :----: | :---- | :---- |
| 200 | Ok | 请求成功 |
| 400 | Bad Request | 请求语法错误，不能被服务器解析 |
| 401 | Unauthorized | 未经授权，需与www-Authenticate一起用 |
| 403 | Forbidden | 服务器收到请求，但拒绝提供服务 |
| 404 | Not Found | 请求资源不存在 |
| 500 | Internal Server Error | 服务器发生不可预期的错误 |
| 503 | Server Unavailable | 服务器当前请求不可用 |
