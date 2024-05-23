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
- 配置文件中[filter_remote]下粘贴以下内容
FILTER_LAN, tag=LAN, force-policy=direct, enabled=true
FILTER_REGION, tag=CN, force-policy=direct, enabled=true
