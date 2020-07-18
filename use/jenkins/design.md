---
author: Harris Wang
email: harris-wang@qq.com
date: 2020-07-19
---

# CI/CD Design

[TOC]

## 1.基础设施

1. 一台ubuntu服务器
2. jdk+tomcat+jenkins
3. git
4. docker(build services images; nginx image, mysql image etc.)
5. .netcore sdk
6. nodejs+yarn



## 2.规划

### 2.1多环境

- dev
- test
- staging
- prod

### 2.2阶段

- build
- test
- publish
- build image
- deploy



## 3.实现

### 3.1编写脚本

- shell
- groovy（jenkins pipline）

### 3.2配置jenkins

### 3.3日志

为日志文件创建静态站点，方便查看或者下载。



