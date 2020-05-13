---
layout: post
title: Web与前端知识点总结归纳
date: 2020-05-08 23:05:08
updated: 2020-05-14 01:36:55
tags: 
  - Web基础
  - 前端框架
  - 知识回顾
categories: 前端知识

---

> 本文主要对Web基础和前端框架知识进行梳理、回顾，把一些需要记住的概念原理，和容易混淆，晦涩的知识点进行归纳。

<!-- more -->

<div style='display: none'>

<!-- TOC -->

- [Web基础](#web基础)
    - [1. 常用的网络传输协议](#1-常用的网络传输协议)
    - [2. 常见的状态码](#2-常见的状态码)
    - [3. 三次握手](#3-三次握手)
    - [4. 四次挥手](#4-四次挥手)
- [Django](#django)
- [Flask](#flask)
- [Tornado](#tornado)
- [jQuery](#jquery)
- [Vue](#vue)
- [AngularJS](#angularjs)
- [React](#react)

<!-- /TOC -->

</div>

# Web基础

## 1. 常用的网络传输协议

* TCP：传输控制协议，可靠传输，面向连接
* UDP：用户数据包协议，不可靠传输，面向无连接
* FTP：文件传输协议,用于上传和下载文件
* HTTP：超文本传输协议，基于TCP/IP通信协议，面向对象
* SMTP：邮件传输协议
* TELNET：Internet远程登录服务的标准协议和主要方式
* DNS：域名系统，将域名解析为ip地址

## 2. 常见的状态码

| 状态码 | 状态 | 描述 |
| :----: | :---- | :---- |
| 200 | Ok | 请求成功 |
| 400 | Bad Request | 请求语法错误，不能被服务器解析 |
| 401 | Unauthorized | 未经授权，需与www-Authenticate一起用 |
| 403 | Forbidden | 服务器收到请求，但拒绝提供服务 |
| 404 | Not Found | 请求资源不存在 |
| 500 | Internal Server Error | 服务器发生不可预期的错误 |
| 503 | Server Unavailable | 服务器当前请求不可用 |

## 3. 三次握手

* 第一次握手：建立连接时，客户端发送SYN（SYN=x）到服务器，有主动打开状态进入SYN_SENT状态，等待服务器确认。
* 第二次握手：服务器收到SYN包，必须确认客户的SYN（ack=x+1）,同时自己也发送一个SYN包（syn=y），即SYN+ACK包，服务器进入SYN_RECV状态。
* 第三次握手：客户端收到服务器的SYN+ACK包，想服务器发送确认ACK包（ACK=y+1）,发送完毕，客户端和服务器进入ESTABLISHED状态，完成握手。

## 4. 四次挥手

# Django

# Flask

# Tornado

# jQuery

# Vue

# AngularJS

# React