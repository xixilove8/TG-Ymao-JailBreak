一些github写作技巧

1、插入代码行，复制下列代码
</span>

    </span>

        删
2、添加折叠效果
</span>

    <details>
    <summary>折叠标题</summary>
2-1、结尾输入
    </span>

    </details>
3、添加士例
</span>

    ---
    >
---
>示例效果展示，具体是这个样子的，
# 一、Quantumult X  自用资源汇总
## 1、Quantumult X 一些配置介绍。
**1、Quantumult X 策略组是什么？**
- 策略组可以实现 自动切换节点、节点筛选、是否走代理等。
- 策略组 需要配合 分流规则 使用。
- 策略组 可包含多个节点和策略组。

**2、Quantumult X 自带 3 种策略。**
- PROXY （代理）
- DIRECT（直连）
- REJECT（拒绝）

**3、Quantumult X 策略组类型。**
- static 静态策略-手动选择节点
- available 健康检查-自动选择节点，从第一个节点开始检查是否可用，直到选择可用节点。
- round-robin 负载均衡-轮询调度，轮流调用节点使用，IP可能会一直变。
- dest-hash 随即调整负载均衡
- url-latency-benchmark 自动测速-自动选择延迟低的节点

**4、Quantumult X 手动添加。**

在配置文件中的[general]下面添加以下内容

</span>

    用于节点延迟测试
    server_check_url=
    http://www.gstatic.com/generate_204
    #用于节点测试geo_location_checker=http://ip-api.com/json/?lang=zh-CN, https://raw.githubusercontent.com/I-am-R-E/Functional-Store-Hub/Master/GeoLocationChecker/QuantumultX/IP-API.js
    服务器测试超时时间 (毫秒)
    server_check_timeout = 3000
    功能强大的解析器，用于引用资源的转换resource_parser_url=https://cdn.jsdelivr.net/gh/KOP-XIAO/QuantumultX@master/Scripts/resource-parser.js
    下列路径将不经过QuanX的处理
    excluded_routes=239.255.255.250/32, 
    24.105.30.129/32, 185.60.112.157/32, 
    185.60.112.158/32, 182.162.132.1/32
    udp_whitelist=1-442, 444-65535

在配置文件中的[filter_remote]下粘贴以下内容

</span>

    FILTER_LAN, tag=LAN, force-
    policy=direct, enabled=true
    FILTER_REGION, tag=CN, force-
    policy=direct, enabled=true

## 2、Quantumult X 分流规则。
- Spotify分流 
</span>

    https://whatshub.top/rule/Spotify.list
- Copilot分流
</span>

    https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX/Microsoft/Microsoft.list
- 国际网络分流
</span>

    https://raw.githubusercontent.com/kjfx/QuantumultX/main/country/filter.list
- Twitter分流
</span>

    https://whatshub.top/rule/Twitter.list
- 国内媒体分流
</span>

    https://whatshub.top/rule/ChinaMedia.list
- YouTube Music分流
</span>

    https://whatshub.top/rule/YouTubeMusic.list
- YouTube分流
</span>

    https://whatshub.top/rule/YouTube.list
- 抖音IP分流
</span>

    https://raw.githubusercontent.com/im-dashan/proxy-plugin/main/loon/DouYin.list
- 抖音IP分流最新群友给的
</span>

    https://whatshub.top/rule/DouYin.list
- 微博分流
</span>

    https://whatshub.top/rule/Weibo.list
- 国内直连
</span>

    https://whatshub.top/rule/China.list
- Telegram分流
</span>

    https://whatshub.top/rule/Telegram.list
- ChatGPT分流
</span>

    https://whatshub.top/rule/ChatGPT.list

## 3、Quantumult X 重写资源。
- 知乎净化
</span>

    https://gist.githubusercontent.com/ddgksf2013/d43179d848586d561dbb968dee93bae8/raw/zhihu.js
- 什么值得买净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/smzdm_remove_ads.plugin
- 酷安净化
</span>

    https://github.com/ddgksf2013/Scripts/raw/master/coolapk.js
- 百度网盘净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/BaiduNetDisk_remove_ads.plugin
- 阿里云盘净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/AliYunDrive_remove_ads.plugin
- 起点读书净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/QiDian_remove_ads.plugin
- 12406净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/12306_remove_ads.plugin
- 淘宝净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/Taobao_remove_ads.plugin
- 京东净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/JD_remove_ads.plugin
- 微博净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/Weibo_remove_ads.plugin
- YouTube净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/YouTube_remove_ads.plugin
- 百度地图净化
</span>

    https://gist.githubusercontent.com/ddgksf2013/beec132ca0c3570ffa0cf331bce8f82a/raw/baidumap.adblock.conf
- 高德地图净化
</span>

    https://github.com/ddgksf2013/Rewrite/raw/master/AdBlock/Amap.conf
-  Spotify净化
</span>

    https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/Spotify_remove_ads.plugin
- vvwbo修复主页
</span>

    https://raw.githubusercontent.com/bin64/Scripts/main/QuantumultX/vvebo.js
- 最美证件照VIP
</span>

    https://raw.githubusercontent.com/WeiGiegie/666/main/zjzxg.js
- 酷我音乐VIP
</span>

    https://napi.ltd/script/Worker/KuWo.js
- 读不舍手VIP
</span>

    https://gist.githubusercontent.com/ddgksf2013/dbb1695cd96743eef18f3fac5c6fe227/raw/revenuecat.js
- 韩小圈VIP
</span>

    https://gist.githubusercontent.com/Yu9191/35453bcc1df1fd21febed34eb078c7e9/raw/Hanxiaoquan.sgmodules


# 二、个人收集Telegram频道
## 1、Quantumult X频道
</span>

    1、叮当猫iOS资源脚本分享 
    https://t.me/chxm1023
    
    2、QuantumultXjs
    https://t.me/GieGie777
    
    3、可莉日常  主要loon脚本
    https://t.me/ibilibili
    
    4、Surng&loon&QX脚本收集
    https://t.me/NobyDa
   
    5、小帽集团脚本频道
    https://t.me/XiaoMaoScript
    
    6、广告必须死
    https://t.me/Aa28413761
    
    7、Cuttlefish自留地
    https://t.me/ddgksf2021

## 2、TrollStore系列频道
</span>

    1、巨魔商店pro 交流群组
    https://t.me/TrollStorePro
   
    2、巨魔商店 频道
    https://t.me/iOS_TrollStore
   
    3、秋名山巨魔俱乐部
    https://t.me/ae86_ios
   
    4、浥轻尘&黑科技&软件脚本破解库
    https://t.me/yqc_123
   
    5、iOS宝藏
    https://t.me/iosrxwy
   
    6、登拜科技
    https://t.me/dengbai
   
    7、JB交流 巨魔砸壳作者
    https://t.me/gblwjb
   
    8-MacKed Channel 破解iOS和mac大佬
    https://t.me/macked_channel
   
    9、小果子
    https://t.me/iosapper
   
    10、酷卡iOS破解软件
    https://t.me/gekuGou

## 3、iOS越狱插件
</span>

    1、懒猫插件交流
    https://t.me/maogroup
   
    2、懒猫的频道
    https://t.me/lanmaoshare
   
    3、WeChat｜微信｜插件
    https://t.me/wechatshare
   
    4、黄白｜助手｜插件频道
    https://t.me/HbHelper
    
    5、PKC皮卡车
    https://t.me/TopStyle2021
   
    6、刀刀源
    https://t.me/ae86_hk
    
    7、Netskao 曾经的狗哥
    https://t.me/IPAPatch
   
    8、SWIGN越狱交流群｜新晋作者
    https://t.me/abox1993

一些云盘影视频道
</span>

    1、影视分享 
    https://t.me/movies_metamm
   
    2、阿里云盘发布频道
    https://t.me/Aliyundrive_Share_Channel


# 三、薅羊毛上车抓Cookie教程记录
## 1、什么值得买app
</span>

    手机抓包域名为 userapi.smzdm.com 下的任意链
    接,任选一条把结尾为(iphone;)的Cookie复制出来.
类似以下这种
</span>

    z_df=%2B473T0N2A3LSg09XSw3BfgN%2BeIogL%2FWSJO9Mnn4JPw5Lmr86XkADqQ%3D%3D;session_id=wl3ficQiuwPxzplVKI0%2BqZfDiSvab3hZRF7Le%2B4E6V56j0wCoWp%2FUg%3D%3D.1716516408;basic_v=0;device_s=wl3ficQiuwPxzplVKI0qZfDiSvab3hZRF7Le4E6V7NbPjdmHxi6DPzbu%2Fgk8BJl4nMS84UGw%3D;device_recfeed_setting=%7B%22homepage_sort_switch%22%3A%221%22%2C%22haojia_recfeed_switch%22%3A%221%22%2C%22other_recfeed_switch%22%3A%221%22%2C%22shequ_recfeed_switch%22%3A%221%22%7D;phone_sort=8X;register_time=1699684223;device_id=wl3ficQiuwPxzplVKI0%2BqZfDiSvab3hZRF7Le%2B4E6V56j0wCoWp%2FUg%3D%3D;f=iphone;device_name=iPhone%2013%20Pro%20Max;is_new_user=0;apk_partner_name=appstore;active_time=1699684173;v=11.0.10;is_dark_mode=0;device_smzdm_version_code=151;device_smzdm_version=11.0.10;device_system_version=17.0;sess=BC-hAlRfYzs8j3gmLcbFQ6qz5hMNpzKuwJPZzzrwnVTE0OcdGWqjGm301owV4HSZijO%2F3x9euLujakJvg2bh%20rc6eGZ3HhT9cjO2CE03D0JyJCcYYgF8B8Dk6mwfQ%3D%3D;login=1;client_id=1f4653a147055ed093a1a42f46601d23.1716428857607;osversion=21A329;onmac=0;network=5;smzdm_id=6356227657;device_push=notifications_are_disabled;ab_test=l;device_type=iPhone14%2C3;font_size=normal;device_smzdm=iphone;
## 2、太平通app
</span>

    （抓ecustomer.cntaiping.com域名下的随便
    一个x-ac-token-ticket的值：xzxxxxxxxx,xxxxx）

类似以下这种
</span>

    eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOltdLCJzdWIiOiIxNzE1MDQxNTc0NzIxR0xCODduM3o4RmQ5NnBuVXNPbDhNViIsInVzZXJfbmFtZSI6Ijg5ODcyNjM0MDg4Nzg3MzUzNjAiLCJsb2dpY19pZCI6MzYwNTEwMDA2NzExNTI5NDcyLCJpc3MiOiJraHQudGFpcGluZyIsInNjb3BlIjpbXSwiZ3JhbnRfdHlwZSI6InBhc3N3b3JkIiwianRpIjoiMTcxNTA0MTU4NjQ1OEM5WGhTb1cyTk1IY1R6Y3l1TzNNeVoiLCJhZGRpdGlvbmFsSW5mbyI6e30sImlhdCI6MTcxNTA0MTU4NiwiZXhwIjoxNzc5ODQxNTg2LCJhdXRob3JpdGllcyI6W10sImNsaWVudF9pZCI6IlRQVF9BUFAiLCJyb2xlX3R5cGVzIjoiQyJ9.GO9D0gmY4H7jlcfOdB72K3_KKBRtCQBFlNJV4E6luVHSu6Yxh5bUtFXwSwfoQqKplpQkwzwqliN8Vc6Xsgq80Hp6-YM28P2SY0XzIIkl0Xz84BWhsLVhwGI9uQ5cYxt4yb9_cA_-0kAFx2NCo1nqrpjTKsC4jxT6PTdfwRWieqc

## 3、饿了么app

</span>

    找到抓包域名为 nt2.exe.me 进去第一个点进去
    挨个复制
</span>

    und=
    cookie2=***
    USERID***
    SID=*** 
    wxUid=UID***

$\color{#F56C6C}{如果SID=***结尾有==记得删掉}$ <br>

然后把以上内容拼接在一起。
再找到Wxpusher消息推送平台公众号进去-点击我的-获取UID

类似以下格式
</span>

    unb=2211211076533;cookie2=2fae838adc772d1caf911b3cc9aaa887;USERID=1000172475694;SID=MmZhZTgzOGFkYzc3MmQxY2FmOTExYjNjYzlhYWE4ODelp6EYRxJUWXhqUrSh5xVH;wxUid=UID_FLRReNeAs1fN1SxN19bcYyPoAgVX;
# 四、iOS URL Scheme收集整理
比较全的系统URL项目地址
</span>

    https://github.com/FifiTheBulldog/ios-settings-urls/blob/master/settings-urls.md

<details>
<summary>系统URL</summary>
文件
</span>

    shareddocuments://
钱包 
</span>

    shoebox://
捷径 
</span>

    shortcuts://
邮箱 
</span>

    Message://
备忘录 
</span>

    mobilenotes://

</details>
<details>
<summary>国外社交</summary>
推特
</span>

    Twitter://
Telegram 
</span>

    tg://
swiftgram 
</span>

    sg://
YouTube 
</span>

    youtube://
Instagram 
</span>

    instagram://

</details>
<details>
<summary>导航地图</summary>
高德地图 
</span>

    iosamap://
百度地图 
</span>

    baidumap://
腾讯地图 
</span>

    qqmap://
北京交警 
</span>

    zcblbjjj://
滴滴出行 
</span>

    diditaxi://
摩拜单车扫码 
</span>

    mobike://scanqr
订票助手 
</span>

    trainassist://
艺龙旅行 
</span>

    elongIPhone://
携程无线 
</span>

    CtripWireless://
淘宝旅行 
</span>
    
    taobaotravel://

</details>
<details>
<summary>购物篇</summary>

淘宝 
</span>

    taobao://
淘宝(搜索)
</span>

    taobao://s.taobao.com/?q=裙子
支付宝 
</span>

    alipay://
支付宝(付款)
</span>

    alipayqr://platformapi/startapp?saId=20000056
支付宝(扫一扫)
</span>

    alipayqr://platformapi/startapp?saId=10000007
支付宝记账
</span>

    alipay://platformapi/startapp？appId=20000168
支付宝滴滴
</span>

    alipay://platformapi/startapp?appId=20000778
支付宝蚂蚁森林 
</span>

    alipay://platformapi/startapp?appId=60000002
支付宝转账 
</span>

    alipayqr://platformapi/startapp?saId=20000116
支付宝手机充值 </span>

    alipayqr://platformapi/startapp?saId=10000003
支付宝口令红包 
</span>

    alipayqr://platformapi/startapp?saId=88886666
支付宝提现 
</span>

    alipayqr://platformapi/startapp？saId=20000033
支付宝余额宝 
</span>

    alipayqr://platformapi/startapp？saId=20000032
支付宝蚂蚁庄园 
</span>

    alipays://platformapi/startap
京东 
</span>

    openapp.jdmoble://
美团 
</span>

    imeituan://
大众点评 
</span>

    dianping://
1号店 
</span>

    yhd://
唯品会 
</span>

    vipshop://
天猫 
</span>

    tmall://
旺旺卖家版
</span>

    wangwangseller://

</details>
<details>
<summary>工具类</summary>

Cerulean工具箱 
</span>

    Cerulean://
钱迹
</span>

    qianji://
Picsew 
</span>

    picsew://
Picsew打开最近长截图 
</span>

    picsew://recent
我的标记 
</span>

    clover-imark://
抓图猫 
</span>

    imagecat://
Piiic 2 
</span>

    wb1934889315://
Alook浏览器 
</span>

    Alook://
115云盘 
</span>

    wb1307639798://
123云盘 
</span>

    wx5d164fd6498c6e80://
米家
</span>

    mihome://
uc浏览器 
</span>

    ucbrowser://
搜狗输入法 
</span>

    com.sogou.sogouinput://
圈子账本 
</span>

    qzzb://
我的密码
</span>

    findmykey://
我查查 
</span>

    wcc://

名片全能王 
</span>

    camcard://
Evernote 
</span>

    evernote://
迅雷 
</span>

    thunder://
天气通 
</span>

    sinaweather://
墨迹天气 
</span>

    rm434209233MojiWeather://
同花顺 
</span>

    amihexin://


</details>
<details>
<summary>腾讯系列</summary>
微信扫一扫
</span>

    weixin://scanqrcode
微信付款码
</span>

    weixin://widget/pay
QQ
</span>

   mqq://
QQ音乐 
</span>

    qqmusic://
QQ音乐最近播放 
</span>

    qqmusic://today?mid=31&k1=2
QQ音乐本地播放 
</span>

    qqmusic://today?mid=31&k1=3
QQ音乐听歌识曲 </span>

    qqmusic://http://qq.com/ui/recognize
腾讯安全中心
</span>

    qmtoken://
腾讯手机管家 
</span>

    mqqsecure://
腾讯视频 
</span>

    tenvideo://
腾讯新闻 
</span>

    qqnews://
腾讯微云 
</span>

    weiyun://
微信读书 
</span>

    weread://
腾讯企业邮箱 
</span>

    qqbizmailDistribute2://
Chrome 
</span>

    googlechrome://
QQ邮箱 
</span>

    qqquicklogin://
QQ浏览器 
</span>

    mqqbrowser://

QQ同步助手 
</span>

    qqpim://

腾讯企业邮箱 
</span>

    qqbizmailDistribute2://
腾讯手机管家 
</span>

    mqqsecure://

</details>
<details>
<summary>网易系列</summary>

网易新闻
</span>

    newsapp://
网易云音乐
</span>

    orpheus://
网易云(识别音乐)
</span>

    orpheus://recognize
网易云（本地音乐）
</span>

    orpheus://download
网易云（私人FM）
</span>

    orpheus://radio
网易云（我的喜欢）
</span>

    orpheus://playlist/32778108
网易严选 
</span>

    yanxuan://
有道词典 
</span>

    yddict://
网易邮箱 
</span>

    neteasemail://
网易公开课 
</span>

    ntesopen://
网易将军令
</span>

    netease-mkey://
有道词典 
</span>

    yddictproapp://
有道翻译官 
</span>

    ydtranslator://
</details>
<details>
<summary>百度系列</summary>

百度云
</span>

    baiduyun:// 
百度输入法 
</span>

    BaiduIMShop://
百度阅读 
</span>

    bdbook://
手机百度 
</span>

    bdboxiosqrcode://
百度音乐 
</span>

    baidumusic://
百度视频 
</span>

    bdviphapp://
百度浏览器 
</span>

    bdbrowser://
</details>
<details>
<summary>影音类</summary>
酷我音乐 </span>

    com.kuwo.kwmusic.kwmusicForKwsing://
搜狐视频 
</span>

    sohuvideo-iphone://
虾米音乐 
</span>

    xiami://
抖音 
</span>

    wb1462309810://
快手 
</span>

    gifshow://
火山小视频 
</span>

    wb1462309810://
爱奇艺视频 
</span>

    qiyi-iphone://
PPTV 
</span>

    pptv://
今日头条 
</span>

    snssdk141://
哔哩哔哩动画
</span>

    bilibili://
优酷 
</span>

    youku://
搜狐视频 
</span>

    sohuvideo://
掌阅iReader
</span>

    iReader://

豆瓣FM 
</span>

    doubanradio://
全民K歌 
</span>

    qmkege://

</details>
<details>
<summary>银行系列</summary>
招商银行 
</span>

    cmbmobilebank://
建设银行
</span>

    wx2654d9155d70a468://
工商银行 
</span>

    com.icbc.iphoneclient://
中国银行 
</span>

    BOCMBCIZF://
农业银行 
</span>

    bankabc://
邮政银行 
</span>

    wb1424286189://
浦发银行 
</span>

    wx1cb534bb13ba3dbd://
云闪付扫一扫
</span>

    upwallet://native/scanCode
云闪付付款码 
</span>

    upwallet://pay
云闪付乘车码 
</span>

    upwallet://rn/rnhtmlridingcode

</details>
<details>
<summary>游戏系列</summary>
王者荣耀
</span>

    tencentlaunch1104466820://
绝地求生 刺激战场 
</span>

    itlogin-JSMahjong://
海岛奇兵 
</span>

    app://gridlens://
天天飞车 
</span>

    tencent100695850://
天天星连萌 
</span>

    tencent100689806://
天天爱消除 
</span>

    tencent100689805://
天天酷跑 
</span>

    tencent100692648://
</details>


