Quantumult X 策略组是什么？
- 策略组可以实现 自动切换节点、节点筛选、是否走代理等。
- 策略组 需要配合 分流规则 使用。
- 策略组 可包含多个节点和策略组。

Quantumult X 自带 3 种策略。
- PROXY （代理）
- DIRECT（直连）
- REJECT（拒绝）

Quantumult X 策略组类型。
- static 静态策略-手动选择节点
- available 健康检查-自动选择节点，从第一个节点开始检查是否可用，直到选择可用节点。
- round-robin 负载均衡-轮询调度，轮流调用节点使用，IP可能会一直变。
- dest-hash 随即调整负载均衡
- url-latency-benchmark 自动测速-自动选择延迟低的节点

Quantumult X 分流规则。
- Spotify分流 
- https://whatshub.top/rule/Spotify.list
- Copilot分流 https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX/Microsoft/Microsoft.list
- 国际网络分流
- https://raw.githubusercontent.com/kjfx/QuantumultX/main/country/filter.list
- Twitter分流
- https://whatshub.top/rule/Twitter.list
- 国内媒体分流
- https://whatshub.top/rule/ChinaMedia.list
- YouTube Music分流
- https://whatshub.top/rule/YouTubeMusic.list
- YouTube分流
- https://whatshub.top/rule/YouTube.list
- 抖音IP分流
- https://raw.githubusercontent.com/im-dashan/proxy-plugin/main/loon/DouYin.list
- 抖音IP分流最新群友给的
- https://whatshub.top/rule/DouYin.list
- 微博分流
- https://whatshub.top/rule/Weibo.list
- 国内直连
- https://whatshub.top/rule/China.list
- Telegram分流
- https://whatshub.top/rule/Telegram.list
- ChatGPT分流
- https://whatshub.top/rule/ChatGPT.list

Quantumult X 重写资源。
- 酷安净化
- https://github.com/ddgksf2013/Scripts/raw/master/coolapk.js
- 百度网盘净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/BaiduNetDisk_remove_ads.plugin
- 阿里云盘净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/AliYunDrive_remove_ads.plugin
- 起点读书净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/QiDian_remove_ads.plugin
- 12406净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/12306_remove_ads.plugin
- 淘宝净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/Taobao_remove_ads.plugin
- 京东净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/JD_remove_ads.plugin
- 微博净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/Weibo_remove_ads.plugin
- YouTube净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/YouTube_remove_ads.plugin
- 百度地图净化
- https://gist.githubusercontent.com/ddgksf2013/beec132ca0c3570ffa0cf331bce8f82a/raw/baidumap.adblock.conf
- 高德地图净化
- https://github.com/ddgksf2013/Rewrite/raw/master/AdBlock/Amap.conf
-  Spotify净化
- https://gitlab.com/lodepuly/vpn_tool/-/raw/master/Tool/Loon/Plugin/Spotify_remove_ads.plugin
- vvwbo修复主页
- https://raw.githubusercontent.com/bin64/Scripts/main/QuantumultX/vvebo.js
- 最美证件照VIP
- https://raw.githubusercontent.com/WeiGiegie/666/main/zjzxg.js
- 酷我音乐VIP
- https://napi.ltd/script/Worker/KuWo.js
- 读不舍手VIP
- https://gist.githubusercontent.com/ddgksf2013/dbb1695cd96743eef18f3fac5c6fe227/raw/revenuecat.js
- 韩小圈VIP
- https://gist.githubusercontent.com/Yu9191/35453bcc1df1fd21febed34eb078c7e9/raw/Hanxiaoquan.sgmodules

- Quantumult X 手动添加。
[general]下面添加
用于节点延迟测试
server_check_url= http://www.gstatic.com/generate_204
#用于节点地址
geo_location_checker=http://ip-api.com/json/?lang=zh-CN, https://raw.githubusercontent.com/I-am-R-E/Functional-Store-Hub/Master/GeoLocationChecker/QuantumultX/IP-API.js
服务器测试超时时间 (毫秒)
server_check_timeout = 3000
功能强大的解析器，用于引用资源的转换
resource_parser_url=https://cdn.jsdelivr.net/gh/KOP-XIAO/QuantumultX@master/Scripts/resource-parser.js
下列路径将不经过QuanX的处理
excluded_routes=239.255.255.250/32, 24.105.30.129/32, 185.60.112.157/32, 185.60.112.158/32, 182.162.132.1/32
udp_whitelist=1-442, 444-65535

- 配置文件中[filter_remote]下粘贴以下内容
FILTER_LAN, tag=LAN, force-policy=direct, enabled=true
FILTER_REGION, tag=CN, force-policy=direct, enabled=true
