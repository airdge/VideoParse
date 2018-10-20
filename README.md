# VideoParse
![](https://upfile.asqql.com/2009pasdfasdfic2009s305985-ts/2016-7/20167112512365720.jpg)
## 优酷/youku
优酷的 ccode 经常变动,会导致解析器不可用,其一般限制useragent/referer/ckey/cookies

当前的解析器,大多以更换ccode为主,大体可以分为:
* App
   1. youku/tudou/cibn/合作方app,ccode大多为01010101多位数字字符串
   2. 此类ccode可以解析全长视频
   3. 依赖utid参数,由app算法生成,全平台app共用此utid
   4. 依赖useragent
   5. 默认ckey:7B19C0AB12633B22E7FE81271162026020570708D6CC189E4924503C49D243A0DE6CD84A766832C2C99898FC5ED31F3709BB3CDD82C96492E721BDD381735026
* 网页
   1. ccode经常变动/限制
   2. 全长:0502/0511/0512/0515/0519...  预览:0505/0503/0516/0517/0590..
   3. 部分视频使用预览ccode不能解析全长视频,具体由json.data.show.copyright字段控制
   4. 目前有效的解决方法为带cookies访问,或者带ckey(110#/112#)访问
   5. 同个ckey(110#)有解析时效限制
   6. ckey(110#)获取,一般可以使用phantomjs/webdriver,或者nodejs跑js获取
   7. ckey相关js: `https://aeu.alicdn.com/js/cj/113.js`
   8. 各版本ckey所能解析的ccode有点差异
   9. 默认ckey:DIl58SLFxFNndSV1GFNnMQVYkx1PP5tKe1siZu%2F86PR1u%2FWh1Ptd%2BWOZsHHWxysSfAOhNJpdVWsdVJNsfJ8Sxd8WKVvNfAS8aS8fAOzYARzPyPc3JvtnPHjTdKfESTdnuTW6ZPvk2pNDh4uFzotgdMEFkzQ5wZVXl2Pf1%2FY6hLK0OnCNxBj3%2Bnb0v72gZ6b0td%2BWOZsHHWxysSo%2F0y9D2K42SaB8Y%2F%2BaD2K42SaB8Y%2F%2BahU%2BWOZsHcrxysooUeND

## 爱奇艺/iqiyi 
dash与tmts算法一致,依赖cmd5x算法
cmd5x:http://static.iqiyi.com/js/common/7d183edd03bc4414b315e8964fb41826.js
encrypt: md5(tmts + salt)
salt: h2l6suw1************************
 
## 搜狐/sohu
uid要经过上报流程,链接才不会卡顿

`r.pingback("//z.m.tv.sohu.com/h5_cc.gif?" + d.stringify(f))`
## 腾讯/qq
url要经过上报流程,链接才不会卡顿


