分流规则
1、分流规则是什么？
分流规则可以实现不同的网站走不同的节点，自动让网站或APP走指定的节点或策略组，不需要人工操作。
2、Quantumult X 分流规则类型
HOST / 域名匹配 / 例如：www.google.com
HOST-SUFFIX / 域名后缀匹配 / 例如：google.com
HOST-KEYWORD / 域名关键字匹配 / 例如：google
USER-AGENT / 用户代理匹配 / 例如：*abc?
IP-CIDR / IP匹配 / 例如：192.168.0.1/24
IP6-CIDR / IPV6
GEOIP / IP数据库匹配 / 例如：US
3、添加分流规则
打开Quantumult X 配置文件，找到 [filter_remote] 和 [filter_local] 位置可以添加
点击 分流规则 按钮也可以添加和引用分流规则。
分流规则（引用）示例：
https://raw.githubusercontent.com/kjfx/QuantumultX/main/country/filter.list

策略组
1、策略组是什么？
策略组可以实现 自动切换节点、节点筛选、是否走代理等。
策略组 需要配合 分流规则 使用。
策略组 可包含多个节点和策略组。
2、Quantumult X 自带 3 种策略。
PROXY（代理）
DIRECT（直连）
REJECT（拒绝）
3、Quantumult X 策略组类型
static 静态策略-手动选择节点
available 健康检查-自动选择节点，从第一个节点开始检查是否可用，直到选择可用节点。
round-robin 负载均衡-轮询调度，轮流调用节点使用，IP可能会一直变。
dest-hash
url-latency-benchmark 自动测速-自动选择延迟低的节点
4、添加策略组 （重点）
打开Quantumult X 配置文件，找到 [policy] 位置
默认策略
static=default, proxy, direct, reject
筛选节点的策略组
static= HK 香港, server-tag-regex= 香港|
