# 记录一次gitPage的搭建过程.
> @author zhangshun 

* 一开始我的需求很简单,我需要一个docsify网站.把我的md笔记整理,阿里云的博客内容迁移
   * 所以我需要一个评论区
   * 常见的评论组件最常见的是gitalk
   * gittalk需要在github的用户信息->setting->deploy setting ->OAuth App进行配置
   * 但是配置好之后评论区一直出现Error:not Found无法评论
   * 根据常理: 第一时间找文档,没文档关键词百度查询
   * 得出关键词: ```gitalk``` ,```error: not found```
   * 发现他们说OAuth App 的url回调地址应该填写git仓库的地址.
   * 尝试之后.不行
   * 观察他们的特征,是github.io结尾的.这个域名和我git仓库的地址不一样
   * 于是百度关键词: io结尾的域名.搜到好多博客搭建网站.大概遍历得出关键词gitPage
   
* 于是,搭建gitPage
  * 创建一个{username}.github.io为名称的空仓库并选择readme.md初始化.
  * 可以创建index.html当做主页
  * 这里有两条路子可以选,嫖线上的模板.或者自己搭建docsify网站
  * 这里我选择自己搭建docsify网站
  * 于是我的OAuth App的url也有了一个github.io结尾的gitPage地址
  * 此时我发现还tnd不行.评论区依然是这个问题.
  * 此时出于控制变量法我唯一可以尝试的就是repo这个属性.
  * 这是唯一一个填写实际地址的属性.那么,假设所有的博客都不对的话,自己去尝试,第一眼一定是仓库地址
  * 于是repo更换为一个简单的git仓库地址,而不是使用OAuth App的名称.评论模板成功   
   