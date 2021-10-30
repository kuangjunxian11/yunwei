# Windows配置SSL证书

## 目录

[TOC]

## 一.前提条件

- Web服务器类型是IIS。
- 要安装的证书已通过CA中心审核并签发。

## 二.安装配置

### 1. SSL证书（IIS）下载

将已签发的SSL证书（IIS）下载到服务器。

<img src="./imags/p101231.png" style="zoom:67%;" />

### 2.解压缩已下载的SSL证书（IIS）压缩包并上传到服务器

- 证书文件（PFX格式）：以`证书ID_证书绑定域名`方式命名。
- 私钥文件（TXT格式）：名称为pfx-password，内容为证书的密码。

<img src="./imags/WX20211008-155955@2x.png" style="zoom:67%;" />

### 3.导入证书

1.在服务器按Win+R键，打开运行，输入mmc，单击确定。

<img src="./imags/WX20211008-162146@2x.png" style="zoom:67%;" />

2.为本地计算机添加证书管理单元

在控制台上选择文件 > 添加删除管理单元。

<img src="./imags/WX20211008-163603@2x.png" style="zoom:67%;" />

在添加或删除管理单元对话框，从左侧可用的管理单元表中选择证书，单击添加。

<img src="./imags/WX20211008-163706@2x.png" style="zoom: 50%;" />

选择计算机账户

<img src="./imags/WX20211008-163823@2x.png" style="zoom: 50%;" />

选择本地计算机

<img src="./imags/WX20211008-163959@2x.png" style="zoom:50%;" />

点击确认。

3.安装IIS组件

打开服务器管理器，点击右上角的管理，选择添加角色和功能

<img src="./imags/WX20211008-164508@2x.png" style="zoom: 33%;" />

向导这里点击下一步

<img src="./imags/WX20211008-164611@2x.png" style="zoom:50%;" />

基于角色或者基于功能的安装，点击下一步，服务器选择这里选择本机，

<img src="./imags/WX20211008-164818@2x.png" style="zoom:50%;" />

<img src="./imags/WX20211008-164833@2x.png" style="zoom:50%;" />

选择web服务器（IIS），然后再添加功能

<img src="./imags/WX20211008-165014@2x.png" style="zoom:50%;" />

<img src="./imags/WX20211008-165051@2x.png" style="zoom:50%;" />

选择IIS可承载web核心

<img src="./imags/WX20211008-165312@2x.png" style="zoom:50%;" />

角色服务这里全部勾选

<img src="./imags/WX20211008-165652@2x.png" style="zoom:50%;" />

点击确认，等待安装完成即可。

<img src="./imags/WX20211008-172117@2x.png" style="zoom:50%;" />

3.导入证书

<img src="./imags/WX20211008-174652@2x.png" style="zoom: 33%;" />

点击下一页，添加要添加SSL文件

<img src="./imags/WX20211008-175212@2x.png" style="zoom:50%;" />

<img src="./imags/WX20211008-175147@2x.png" style="zoom:50%;" />

为私钥键入密码

<img src="./imags/WX20211008-175354@2x.png" style="zoom:50%;" />

<img src="./imags/WX20211008-175457@2x.png" style="zoom:50%;" />

导入证书完成

<img src="./imags/WX20211008-175520@2x.png" style="zoom:50%;" />



3.为网站绑定证书

搜索栏搜索IIS

<img src="./imags/WX20211008-165957@2x.png" style="zoom: 33%;" />

新建一个站点文件夹和index页面

<img src="./imags/WX20211008-173037@2x.png" style="zoom:50%;" />

然后添加网站

<img src="./imags/WX20211008-172320@2x.png" style="zoom:50%;" />

添加网站名称，填写网站内容目录，IP地址选择本机IP私有地址

<img src="./imags/WX20211008-173622@2x.png" style="zoom:50%;" />

绑定证书

<img src="./imags/WX20211008-175811@2x.png" style="zoom:50%;" />

添加网站

<img src="./imags/WX20211008-175835@2x.png" style="zoom:50%;" />

<img src="./imags/WX20211008-180307@2x.png" style="zoom:50%;" />



## 三.测试验证

### 搭站验证

<img src="./imags/WX20211008-180444@2x.png" style="zoom:50%;" />

<img src="./imags/WX20211008-180603@2x.png" style="zoom:50%;" />

<img src="./imags/WX20211008-180802@2x.png" style="zoom:50%;" />

![](/Users/kuangjunxian/Desktop/青莲/学习文档/阿里云/七牛云对象存储迁移到阿里云对象存储/images/WX20211029-182722@2x.png)

