---
title: node express 
date: 2020-07-01 11:15:00
tags:
    - node
    - express
categories:
    - node    
---

## 是什么
- web开发框架

## 用来干什么
- 写api接口
- 写web网站

## 安装
- npm install express --save

## 路由
```javascript
var app = express()

app.use(function (req, res, next) {
  console.log('Time:', Date.now())
  next()
})

app.post('/', function (req, res) {
  res.send('Got a POST request')
})

app.put('/user', function (req, res) {
  res.send('Got a PUT request at /user')
})

app.delete('/user', function (req, res) {
  res.send('Got a DELETE request at /user')
})
```

## 中间件
```javascript

var app = express()

app.use(function (req, res, next) {
  console.log('Time:', Date.now())
  next()
})

```