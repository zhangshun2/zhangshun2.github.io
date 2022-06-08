# fidder自测和路由转发

> @author zhangshun
>
> 对fidder不熟悉的优先点开文档中的链接



## 痛点和用途

Q: 点击小程序不知道访问了那些接口,不知道环境是啥样的,也不清楚数据流转,有时间验证接口参数是不是按照对接标准来的,想要确认一下

A:使用fidder抓包



Q: 微信小程序依赖于腾讯的平台,体验版只有一个,但是uat和sit有两个,使用的时候前端需要编译发布来回切换,对于使用两套环境的人是冲突的

A:使用fidder做路由转发,去切换后台环境,如果token也不一样可以参照下方`本地环境任意切换`,`参数替换`的参考链接替换掉token

​	这样就走代理实现了本地平滑切换sit和uat,甚至是自测生产环境,有些时候测试问题可以用这种方法快速切换到本地进行回归



Q:开发这边想自测从登录注册,到完善简历投递简历,到候选人审核,到审核通过查询是否有奖金的全流程

A:可以用fidder抓包,之后删除用不到的接口,只保留有用的接口,然后导出为har脚本,然后生成python文件,直接修改python代码逻辑做主流程的链路测试

​	同时一些常用的东西保存脚本,修改路由成本地的localhost进行自测.



## 本地环境任意切换

### 基础

[fidder下载]: https://www.telerik.com/fiddler

(可以自行搜搜fidder抓包手机)

[相关fidder抓包手机链接]: https://blog.csdn.net/weixin_44931933/article/details/121271938

电脑打开wifi,台式机的话插一个外置网卡然后再打开wifi

打开fidder,配置代理默认端口8888

电脑cmd命令查看ipconfig,查看本地局域网ip4地址

手机连接到电脑所开的局域网,之后选择静态地址,填写进电脑局域网的ip4地址以及端口8888

此时fidder抓包正常抓入



### 遇到的问题

前端转发的后端地址,是指定死的,这里想直接走代理切换掉环境

把接口转发掉

打开rule-customize rules 

全文检索Before

找到BeforeRequest

在对应的函数末补充如下配置

~~~har
		if(oSession.indexOf('路由A')>-1){
			oSession.url = oSession.url.Replace('路由A','路由B');	
		}
~~~

即可实现环境从sit转发到uat或者本地

举例: 当前是预生产环境uat,我想本地直接让小程序连到测试st的后台

已知预发域名是:jr-zl-wechat.jrit.top;  测试域名是:jr-zl-wechat.jrit.vip;

~~~shell
if(oSession.indexOf('jr-zl-wechat.jrit.vip')>-1){
			oSession.url = oSession.url.Replace('jr-zl-wechat.jrit.vip','jr-zl-wechat.jrit.top');	
}
~~~

同理可得,你可以任意替换前端页面对应的后台,实现本地任意切换后台环境,甚至是线上环境路由到本地进行测试,调试可以说是,方便的一批

参考链接:

[fidder修改代理的路由]: https://blog.csdn.net/difffate/article/details/62425723?spm=1001.2101.3001.6650.1&amp;utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-62425723-blog-112610710.pc_relevant_antiscanv3&amp;depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-62425723-blog-112610710.pc_relevant_antiscanv3&amp;utm_relevant_index=2	"fidder修改代理的路由"

也可以替换参数

参考链接:

[fidder修改代理路由的参数]: https://docs.telerik.com/fiddler/knowledge-base/fiddlerscript/modifyrequestorresponse



## HAR脚本使用

参考链接:

[fidder生成测试用例python版本]: http://t.zoukankan.com/chineseluo-p-13703944.html

fidder,postman,以及谷歌浏览器控制台

都可以把对应的链接

右键生成httpArchive,即后缀har的文件

直观理解为录制脚本

可以通过脚本化操作进行自动化测试

也可以很方便的进行本地测试,详述见下面`测试用例快速生成`的文档

### 生成文件

生成json文件

~~~shell
har2case har_demo.har -2j
~~~

生成yml文件

~~~shell
har2case har_demo.har -2y
~~~

生成python对应的.py文件

~~~shell
har2case har_demo.json/har_demo.yml
~~~

### 运行文件

相关命令

~~~shell
hrun har_demo_test.py/har_demo.json/har_demo.yml
~~~

python文件可以单独测试

~~~shell
pytest har_demo_test.py
~~~



## 测试用例快速生成

短期内开发自身用不上,不做累述

参考链接

https://www.jianshu.com/p/0dba91d12f01