# 乐优商城

## 跨域问题解决

https://github.com/coder-lzh/leyou/blob/master/day06-webpack/day06.md#63cors%E8%A7%A3%E5%86%B3%E8%B7%A8%E5%9F%9F

## 异步查询工具axios
https://github.com/coder-lzh/leyou/blob/master/day06-webpack/day06.md#73%E5%BC%82%E6%AD%A5%E6%9F%A5%E8%AF%A2%E5%B7%A5%E5%85%B7axios

## qs工具的使用
https://github.com/coder-lzh/leyou/blob/master/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86.md#132qs%E5%B7%A5%E5%85%B7

## 子组件调用父组件方法
https://github.com/coder-lzh/leyou/blob/master/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86.md#14%E6%96%B0%E5%A2%9E%E5%AE%8C%E6%88%90%E5%90%8E%E5%85%B3%E9%97%AD%E7%AA%97%E5%8F%A3

## Zuul的路由过滤
https://github.com/coder-lzh/leyou/blob/master/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86.md#224%E7%BB%95%E8%BF%87%E7%BD%91%E5%85%B3
注意一下：这个链接的方案是不对的。需要采取这种方法
这里比较容易迷惑，再仔细说明一下，下面的配置的作用仅仅是改变下路由的路径。没其他作用，请求还是要走网关的。要是不想走网关，需要去nginx中配置一下。可以看课件，没毛病。
http://api.leyou.com/api/item/brand/page   映射成   item-service/brand/page  
http://api.leyou.com/api/upload/image      映射成   upload-service/upload/image   
```html
zuul:
  prefix: /api # 添加路由前缀
  retryable: true
  routes:
      item-service: /item/** # 将商品微服务映射到/item/**
      upload-service:       # 将上传微服务映不添加映射信息。注意，/api是映射，同样upload也是映射
        path: /upload/**
        serviceId: upload-service
        strip-prefix: false
```
## fastDFS的安装
卧槽，快搞死我了，一直报错。发现课件和视频上的不一致--但是最主要原因是配置文件的ip写错了。。。
测试安装成功命令 在 /etc/fdfs 下 执行  成功会返回一个路径
/usr/bin/fdfs_upload_file  client.conf /2.png

我安装的时候nginx路径是 /usr/sbin/nginx   配置文件是 /usr/local/nginx-1.10.0/conf/nginx.conf

https://github.com/coder-lzh/leyou/blob/master/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86/centos%E5%AE%89%E8%A3%85FastDFS.md#1-centos%E4%B8%8B%E5%AE%89%E8%A3%85fastdfs

## 静态页面实现服务器热部署
https://github.com/coder-lzh/leyou/blob/master/day10-%E5%95%86%E5%93%81%E7%AE%A1%E7%90%86/day10-%E5%95%86%E5%93%81%E7%AE%A1%E7%90%86.md#32live-server

## redis的安装
https://github.com/coder-lzh/leyou/blob/master/day16-%E7%94%A8%E6%88%B7%E6%B3%A8%E5%86%8C/redis%E5%AE%89%E8%A3%85%E9%85%8D%E7%BD%AE.md#redis%E5%AE%89%E8%A3%85%E5%92%8C%E9%85%8D%E7%BD%AE

## 后台数据的校验
https://github.com/coder-lzh/leyou/blob/master/day16-%E7%94%A8%E6%88%B7%E6%B3%A8%E5%86%8C/day16-%E7%94%A8%E6%88%B7%E6%B3%A8%E5%86%8C.md#651%E4%BB%80%E4%B9%88%E6%98%AFhibernate-validator
