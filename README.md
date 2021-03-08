SDK
体验地址
http://paysdk.weixin.qq.com/

快速搭建指南
①、安装配置nginx+phpfpm+php
②、建SDK解压到网站根目录
③、修改lib/WxPay.Config.php为自己申请的商户号的信息（配置详见说明）
⑤、下载证书替换cert下的文件
⑥、搭建完成

SDK目录结构
|-- lib
|-- logs
`-- example


目录功能简介
lib
API接口封装代码
WxPay.Api.php 包括所有微信支付API接口的封装
WxPay.Config.Interface.php  商户配置 , 业务需要从这里继承（请注意保管自己的密钥/证书等）
WxPay.Data.php   输入参数封装
WxPay.Exception.php  异常类
WxPay.Notify.php    回调通知基类

cert
证书存放路径，证书可以登录商户平台https://pay.weixin.qq.com/index.php/account/api_cert下载
注意:
1.证书文件不能放在web服务器虚拟目录，应放在有访问权限控制的目录中，防止被他人下载；
2.建议将证书文件名改为复杂且不容易猜测的文件名；
3.商户服务器要做好病毒和木马防护工作，不被非法侵入者窃取证书文件。

example
样例程序代码路径

example/phpqrcode
开源二维码php代码

logs
日志文件

※配置指南
MCHID = '1225312702';
这里填开户邮件中的商户号

APPID = 'wx426b3015555a46be';
这里填开户邮件中的（公众账号APPID或者应用APPID）

KEY = 'e10adc3949ba59abbe56e057f20f883e'
这里请使用商户平台登录账户和密码登录http://pay.weixin.qq.com 平台设置的“API密钥”，为了安全，请设置为32字符串。

APPSECRET = '01c6d59a3f9024db6336662ac95c8e74'
改参数在JSAPI支付（open平台账户不能进行JSAPI支付）的时候需要用来获取用户openid，可使用APPID对应的公众平台登录http://mp.weixin.qq.com 的开发者中心获取AppSecret。

