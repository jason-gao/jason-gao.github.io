---
title: sql inject leak 
date: 2021-06-23 16:40:00
tags:
    - sql注入
categories:
    - safe    
---

## sql盲注

### sql注入是什么
- sql注入是一种常见的黑客攻击手段，通过执行一些sql，获取数据库数据和权限

### 危险等级
- 危害等级：高

### 注入案例
- 通常在参数后面接
    - param1=xx'and(select*from(select+sleep(10))a/**/union/**/select+1)='
    - param1=xx%27and%28select%2Afrom%28select%2Bsleep%283%29%29a%2F%2A%2A%2Funion%2F%2A%2A%2Fselect%2B1%29%3D%27

### 产生原因
- 参数没有严格校验
- 数据库orm没有遵循预处理

### 修复方法
- 用户输入参数做校验
- 数据库orm使用预编译，且业务遵循orm封装





