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
- dest-hash
- url-latency-benchmark 自动测速-自动选择延迟低的节点
