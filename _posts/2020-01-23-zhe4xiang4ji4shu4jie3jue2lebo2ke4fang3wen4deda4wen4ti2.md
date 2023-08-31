---
title: "这项技术解决了博客访问的大问题"
categories: [ "计算机技术", "通用技术"  ]
tags: [ "CDN" ]
draft: false
slug: "299"
date: "2020-01-23 11:35:00"
---


由于一些原因，我的博客暂时托管在香港某家服务提供商的云主机之上，虽然商家已经尽权力为线路做了优化，但是到达大陆一些地域的访问速度还是不太理想，特别是在一些本人长期驻留的地域。

![2020-01-23-10-36-39-.png](https://imagehost-cdn.frytea.com/images/2020/01/23/2020-01-23-10-36-39-.png)

未来计划将网站迁回大陆，但还需时间，此外就算是大陆服务器，中国地大物博，无法保证到达任何一个区域的访问速度。因此就要用到一个叫 CDN 的技术了。

## CDN

内容分发网络（英语：Content Delivery Network或Content Distribution Network，缩写：CDN）是指一种透过互联网互相连接的电脑网络系统，利用最靠近每位用户的服务器，更快、更可靠地将音乐、图片、影片、应用程序及其他文件发送给用户，来提供高性能、可扩展性及低成本的网络内容传递给用户。（维基百科）

在国内使用 CDN 的话，除了各大综合性云服务商，就是较为专业的又拍云和七牛云了。使用又拍云测了一下速，可以发现上了 CDN 动态加速之后，博客访问速度有了较大的提升。

![2020-01-23-11-10-48-.png](https://imagehost-cdn.frytea.com/images/2020/01/23/2020-01-23-11-10-48-.png)

经过一段时间的使用，发现想要实现 动态加速 + HTTPS 访问的 CDN 加速，费用上还是需要考虑的。以某一天的访问数据为例（	2020-01-22），博客目前的访问量大概是这样子：

| CDN 服务	日使用流量 | HTTPS 加速 	日请求次数 | 动态资源加速 	日请求次数 |
| :--------------------------: | :------------------------------: | :-------------------------------: |
| 	0.176 GB | 	13186 次 | 12494 次 |

每日的使用水平大概是如此，就此可以大致推算出我目前所需的资源量，接下来我分别从 又拍云、七牛云和阿里云的官网找到了三家服务商的价格水平（2020-1-23），汇总如下：

CDN 费用对比

| 服务商 | 流量计费(流出，国内（元/GB）) | 动态请求计费（元/万次） | HTTPS 请求计费（元/万次） |
| :----: | :------------------: | :----------------: | :-------------------: |
| [又拍云](https://help.upyun.com/knowledge-base/cdn-price/) | 0.29 | 0.2 | 0.05  |
| [七牛云](https://www.qiniu.com/prices?source=fusion) | 0.28（0 ～ 100 TB，HTTPS 下载流量/动态加速）  | 0.19 | - |
| [阿里云](https://cn.aliyun.com/price/product#/cdn/detail) | 0.24（0GB-10TB(含）） | 0.15（动态HTTPS请求） | - |

套餐费用对比

| 服务商 | 流量包（100G/年） | 动态请求流量包(100万次/年) |
| :-------: | :-------: | :-------------------: |
| [又拍云](https://console.upyun.com/billing/resources/buy/) | ￥20 | - |
| [七牛云](https://portal.qiniu.com/financial/respack/fusion-composite) | ￥20  | - |
| [阿里云](https://cn.aliyun.com/) | ￥18  | ￥12.60 |

宗上，根据个人的需要，打算采用阿里云提供的 CDN 全站动态加速服务。

## 阿里云

这时出现问题了。

![2020-01-23-10-29-06-.png](https://imagehost-cdn.frytea.com/images/2020/01/23/2020-01-23-10-29-06-.png)

我第一次使用阿里云的 CDN 服务，怎么可能域名已存在呢？于是提交工单，阿里云给的答复是`有其他账号绑定了该域名`。这是什么情况？过了两天还未处理完毕，这时快过年了，阿里云回了一个电话说出了实情 `您这个情况是因为您在七牛云绑定了该域名`。what？我在七牛云绑定了和阿里云有什么关系？好吧，他们就是合作伙伴关系。就此呼应一下标题 `震惊！阿里云 CDN 居然和七牛云是一体的？`

经过一系列的工单操作，还是需要在阿里云那边操作，最终终于将我的域名放在了阿里云加速，最终发现速度还是很理想的，最终选择了速度较快且价格较实惠的阿里云 CDN 全站动态加速。

![2020-01-24-09-57-50-.png](https://imagehost-cdn.frytea.com/images/2020/01/24/2020-01-24-09-57-50-.png)

## 参考文档

 - [WikiPedia/内容分发网络](https://zh.wikipedia.org/wiki/%E5%85%A7%E5%AE%B9%E5%82%B3%E9%81%9E%E7%B6%B2%E8%B7%AF)