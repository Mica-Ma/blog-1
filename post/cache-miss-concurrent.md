---
title: node 中的缓存击穿与解决方案
date: 2019-06-26T18:30:41+08:00
thumbnail: ""
categories:
  - 前端
  - 后端
tags:
  - node
---

缓存击穿指当某个 key 的缓存失效时，此时高并发请求来临时，会产生大量 IO 操作（读读数据库或发个请求），影响性能。

高并发场景并不多见，按理来说缓存击穿也很少发生。其实不然，数据的 batch 也会造成缓存击穿。

查看以下示例，获取某个用户的信息

如果
