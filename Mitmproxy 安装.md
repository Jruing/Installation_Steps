# Mitmproxy Python 安装步骤

[官方文档](https://docs.mitmproxy.org/stable/)

## 安装mitmproxy
在cmd中输入

```
pip install mitmproxy
```
安装完成后，在cmd中输入 mitmdump(*windows不能使用mitmproxy*)

## 安装证书
当前用户目录中找到.mitmproxy这个文件夹

[![微信截图_20190513102141.png](https://i.loli.net/2019/05/13/5cd8d4ee21b2990403.png)](https://i.loli.net/2019/05/13/5cd8d4ee21b2990403.png)

安装这个证书
一直点下一步，直至完成，在完成阶段会出现一个警告，点击是就ok

## 测试
修改系统代理
在IE浏览器中 》 工具 》internet选项 》 连接 》 局域网设置 》 高级 

[![db2531b09a7d5da4326d9ca319f87f8.png](https://i.loli.net/2019/05/13/5cd8d6919dfe737266.png)](https://i.loli.net/2019/05/13/5cd8d6919dfe737266.png)

修改图中服务器地址为127.0.0.1 端口为8000 点击确定

在cmd中输入mitmweb

新启动一个浏览器

随意访问一个页面查看

返回http://127.0.0.1:8081/#/flows查看抓取的内容
