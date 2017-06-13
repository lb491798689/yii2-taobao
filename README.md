# yii2-taobao
将阿里大于api整合为composer扩展（虽然名称是yii只要是composer就可以安装使用）
## 安装
```shell
composer require itsyc/yii2-taobao dev-master
```
## 使用
发送短信验证码的接口
```php
TopSdk::set();
$taobao = new Autoloader();
$c = new TopClient();
$c->appkey = $appkey;     //自己阿里大鱼的appkey
$c->secretKey = $secretKey;   //自己阿里大鱼的secretKey
$req = new AlibabaAliqinFcSmsNumSendRequest();
$req->setExtend("123456");
$req->setSmsType("normal");
$req->setSmsFreeSignName("有票了");
$req->setSmsParam("{\"code\":\"123123\"}");
$req->setRecNum("13023232323");
$req->setSmsTemplateCode("SMS_22910019");
$resp = $c->execute($req);
```
